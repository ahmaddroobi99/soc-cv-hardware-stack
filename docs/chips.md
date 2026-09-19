# Chip case studies

Three SoCs from the Branch Education SoC episode, verified against public specs.

## Qualcomm Snapdragon 808 (MSM8992)

The teaching phone in the video is the **LG V10** (October 2015).

| Block | Spec |
| --- | --- |
| Process | 20 nm |
| CPU | 2x Cortex-A57 (~1.8-2.0 GHz) + 4x Cortex-A53 (~1.4 GHz), ARMv8-A big.LITTLE |
| GPU | Adreno 418, OpenGL ES 3.1 |
| DSP | Hexagon QDSP V56 |
| ISP | Dual 12-bit ISPs, up to 21 MP |
| Video | 4K30 H.264 capture; H.265 decode |
| Modem | Integrated X10 LTE Cat 9, 450 / 50 Mbps |
| Memory | Dual-channel LPDDR3-933, ~15 GB/s |
| Display | up to 2560x1600 |
| NPU | None. ML ran on DSP + CPU |

Why it matters in 2026 interviews: it is a readable mid-2010s SoC. Every modern
flagship is this floorplan plus an NPU, a fatter GPU, LPDDR5/5X, and a 5G modem.

## Qualcomm Snapdragon 865 (SM8250)

The comparison phone in the video is the **Galaxy S20** (February 2020).

| Block | Spec |
| --- | --- |
| Process | TSMC 7 nm N7P |
| Transistors | ~10.3 billion |
| CPU | Kryo 585 = 1x Cortex-A77 2.84 GHz + 3x A77 2.42 GHz + 4x A55 1.80 GHz |
| Caches | Prime L2 512 KiB, Gold L2 256 KiB, Silver L2 128 KiB, shared L3 4 MiB |
| GPU | Adreno 650 |
| ISP | Spectra 480, dual 14-bit CV-ISP, 2 gigapixels/s |
| Camera | 200 MP stills, 8K30 / 4K120 video |
| AI | Hexagon 698 + tensor accelerator, ~15 TOPS |
| Memory | LPDDR5-5500 quad-channel, ~44 GB/s, up to 16 GiB |
| Modem | Discrete Snapdragon X55 5G (not on the application die) |
| Connectivity | FastConnect 6800: Wi-Fi 6, Bluetooth 5.1, 60 GHz |

Design note: Qualcomm split the 5G modem off-die to keep yield and thermals
manageable. 808 had an integrated LTE modem. Interviewers like this contrast.

## Apple A12 Bionic (APL1W81, Cyprus)

The SoC in the **iPhone XS / XS Max / XR** (2018). First high-volume consumer 7 nm chip.

| Block | Spec |
| --- | --- |
| Process | TSMC N7 |
| Transistors | 6.9 billion |
| Die | 83.27 mm² |
| CPU | 2x Vortex 2.49 GHz (7-wide OoO) + 4x Tempest ~1.6 GHz (3-wide) |
| Caches | P-core L1 128 KiB I + 128 KiB D, L2 8 MiB |
| GPU | 4-core Apple GPU (G11P), ~50 percent faster than A11 |
| NPU | 8-core Neural Engine, 5 TOPS INT8 |
| ISP | Petra ISP + Depth Engine + video processor |
| Security | Secure Enclave (SEP) |
| Memory | LPDDR4X package-on-package, 3-4 GiB, ~34 GB/s |
| ISA | ARMv8.3-A including pointer authentication |

A12 is the cleanest teaching floorplan of the three: Vortex, Tempest, four GPU
cores, NPU in the middle of the coherent fabric, ISP + depth + HEVC along the
bottom edge, Always-on MCU and SEP isolated.
