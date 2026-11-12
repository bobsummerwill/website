---
layout: post
title: "Mac mini M4 Pro (64 GB / 1 TB) — for sale"
date: 2026-11-10
author: Bob Summerwill
featured_image: /assets/mac-mini/mac-mini-01.jpg
excerpt: "Selling the Mac mini M4 Pro from my AI home lab: 14-core CPU, 20-core GPU, 64 GB unified memory, 1 TB SSD, 10 Gigabit Ethernet and AppleCare+ until 2 March 2029. Lightly used — 281 power-on hours, 0% SSD endurance consumed. US$2,500 (≈ C$3,500) or nearest offer. Pickup in Vancouver or worldwide shipping at buyer's expense."
---

<style>
.sale-buy { background: #f7f7f7; border-left: 4px solid #1F3A5F; padding: 1em 1.25em; margin: 0 0 2em; }
.sale-buy p:last-child { margin-bottom: 0; }
.mac-mini-gallery { display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: 12px; margin: 0 0 2em; }
.mac-mini-gallery figure { margin: 0; }
.mac-mini-gallery a { display: block; }
.mac-mini-gallery img { width: 100%; height: 220px; object-fit: cover; border: 1px solid #eee; border-radius: 4px; }
.mac-mini-gallery figcaption { font-size: 1.3rem; line-height: 1.5; color: #666; margin-top: 0.5em; }
.mac-mini-receipt { max-width: 640px; margin: 0 0 2em; }
.mac-mini-receipt img { width: 100%; height: auto; border: 1px solid #eee; border-radius: 4px; }
.mac-mini-receipt figcaption { font-size: 1.3rem; line-height: 1.5; color: #666; margin-top: 0.6em; }
</style>

I have some new purchases planned for the [AI home lab](/ai-home-lab/), so **Zebra** — the lab's Mac mini — is for sale. It is an M4 Pro with the maximum 64 GB of unified memory, a 1 TB SSD and 10 Gigabit Ethernet, bought new from Apple in February 2026 and still covered by AppleCare+ until 2 March 2029.

It has been part of the lab as a local model server, left running for long stretches, but in practice it has seen light use rather than a constant workload. The drive reports **281 power-on hours**, **0%** of its rated endurance consumed and zero media errors. It is quiet, sips power, and is still one of the nicest small machines for local inference on Apple silicon. The 64 GB of memory and 10 GbE are both build-to-order options — 64 GB is the maximum Apple offered in the M4 Pro mini, and 10 GbE was a paid upgrade.

## Why it is interesting

The 64 GB of unified memory is the point. The GPU can address the whole pool, so this machine comfortably runs models that would not fit on a typical 8 GB or 16 GB graphics card. It serves **Gemma-4-31B-it Q4_K_M** with a **131,072-token context** when loaded, and it can also join a larger machine as an RPC worker when a model needs more memory than either host has alone.

It is also a very good general-purpose Mac: fast CPU, three Thunderbolt 5 ports, 10 GbE, and very little fan noise.

## Hardware

| Component | Specification |
|---|---|
| Machine | Mac mini (Mac16,11), silver |
| Chip | Apple M4 Pro — 14-core CPU (10 performance + 4 efficiency), 20-core GPU, 16-core Neural Engine |
| Memory | 64 GB unified, 273 GB/s memory bandwidth |
| Storage | 1 TB Apple SSD (AP1024Z, 994.7 GB) |
| Networking | 10 Gigabit Ethernet (10Gbase-T), Wi-Fi 6E (802.11ax), Bluetooth 5.3 |
| Front ports | 2 × USB-C (USB 3), 3.5 mm headphone jack |
| Rear ports | 3 × Thunderbolt 5 (up to 120 Gb/s), HDMI, 10 GbE, power |
| Operating system | macOS 27.0.1 (build 26A434) |
| Dimensions | 5.0 × 5.0 × 2.0 in (127 × 127 × 50 mm) |
| Weight | 1.6 lb (0.73 kg) |

## Health and performance

Checked on 12 November 2026 with `smartctl` (smartmontools 7.5) and `macmon`.

| SSD metric | Reading |
|---|---|
| SMART overall | **PASSED** |
| Endurance used | **0%** |
| Data written | **5.60 TB** (10,944,005 data units) |
| Data read | 48.3 TB |
| Media / data-integrity errors | **0** |
| Available spare | 100% (threshold 99%) |
| Power-on hours | **281** |
| Power cycles | 133 |
| Temperature (idle) | 31 °C |

281 hours is about 11.7 days of powered-on time since February. The machine has been left running, but it has not been used heavily.

- **Stability:** no kernel panics in the system logs over the last 30 days, no panic reports on disk, and 15 days of uptime at check time.
- **Thermals:** macOS has never recorded a thermal or performance warning. Idle temperatures are about 38 °C CPU and 35 °C GPU.
- **Load test:** 45 seconds of sustained full-GPU inference on Gemma-4-31B Q4_K_M. The GPU stayed at 100% utilisation and its maximum clock (1576–1578 MHz) for the whole run — no throttling. Peak temperatures were **70.8 °C CPU** and **89.2 °C GPU**; package power averaged 72 W (peak 77 W); the fan reported around 1000 rpm; memory pressure peaked at 51% of 64 GB.

The full `smartctl` output is available on request, and I am happy to repeat any of these checks over a video call.

## Purchase and warranty

- Bought new from Apple on 7 February 2026; single owner.
- Original configuration: M4 Pro 14-core CPU / 20-core GPU / 16-core Neural Engine, 64 GB unified memory, 1 TB SSD and 10 Gigabit Ethernet.
- Original Apple price: **CA$3,649**, plus **CA$119** for AppleCare+.
- AppleCare+ for Mac mini (M4) is active until **2 March 2029**. I will confirm the transfer process with Apple before sale and provide the agreement number and proof of coverage.

<figure class="mac-mini-receipt">
  <img src="/assets/mac-mini/apple-order-2026-02-07.png" alt="Apple order receipt for the Mac mini M4 Pro" />
  <figcaption>Apple order receipt, 7 February 2026: Mac mini M4 Pro 14-core/20-core, 64 GB unified memory, 1 TB SSD and 10 Gigabit Ethernet — CA$3,649 plus CA$119 for AppleCare+.</figcaption>
</figure>

## What it runs today

- **llama.cpp 0.6.0-dev** (build 132, Metal) set up to serve **Gemma-4-31B-it Q4_K_M** (17 GB) on demand.
- 999 GPU layers, flash attention, batch 1024 / ubatch 512, **131,072-token context**, alias `gemma-4-31b` on port `18080`.
- Managed by a LaunchAgent so it is available after a reboot. It has been left running, but lightly used.
- The local model cache also carries Qwen3.8-27B and Qwen3-30B-A3B Q4_K_M.
- Can act as an RPC worker alongside another llama.cpp host for larger models.

The model cache will be cleared as part of the wipe, so treat the software stack as a demonstration rather than part of the sale.

## Photos

<div class="mac-mini-gallery">
  <figure>
    <a href="/assets/mac-mini/mac-mini-01.jpg" target="_blank" rel="noopener"><img src="/assets/mac-mini/mac-mini-01.jpg" alt="Mac mini M4 Pro powered on, viewed from the front and top" loading="lazy"></a>
    <figcaption>Mac mini powered on.</figcaption>
  </figure>
  <figure>
    <a href="/assets/mac-mini/mac-mini-02.jpg" target="_blank" rel="noopener"><img src="/assets/mac-mini/mac-mini-02.jpg" alt="Rear ports of the Mac mini with the HDMI dummy plug fitted" loading="lazy"></a>
    <figcaption>Rear ports, with the HDMI dummy plug fitted.</figcaption>
  </figure>
  <figure>
    <a href="/assets/mac-mini/mac-mini-03.jpg" target="_blank" rel="noopener"><img src="/assets/mac-mini/mac-mini-03.jpg" alt="Underside of the Mac mini showing the power button and regulatory markings" loading="lazy"></a>
    <figcaption>Underside, showing the power button and regulatory markings.</figcaption>
  </figure>
</div>

## Headless GUI access

An HDMI dummy plug is included if you want it. With the plug fitted, macOS keeps a virtual display active while the Mac mini runs headless, so you can connect to the full desktop over VNC rather than being limited to SSH.

## Condition and what is included

- Single owner, bought new in February 2026. Fully working, no known faults. It has been left running as a lab server for long stretches, with no panics, crashes or thermal warnings, but it has seen light use.
- Sold erased and signed out of iCloud, with macOS reinstalled and ready for setup.
- Original Accessory Kit and power cable included.
- Can be inspected and tested in Vancouver by arrangement.

## Price and shipping

<div class="sale-buy">
<p><strong>US$2,500</strong> (≈ C$3,500) or nearest offer. AppleCare+ runs until 2 March 2029; I will confirm the transfer process with Apple before sale.</p>
<p>Pickup in Vancouver, BC, or shipping worldwide at the buyer's expense. The Mac mini is small and light, so international shipping is straightforward. Payment can be made in USD or CAD.</p>
<p><small>CAD price is approximate, converted at US$1 ≈ C$1.41 on 10 November 2026.</small></p>
</div>

Payment by PayPal G&amp;S, Interac e-transfer, or cash on pickup. If you want more photos, a benchmark, or the exact serial number before buying, [get in touch](/contact/).

---

*Full background and specifications: [AI Home Lab](/ai-home-lab/).*
