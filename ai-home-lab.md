---
layout: page
title: "AI Home Lab"
permalink: /ai-home-lab/
---

Two machines, one private tailnet. The lab serves every family device over [Tailscale](https://tailscale.com): laptops, phones, desktops and the servers themselves. Access is governed by Tailscale ACLs, and no services are port-forwarded to the internet.

## Fleet

| | **Shadowfax** | **Zebra** |
|---|---|---|
| Role | GPU serving and orchestration | Always-on serving and RPC |
| Machine | Custom desktop | Mac mini (Mac16,11) |
| CPU | AMD Ryzen 9 9950X3D, 16C/32T, up to 5.76 GHz, 128 MB L3 | Apple M4 Pro, 14 cores (10 performance + 4 efficiency) |
| GPU | 2 x NVIDIA GeForce RTX 3090, 24 GB each, NVLink-bridged | Apple M4 Pro, 20-core GPU, Metal 4 |
| Memory | 64 GB DDR5 | 64 GB unified |
| Storage | WD_BLACK SN850X 4 TB NVMe | 1 TB Apple SSD (AP1024Z) |
| Networking | 10 GbE, 2.5 GbE, 5 GbE, Wi-Fi 7, Thunderbolt 3 | 10 GbE, Wi-Fi 6E, 3 x Thunderbolt 5 |
| Operating system | Ubuntu 24.04.5 LTS (kernel 7.0.0-38) | macOS 27.0.1 |

## Shadowfax

Shadowfax is a custom AMD desktop with two RTX 3090s joined by NVLink. It runs the large-model serving stack and the Hermes Agent gateway.

### Hardware

- **Motherboard:** ASUS ROG Crosshair X870E Hero, BIOS 1003 (January 2025)
- **CPU:** AMD Ryzen 9 9950X3D — 16 cores, 32 threads, 5.76 GHz boost, 128 MB L3 cache
- **Memory:** 64 GB DDR5 (about 62 GiB usable)
- **GPUs:** two NVIDIA GeForce RTX 3090s (GA102, 24 GB GDDR6X each), driver 595.99.02, CUDA 13.2; board power limits 500 W and 450 W
- **GPU interconnect:** NVLink bridge, four links at 14.062 GB/s each (`NV4`, roughly 56 GB/s per direction)
- **Storage:** WD_BLACK SN850X 4 TB NVMe, about 1.7 TB in use
- **Networking:** Aquantia AQC107 10 GbE (connected at 10 Gb/s), Intel I226-V 2.5 GbE, Realtek RTL8126 5 GbE, MediaTek MT7927 Wi-Fi 7 and a Thunderbolt 3 add-in card
- **Operating system:** Ubuntu 24.04.5 LTS, kernel 7.0.0-38-generic

### Serving stack

- **Tabby with ExLlamaV3 1.6.3** serves **Qwen3.8-27B at EXL3 5 bpw** (19 GB) across both GPUs, with tensor parallelism and a 22/22 GB split.
- Speculative decoding uses **MTP with 5 draft tokens**; the maximum batch size is 4.
- Context is **131,072 tokens per request** with a 262,144-token FP16 KV cache.
- The model backend binds to `127.0.0.1:18083`; an inference-only proxy exposes port `18080` on the tailnet.
- **DeepSeek-V4-Flash-REAP** — a 132-expert FP8 mixture-of-experts (6 active experts, 43 layers, 1M-token maximum context) with 79 GB of local weights — runs through the [Colibri](https://github.com/bobsummerwill/colibri) runtime.

## Zebra

Zebra is a Mac mini with an M4 Pro, 64 GB of unified memory and 10 Gigabit Ethernet. It runs the always-on model server and can act as an RPC worker.

### Hardware

- **Machine:** Mac mini (Mac16,11), Apple M4 Pro
- **CPU:** 14 cores — 10 performance and 4 efficiency
- **GPU:** 20-core Apple GPU, Metal 4
- **Memory:** 64 GB unified
- **Storage:** 1 TB Apple SSD (AP1024Z, 994.7 GB), about 548 GB in use
- **Networking:** 10 Gigabit Ethernet (10Gbase-T), Wi-Fi 6E (802.11ax), three Thunderbolt 5 ports (up to 120 Gb/s)
- **Operating system:** macOS 27.0.1 (build 26A434)

### Serving stack

- **llama.cpp 0.6.0-dev** (build 132, commit `42c787e`, Metal) serves **Gemma-4-31B-it Q4_K_M** (17 GB) around the clock.
- The server runs 999 GPU layers with flash attention, batch 1024 / ubatch 512, a **131,072-token context** and the alias `gemma-4-31b` on port `18080`, managed by the `com.zebra.llama-gemma` LaunchAgent.
- The local model cache also carries Qwen3.8-27B and Qwen3-30B-A3B Q4_K_M.
- Zebra can join Shadowfax as an RPC worker when a model needs more memory than either machine has alone.

## On the tailnet

- [Tailscale](https://tailscale.com) provides the private mesh, MagicDNS names and ACL-based SSH access.
- OpenAI-compatible endpoints:
  - `http://shadowfax:18080/v1` — Qwen3.8-27B, through the inference-only proxy
  - `http://zebra:18080/v1` — Gemma-4-31B
- Access is per-device through Tailscale ACLs; no ports are forwarded.

## Hermes Agent

Hermes Agent is the control plane for the lab: one gateway process connects the chat interfaces, model endpoints, tools, skills, memory and scheduled jobs. It runs on Shadowfax as `hermes-gateway.service`, starts at boot, restarts on failure and keeps its state under `~/.hermes`.

### Custom skills

Most of the useful behavior here comes from custom skills the agent wrote for this lab. They cover running and benchmarking the serving stack, publishing services on the tailnet and diagnosing peer or ACL problems, keeping long-running autonomous work anchored to GitHub issues and live state, and handling recurring personal finance and task workflows. Others wire in local browser automation, coding harnesses, email and file services.

---

*Last verified 2026-10-29. Hardware and software versions are point-in-time observations.*
