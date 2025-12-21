# 2025-12-20 — Rev A Schematic Checkpoint (ESP32-S3 Dev Board)

This entry marks the first major checkpoint for **Revision A** of the Nodifyr ESP32-S3 development board.

The goal of this revision is to establish a starting point for continued development with the ESP32-S3 chip.

---

## Current Status

### Completed

- Core **power architecture**:
  - USB-C 5 V input
  - Single-cell Li-Po support
  - 3.3 V regulation for system power
- **ESP32-S3-WROOM-N16R2** selected:
  - I chose this for its flash/RAM headroom (I figured I would want it to have a lot of flash since it's Nodifyr's first dev board)
- Base MCU **supporting circuitry completed**
  - Boot configuration
  - Reset / enable
  - Decoupling and bulk capacitance
- USB-C port fully wired on schematic for 5v RECIEVING (5.1kΩ on each CC line)
- **Bill of Materials (BOM)** populated
  - Manufacturer part numbers (MPNs)
  - LCSC part numbers for assembly
- Altium project structure established and committed

---

The [https://github.com/Bushido3403/nodifyr-hardware](`nodifyr-hardware`) repository currently contains:

- Altium Designer 26 **project file**
- **Schematic document**
- **BOM document**
- **Integrated libraries (IntLib)** for parts not available via the Altium Content Vault
- Exported **schematic PDF**

### Not Yet Included

- PCB document (no layout has begun)
- Output job files (dependent on PCB creation)

The design is still in an architectural phase.

---

## Design Decisions So Far

- **ESP32-S3 over ESP32-C3**
  The S3 was selected despite higher compute capability than strictly required. The additional GPIO, RAM, and flash provide breathing room for:

  - accessory experimentation
  - future firmware features
  - board reuse

- **Assembly-aware BOM from day one**  
  All components are selected with real assembly in mind (LCSC/JLCPCB part #'s and confirmed stock).

---

## TODOs

- Finalize **GPIO allocation and pin mapping**
- Define and standardize **external connectors**
  - screw terminals
  - waterproof multi-pin connectors
- Decide on:
  - debug header strategy
  - expansion interfaces
- Begin PCB layout once schematic stabilizes
- Add board bring-up and test planning docs