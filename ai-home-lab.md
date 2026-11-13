---
layout: page
title: "AI Home Lab"
permalink: /ai-home-lab/
---

**The lab is currently empty.** Shadowfax and Zebra were both sold on 13 November 2026, after 3 days on the market each. The private tailnet remains in place for the family's laptops, phones and desktops, but there is no longer any AI hardware in the lab. This page is retained as a record of what ran here.

<video controls preload="metadata" style="width:100%;max-width:100%;border-radius:8px;">
  <source src="{{ '/assets/images/home-ai-lab-video.mp4' | relative_url }}" type="video/mp4">
  Your browser does not support the video tag.
</video>

## Fleet (historical)

| | **Shadowfax** | **Zebra** |
|---|---|---|
| Status | **Sold** — 3 days on market | **Sold** — 3 days on market |
| Sale price | C$8,500 incl. NVLink (≈ US$6,000) | C$3,500 (≈ US$2,500) |
| Role | GPU serving and orchestration | Local model serving and RPC |
| Machine | Custom desktop | Mac mini (Mac16,11) |
| CPU | AMD Ryzen 9 9950X3D, 16C/32T, up to 5.76 GHz, 128 MB L3 | Apple M4 Pro, 14 cores (10 performance + 4 efficiency) |
| GPU | 2 x NVIDIA GeForce RTX 3090, 24 GB each, NVLink-bridged | Apple M4 Pro, 20-core GPU, Metal 4 |
| Memory | 64 GB DDR5 | 64 GB unified |
| Storage | WD_BLACK SN850X 4 TB NVMe | 1 TB Apple SSD (AP1024Z) |
| Networking | 10 GbE, 2.5 GbE, 5 GbE, Wi-Fi 7, Thunderbolt 3 | 10 GbE, Wi-Fi 6E, 3 x Thunderbolt 5 |
| Operating system | Ubuntu 24.04.5 LTS (kernel 7.0.0-38) | macOS 27.0.1 |

## Shadowfax (sold)

Shadowfax was a custom AMD desktop with two RTX 3090s joined by NVLink. It ran the large-model serving stack and the Hermes Agent gateway. It was listed at **US$5,100** (≈ C$7,200) on 10 November 2026 and sold with the EVGA 4-slot NVLink bridge for **C$8,500** (≈ US$6,000) on 13 November 2026 — **3 days on the market**. The bridge had been listed separately at US$1,000 and sold with the machine, also after 3 days. The [SOLD listing](/2026/11/10/shadowfax-dual-rtx-3090-workstation-for-sale/) has the full specifications and photos.

### Hardware

- **Motherboard:** ASUS ROG Crosshair X870E Hero
- **CPU:** AMD Ryzen 9 9950X3D — 16 cores, 32 threads, 5.76 GHz boost, 128 MB L3 cache
- **CPU cooler:** DeepCool Assassin IV dual-tower air cooler
- **Memory:** 64 GB Kingston Fury Beast DDR5-6000 CL30 (2 × 32 GB), about 62 GiB usable
- **GPUs:** two EVGA GeForce RTX 3090 FTW3 Ultra cards (GA102, 24 GB GDDR6X each), driver 595.99.02, CUDA 13.2; board power limits 500 W and 450 W
- **GPU interconnect:** EVGA 4-slot NVLink bridge, four links at 14.062 GB/s each (`NV4`, roughly 56 GB/s per direction)
- **Storage:** WD_BLACK SN850X 4 TB NVMe, about 1.7 TB in use
- **Power supply:** Seasonic PRIME PX-1600 ATX 3, 1600 W 80+ Platinum, fully modular
- **Case:** Fractal Design Torrent, high-airflow tower
- **Networking:** Aquantia AQC107 10 GbE (connected at 10 Gb/s), Intel I226-V 2.5 GbE, Realtek RTL8126 5 GbE, MediaTek MT7927 Wi-Fi 7 and a Thunderbolt 3 add-in card
- **Operating system:** Ubuntu 24.04.5 LTS, kernel 7.0.0-38-generic

### Serving stack

- **Tabby with ExLlamaV3 1.6.3** served **Qwen3.8-27B at EXL3 5 bpw** (19 GB) across both GPUs, with tensor parallelism and a 22/22 GB split.
- Speculative decoding used **MTP with 5 draft tokens**; the maximum batch size was 4.
- Context was a single **262,144-token (256K)** window with a 327,680-token FP16 KV cache.
- The model backend was bound to `127.0.0.1:18083`; an inference-only proxy exposed port `18080` on the tailnet.
- **DeepSeek-V4-Flash-REAP** — a 132-expert FP8 mixture-of-experts (6 active experts, 43 layers, 1M-token maximum context) with 79 GB of local weights — ran through the [Colibri](https://github.com/bobsummerwill/colibri) runtime.

## Zebra (sold)

Zebra was a Mac mini with an M4 Pro, 64 GB of unified memory and 10 Gigabit Ethernet. It served local models and could act as an RPC worker. It had been left running for long stretches, but in practice it saw light, occasional use rather than a constant workload. It was listed at **US$2,500** (≈ C$3,500) on 10 November 2026 and sold for **C$3,500** (≈ US$2,500) on 13 November 2026 — **3 days on the market**. The [SOLD listing](/2026/11/10/zebra-mac-mini-m4-pro-for-sale/) has the full specifications and photos.

### Hardware

- **Machine:** Mac mini (Mac16,11), Apple M4 Pro
- **CPU:** 14 cores — 10 performance and 4 efficiency
- **GPU:** 20-core Apple GPU, Metal 4
- **Memory:** 64 GB unified
- **Storage:** 1 TB Apple SSD (AP1024Z, 994.7 GB), about 615 GB in use (379 GB free)
- **Networking:** 10 Gigabit Ethernet (10Gbase-T), Wi-Fi 6E (802.11ax), three Thunderbolt 5 ports (up to 120 Gb/s)
- **Operating system:** macOS 27.0.1 (build 26A434)

### Serving stack

- **llama.cpp 0.6.0-dev** (build 132, commit `42c787e`, Metal) served **Gemma-4-31B-it Q4_K_M** (17 GB) on demand.
- The server ran 999 GPU layers with flash attention, batch 1024 / ubatch 512, a **131,072-token context** and the alias `gemma-4-31b` on port `18080`, managed by the `com.zebra.llama-gemma` LaunchAgent so it was available after a reboot.
- The local model cache also carried Qwen3.8-27B and Qwen3-30B-A3B Q4_K_M.
- Zebra could join Shadowfax as an RPC worker when a model needed more memory than either machine had alone.

### Health

Measured 12 November 2026 with `smartctl` and `macmon`:

- **SSD:** SMART overall **PASSED**; **0%** of rated endurance used; **5.60 TB written** and 48.3 TB read; zero media/data-integrity errors; 100% available spare; **281 power-on hours** and 133 power cycles.
- **Thermals:** macOS never recorded a thermal or performance warning. Idle temperatures were about 38 °C CPU and 35 °C GPU. Under a 45-second sustained full-GPU inference load, the GPU stayed at 100% utilisation and its maximum clock (1576–1578 MHz) throughout — no throttling. Peak temperatures were 70.8 °C CPU and 89.2 °C GPU, with package power averaging 72 W (peak 77 W).
- **Stability:** no kernel panics in the last 30 days of system logs, no panic reports on disk, and 15 days of uptime at check time.

## On the tailnet (historical)

- [Tailscale](https://tailscale.com) provided the private mesh, MagicDNS names and ACL-based SSH access.
- While the lab was running, the OpenAI-compatible endpoints were:
  - `http://shadowfax:18080/v1` — Qwen3.8-27B, through the inference-only proxy
  - `http://zebra:18080/v1` — Gemma-4-31B
- Access was per-device through Tailscale ACLs; no ports were forwarded to the internet.
- With both machines sold, the `shadowfax` and `zebra` endpoints are gone. The tailnet itself remains in use for the family's laptops, phones and desktops.

## Hermes Agent (historical)

Hermes Agent was the control plane for the lab: one gateway process connected the chat interfaces, model endpoints, tools, skills, memory and scheduled jobs. It ran on Shadowfax as `hermes-gateway.service`, started at boot, restarted on failure and kept its state under `~/.hermes`.

### Custom skills

Most of the useful behavior here came from custom skills the agent wrote for this lab. They covered running and benchmarking the serving stack, publishing services on the tailnet and diagnosing peer or ACL problems, keeping long-running autonomous work anchored to GitHub issues and live state, and handling recurring personal finance and task workflows. Others wired in local browser automation, coding harnesses, email and file services.

---

*Last updated 2026-11-13. The lab is currently empty; hardware and software details are retained as historical records.*
