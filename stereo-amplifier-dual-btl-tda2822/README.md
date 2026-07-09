# Stereo Amplifier Dual BTL TDA2822

[![License: Apache](https://img.shields.io/badge/license-APACHE-brightgreen.svg?style=for-the-badge)](/LICENSE.md)

**Rev:** 2.0

This project is a compact stereo audio amplifier PCB based on two TDA2822 audio power amplifier ICs. Each IC is configured in bridged-tied-load (BTL) mode to drive a single speaker, providing significantly higher output power than the standard stereo configuration. The design includes an onboard analog volume control, a standard 3.5 mm auxiliary input, and differential bridge outputs for left and right speakers.

![Stereo Amplifier Dual BTL TDA2822 Rotating View](stereo-amplifier-dual-btl-tda2822.gif)

## Features

- **Amplifier ICs:** Dual TDA2822 audio power amplifiers
- **Configuration:** Stereo (BTL mode, one IC per channel)
- **Volume Control:** 50 kΩ dual-gang potentiometer
- **Input:** 3.5 mm TRS auxiliary (line-level)
- **Output:** Differential BTL speaker outputs
- **Power Supply:** 6–15 V DC (single supply)
- **PCB:** Compact 2-layer PCB with solid ground plane
- **Mixed Technology Design:**
  - SMD resistors and ceramic capacitors
  - Through-hole electrolytic and film capacitors
- **Improved Power Filtering:**
  - 470 µF bulk reservoir capacitor per amplifier
  - Local 0.1 µF ceramic decoupling
- **Stability Features:**
  - Output Zobel networks
  - Bridge-mode compensation network
  - Input bias network
  - Local supply decoupling
- **Mounting:** Four integrated mounting holes

## Design Overview

### Power Input

- Single-supply operation (6–15 V DC recommended)
- 470 µF bulk reservoir capacitor located beside each amplifier
- 0.1 µF ceramic decoupling capacitor placed directly adjacent to each IC VCC pin
- Wide VCC routing for reduced voltage drop
- Solid ground plane with multiple stitching vias for low-impedance return paths

### Input Stage

- 3.5 mm auxiliary input (line-level)
- 4.7 µF AC coupling capacitors
- 50 kΩ dual-gang logarithmic potentiometer for volume control
- Input bias network for stable DC operating point

### Amplifier Stage

- Two TDA2822 ICs configured in bridged-tied-load (BTL) mode
- One IC dedicated to each audio channel
- 22 µF bridge coupling capacitors for improved low-frequency performance
- Local compensation network for stable bridge operation

### Output Stage

- Differential bridge outputs
- Individual Zobel network (4.7 Ω + 0.1 µF film capacitor) on each amplifier output
- Designed for 8 Ω speaker loads

> Since this is a BTL amplifier, neither speaker terminal is connected to ground. The speaker must be connected only between the two output terminals of each channel.

## PCB Layout

The PCB has been optimized for low noise and stable operation:

- Symmetrical left/right amplifier layout
- Short feedback paths
- Wide power traces
- Local decoupling located immediately adjacent to each amplifier
- Continuous ground plane
- Ground stitching vias throughout the power section
- Short differential speaker output routing

## Use Cases

- Desktop speaker amplifiers
- DIY Bluetooth speaker projects (with an external Bluetooth module)
- Retro gaming and arcade audio
- Portable speaker projects
- Educational analog electronics projects
- General-purpose stereo audio amplification
