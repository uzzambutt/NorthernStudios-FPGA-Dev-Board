# NorthernStudios FPGA Dev Board

This repository contains the hardware design files for the **NorthernStudios FPGA Dev Board**, designed using **KiCad**.

## 📁 Repository Structure

The project is organized as follows:

```
├── datasheets/             # PDF datasheets for the components used
├── docs/                   # Schematics (PDF), 3D renders, and pinout diagrams
└── hardware/               # KiCad design files
    ├── libraries/          # Custom project-specific libraries
    │   ├── 3d_models/      # Custom 3D component models (.step, .wrl)
    │   ├── footprints/     # Custom footprint libraries (.pretty)
    │   └── symbols/        # Custom schematic symbols (.kicad_sym)
    ├── [project].kicad_pro # KiCad project file (create when starting)
    ├── [project].kicad_sch # KiCad schematic file
    └── [project].kicad_pcb # KiCad PCB layout file
```

---

## 🛠️ Getting Started in KiCad

1. **Clone the repository**:
   ```bash
   git clone https://github.com/uzzambutt/NorthernStudios-FPGA-Dev-Board.git
   ```
2. **Open the Project**:
   * Open KiCad.
   * Go to **File > Open Project...** and select or create the project file inside the `hardware/` directory.
3. **Configure Custom Libraries (if applicable)**:
   * **Schematic Symbols**: Go to *Preferences > Manage Symbol Libraries...*, add project-specific libraries under the *Project Specific Libraries* tab, pointing to `hardware/libraries/symbols/`.
   * **Footprints**: Go to *Preferences > Manage Footprint Libraries...*, add project-specific footpints under the *Project Specific Libraries* tab, pointing to `hardware/libraries/footprints/`.

---

## 📝 Hardware Specifications (Placeholder)

*Add details about your board here:*
- **FPGA Chip**: [e.g., Lattice iCE40, Gowin GW1N, Xilinx Artix-7]
- **Power Configuration**: [e.g., USB-C 5V input, LDOs for 3.3V, 2.5V, 1.2V]
- **Storage/Flash**: [e.g., SPI Flash for gateware storage]
- **Clocking**: [e.g., 12MHz, 25MHz external oscillator]
- **Peripherals**: [e.g., LEDs, Buttons, PMOD connectors, GPIO Headers]

---

## 🚀 Design Workflow Checklist

- [ ] **Schematic Capture**: Draw schematics in KiCad Schematic Editor. Run Electrical Rules Check (ERC) before proceeding.
- [ ] **Footprint Association**: Ensure all schematic components have footprints assigned.
- [ ] **PCB Layout**: Place and route components in KiCad PCB Editor.
- [ ] **DRC (Design Rule Check)**: Set up design rules matching your fab house capabilities and run DRC. Fix all errors and warnings.
- [ ] **Gerber Generation**: Export Gerbers and Drill files to a manufacturing folder when ready for production.
