# USB PD Module

[![License: Apache](https://img.shields.io/badge/license-APACHE-brightgreen.svg?style=for-the-badge)](/LICENSE.md)

**Rev:** 4.0

A compact, configurable USB-C Power Delivery trigger module based on the CH221K, designed for safe and reliable high-voltage PD negotiation with controlled output enable.

![USB PD Module Rotating View](3d/usb-pd-module.gif)

## Features
- USB-C Power Delivery trigger based on CH221K
- Negotiates fixed PD voltages: 5V / 9V / 12V / 15V / 20V
- 5-position DIP switch voltage selection
- High-side P-MOSFET output gating (AO3407A)
- Output enabled only after successful PD negotiation
- Power Good (PG) LED indicator
- Large bulk output capacitor (4700 µF)
- Output bleed control
- Compact 2-layer PCB
- Mounting holes for enclosure integration

## Design Overview

### Controlled Output Enable

The output rail is gated using a high-side AO3407A P-channel MOSFET driven by the CH221K **PG (Power Good)** signal.

This ensures:
- No voltage is applied to the output until PD negotiation succeeds  
- Output bulk capacitor charges only after contract establishment  
- No unintended pre negotiation backfeed  

### VGS Protection

A gate clamp diode (1N4148W) protects the MOSFET against excessive negative VGS during high-voltage (20V) operation.

### PD Configuration

Voltage selection is handled via a resistor ladder and DIP switch connected to the CH221K configuration input.

### Signal Integrity

- Short, symmetric CC1/CC2 routing  
- ESD protection on CC lines  
- Local decoupling at the PD controller  
- Solid ground plane with stitched returns  

## Electrical Specifications

- **Input:** USB-C PD source  
- **Negotiated Output Voltages:** 5V, 9V, 12V, 15V, 20V  
- **Max Output Current:** Limited by USB-C source and MOSFET rating  
- **Output Capacitance:** 4700 µF bulk  

## Key Components

- **U1:** CH221K USB-C PD controller  
- **Q1:** AO3407A P-channel MOSFET (high-side switch)  
- **D3:** 1N4148W (VGS clamp diode)  
- **C1:** 4700 µF bulk output capacitor  
- **USB-C Connector:** 6-pin USB-C receptacle  
- **U2:** SPX1117M3 LDO regulator  
