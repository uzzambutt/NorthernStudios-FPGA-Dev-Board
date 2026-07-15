# NorthernStudios FPGA Dev Board

[![KiCad](https://img.shields.io/badge/KiCad-v9.0-blue?logo=kicad&logoColor=white)](https://kicad.org/)
[![OSHW](https://img.shields.io/badge/OSHW-Open%20Source%20Hardware-orange.svg)](https://www.oshwa.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Designed by Muhammad Uzzam Butt // Made for Macondo**

---

## Overview

This repository contains the hardware design files for the NorthernStudios FPGA Dev Board. The board is designed in KiCad v9.0 and is built around the Gowin GW1NSR-4C, a hybrid FPGA chip containing an embedded ARM Cortex-M3 microcontroller. 

The design features complete power management, a USB-to-UART bridging interface, on-board clocking, user-programmable peripherals, and dual 24-pin expansion headers breaking out all major GPIOs. It is optimized as a compact and low-cost development platform for mixed hardware-firmware and gateware projects.

![NorthernStudios FPGA Dev Board Thumbnail](Images/image.webp)

---

## Hardware Specifications

### FPGA Core
* FPGA Chip: Gowin GW1NSR-4C (specifically GW1NSR-4C_MG64P in an MBGA64 package)
* Embedded ARM Cortex-M3 hard core processor
* 4,608 Look-Up Tables (LUTs)
* 3,456 Flip-Flops (FFs)
* Embedded block SRAM and internal Flash memory

### Power Delivery
* Input Source: USB Type-C (+5V VBUS)
* Core Regulator: AP2112K-1.2 LDO (600mA) generating +1.2V for the FPGA core
* I/O and Peripheral Regulator: AP2112K-3.3 LDO (600mA) generating +3.3V for I/O banks, clocking, and UART bridge
* Decoupling: Optimized bypass capacitor networks (0.1uF and 10uF) on each power pin to ensure low-noise rails

### Interfaces and Connectivity
* USB Connector: USB 2.0 Type-C interface
* Serial Communication: CP2102N USB-to-UART bridge for programming and debug output
* Main Breakout: Dual 24-pin headers for breadboard compatibility, exposing FPGA I/Os, system power, and ground pins
* Accessory Port: 6-pin PMOD-style header for SPI, I2C, or UART hardware attachments

### Clocking and User Controls
* Clock Oscillator: SG-8002CE (24.0000 MHz) active crystal oscillator
* User Controls: Push buttons for system reset and user input
* Visual Indicators: Status and user-configurable LEDs
* Level Translation: BSS138 N-channel MOSFET circuit for voltage-level switching

---

## Repository Structure

```
├── Images/                 # Board renders and project documentation media
│   └── image.webp          # Top-view 3D render of the PCB
├── datasheets/             # Component datasheets and technical documentation
├── docs/                   # PDF schematics and board layer printouts
└── hardware/               # KiCad 9.0 project files
    ├── jlcpcb/             # Automatically generated manufacturing outputs
    │   ├── gerber/         # Individual 6-layer Gerber and Drill files
    │   └── production_files/ # Zipped Gerbers, BOM, and CPL files for assembly
    ├── libraries/          # Custom symbol, footprint, and 3D model libraries
    │   ├── 3d_models/      
    │   ├── footprints/     
    │   └── symbols/        
    ├── NS FPGA.kicad_pro   # KiCad project configuration file
    ├── NS FPGA.kicad_sch   # KiCad schematic file
    └── NS FPGA.kicad_pcb   # KiCad 6-layer PCB layout file
```

---

## Manufacturing and Assembly

The board layout is a 6-layer design optimized for standard manufacturing capabilities. Production-ready manufacturing files are located in the `hardware/jlcpcb/production_files/` directory, set up specifically for JLCPCB fabrication and automated SMT assembly.

* **Gerber Files**: A complete zip archive (`GERBER-NS FPGA.zip`) contains all 6 copper layers, solder masks, silkscreens, edge cuts, and NC drill files.
* **Bill of Materials (BOM)**: `BOM-NS FPGA.csv` includes LCSC part numbers pre-assigned to all SMD components to streamline the JLCPCB parts selection process.
* **Component Placement List (CPL)**: `CPL-NS FPGA.csv` contains the exact centroid coordinates and rotation angles for automated SMT pick-and-place machines.

---

## KiCad Setup

1. Open the project using KiCad v9.0 or later by selecting [NS FPGA.kicad_pro](file:///D:/NS%20FPGA/hardware/NS%20FPGA.kicad_pro).
2. The Gowin FPGA symbol is located in the local library file [gowin_fpga.lib](file:///D:/NS%20FPGA/gowin_fpga.lib). Make sure it is mapped correctly in your KiCad symbol library table if you plan to edit the schematics.

---

## License

This project is open-source hardware licensed under the [MIT License](LICENSE).

---

*Designed by Muhammad Uzzam Butt // Made for Macondo*
