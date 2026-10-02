---
layout: page
title: "Zebra"
permalink: /zebra/
---

# Zebra

Bob's Mac mini — the second local-LLM lane in the household, alongside [Shadowfax](/about/).

## Machine

| | |
|---|---|
| Model | Mac mini (Mac16,11), Apple M4 Pro |
| CPU | 14-core |
| GPU | 20-core (Metal) |
| Memory | 64 GB unified |
| OS | macOS |
| Tailscale | `zebra` — `zebra.tailbcc578.ts.net` (100.123.224.80) |

## Role

A local inference lane for the same model family as Shadowfax (Qwen3.8-27B), so Hermes Agent behaves consistently across machines. The M4 Pro's 64 GB of unified memory comfortably fits the Q4_K_M quant (~18 GB) with large context headroom, and leaves room to bake off Q6_K (~21 GB) and Q8_0 (~28 GB).

- Serving: llama.cpp (Metal backend), local port 8090
- Models: `~/Models/` — transferred over the tailnet from Shadowfax, no re-download
- Bench targets: 32k / 64k / 128k context responsiveness + tool-call validation

## Status

The machine is back on the tailnet (October 2026), but remote access from Shadowfax is still waiting on an SSH key being provisioned. Until that lands, the lane is not yet serving — see the tracking issues:

- [openclaw-team#51](https://github.com/bobsummerwill/openclaw-team/issues/51) — deploy and benchmark Qwen3.8-27B locally
- [openclaw-team#52](https://github.com/bobsummerwill/openclaw-team/issues/52) — bakeoff Q6_K vs Q8_0 vs Shadowfax Q4_K_M
