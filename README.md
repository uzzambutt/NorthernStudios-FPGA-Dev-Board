# NorthernStudios FPGA Dev Board

[![KiCad](https://img.shields.io/badge/KiCad-v9.0-blue?logo=kicad&logoColor=white)](https://kicad.org/)
[![OSHW](https://img.shields.io/badge/OSHW-Open%20Source%20Hardware-orange.svg)](https://www.oshwa.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Designed by Muhammad Uzzam Butt // Made for Macondo**

---

## Overview
This FPGA Devboard is designed in KiCad v9.0 and is built around the Gowin GW1NSR-4C, a hybrid FPGA chip containing an embedded ARM Cortex-M3 microcontroller. 

![NorthernStudios FPGA Dev Board Thumbnail](Images/image.webp)

---

## Hardware Specifications

### FPGA Core
* FPGA Chip: Gowin GW1NSR-4C (specifically GW1NSR-4C_MG64P in an MBGA64 package)
* Embedded ARM Cortex-M3 hard core processor
* 4,608 Look Up Tables (LUTs)
* 3,456 Flip Flops (FFs)
* Embedded block SRAM and internal Flash memory

### Power Delivery
* Input Source: USB Type-C (+5V VBUS)
* Core Regulator: AP2112K 1.2 LDO (600mA) generating +1.2V for the FPGA core
* I/O and Peripheral Regulator: AP2112K-3.3 LDO (600mA) generating +3.3V for I/O banks, clocking, and UART bridge
* Decoupling: Optimized bypass capacitor networks (0.1uF and 10uF) on each power pin to ensure low-noise rails

### Interfaces and Connectivity
* USB Connector: USB 2.0 Type-C interface
* Serial Communication: CP2102N USB-to-UART bridge for programming and debug output
* Main Breakout: Dual 24-pin headers for breadboard compatibility, exposing FPGA I/Os, system power, and ground pins
* Accessory Port: 6-pin PMOD style header for SPI, I2C, or UART hardware attachments

### Clocking and User Controls
* Clock Oscillator: SG-8002CE (24.0000 MHz) active crystal oscillator
* User Controls: Push buttons for system reset and user input
* Visual Indicators: Status and user-configurable LEDs
* Level Translation: BSS138 N-channel MOSFET circuit for voltage-level switching

---

## Bill of Materials (BOM)

A complete list of components required to assemble the dev board is detailed in the table below (sourced from [bom.csv](file:///D:/NS%20FPGA/hardware/jlcpcb/production_files/bom.csv)):

| Comment | Designator | Footprint | LCSC | Quantity |
| :--- | :--- | :--- | :--- | :--- |
| 0.1uF | C1, C4, C6 | C_0402_1005Metric | C141382 | 3 |
| 0.1uF | C11, C12, C13, C14, C15, C16, C17 | C_0201_0603Metric | C66938 | 7 |
| 10k | R12, R3, R9 | R_0402_1005Metric | C25725 | 3 |
| 10uF | C10, C7, C8, C9 | C_0402_1005Metric | C15525 | 4 |
| 1k | R10 | R_0201_0603Metric | C131396 | 1 |
| 22.1k | R4 | R_0201_0603Metric | C423662 | 1 |
| 330 | R11 | R_0201_0603Metric | C274872 | 1 |
| 4.7k | R7, R8 | R_0201_0603Metric | C142008 | 2 |
| 4.7uF | C2, C3, C5 | C_0402_1005Metric | C23733 | 3 |
| 47.5k | R5 | R_0201_0603Metric | C166179 | 1 |
| 5.1k | R1, R2 | R_0402_1005Metric | C25905 | 2 |
| AP2112K-1.2 | U4 | SOT-23-5 | C49451994 | 1 |
| AP2112K-3.3 | U3 | SOT-23-5 | C3021085 | 1 |
| BSS138 | Q1 | SOT-23 | C52895 | 1 |
| CP2102N-Axx-xQFN24 | U2 | QFN-24-1EP_4x4mm_P0.5mm_EP2.6x2.6mm | C969151 | 1 |
| LED | D1, D2 | LED_0201_0603Metric | C3646922 | 2 |
| R22 | R6 | R_0201_0603Metric | C142011 | 1 |
| SG-8002CE(24.0000M) | Y1 | Oscillator_SMD_SeikoEpson_SG8002CE-4Pin_3.2x2.5mm | C390322 | 1 |
| SW_Push | SW1 | SW_SPST_EVQP2_ShortPushTravel_H2.1mm | C2915174 | 1 |
| USB_C_Receptacle_USB2.0_14P | J1 | USB_C_Receptacle_HCTL_HC-TYPE-C-16P-01A | C165948 | 1 |
| GW1NSR-4C-MG64P | U1 | BGA-64_8x8_4.2x4.2mm | Gowin GW1NSR-4C-MG64P | 1 |
| TestPoint | TP4 | TestPoint_Pad_D1.0mm | | 1 |
| TestPoint | TP3 | TestPoint_Pad_D1.0mm | | 1 |
| TestPoint | TP2 | TestPoint_Pad_D1.0mm | | 1 |
| TestPoint | TP1 | TestPoint_Pad_D1.0mm | | 1 |
| Jtag PIN | J4 | PinHeader_1x06_P2.54mm_Vertical | | 1 |
| Conn_01x24_Pin | J3 | PinHeader_1x24_P2.54mm_Vertical | | 1 |
| Conn_01x24_Pin | J2 | PinHeader_1x24_P2.54mm_Vertical | | 1 |

---

## KiCad Setup

1. Open the project using KiCad v9.0 or later by selecting [NS FPGA.kicad_pro](file:///D:/NS%20FPGA/hardware/NS%20FPGA.kicad_pro).
2. The Gowin FPGA symbol is located in the local library file [gowin_fpga.lib](file:///D:/NS%20FPGA/gowin_fpga.lib). Make sure it is mapped correctly in your KiCad symbol library table if you plan to edit the schematics.

---

## License

This project is open-source hardware licensed under the [MIT License](LICENSE).

---

*Designed by Muhammad Uzzam Butt // Made for Macondo*
