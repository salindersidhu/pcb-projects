# Stereo Speaker Amp

[![License: Apache](https://img.shields.io/badge/license-APACHE-brightgreen.svg?style=for-the-badge)](/LICENSE.md)

**Rev:** 3.0

This is a compact, full range stereo amplifier PCB based on the TDA2822M audio power amplifier IC. The design provides clean, low noise stereo amplification with onboard analog volume control and a standard 3.5mm auxiliary input.

![Stereo Amp Rotating View](3d/stereo-speaker-amp.gif)

## Features

- **Amplifier IC:** TDA2822M (dual-channel audio power amplifier)
- **Configuration:** Stereo (non-bridge mode)
- **Volume Control:** 50kΩ dual-gang potentiometer
- **Input:** 3.5mm TRS auxiliary (line-level)
- **Output:** AC-coupled speaker outputs
- **Rated Output Power:**  
  - ~2–3 W per channel into 8Ω @ 12V (typical conditions)
- **Power Supply:** 12–15V DC (single supply)
- **PCB:** 2-layer layout with solid ground plane
- **Stability Features:**  
  - Output Zobel networks  
  - Input bias network  
  - Local supply decoupling  
- **Mounting:** Integrated mounting holes for enclosure installation

## Design Overview

### Power Input

- Single-supply operation (12–15V DC recommended)
- 470µF bulk reservoir capacitor
- 0.1µF ceramic decoupling capacitor placed near IC VCC pin
- Solid ground plane for low impedance return paths

### Input Stage

- 3.5mm auxiliary input (line-level)
- 2.2µF AC coupling capacitors
- 50kΩ dual-gang potentiometer for volume control
- 18kΩ input bias resistors to ground

### Amplifier Stage

- TDA2822M configured in stereo mode
- 100µF feedback capacitors for AC gain setting and low-frequency response control
- Proper input biasing and decoupling to minimize noise

### Output Stage

- 2200µF output coupling capacitors (per channel)
- Zobel network (4.7Ω + 0.1µF) per channel for stability
- Designed for 8Ω speaker loads

## Layout Notes

- High frequency decoupling capacitor placed directly near the IC VCC pin.
- Bulk reservoir capacitor located close to the amplifier stage.
- Ground plane used for low impedance return.
- Short, direct routing of input and feedback paths.
- Ground stitching vias used to reinforce return paths.

## Use Cases

- Desktop speaker systems  
- DIY Bluetooth speaker builds (with external BT module)  
- Small embedded audio projects  
- Educational analog amplifier projects  
