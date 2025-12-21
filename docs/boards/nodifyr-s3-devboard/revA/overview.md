# Nodifyr S3 Dev Board — Rev A Overview

Revision A of the Nodifyr S3 Dev Board is the first hardware iteration intended to establish a flexible, well-documented development board for the Nodifyr ecosystem.

I decided that this revision should prioritize architectural correctness and expandability over optimization or miniaturization.

---

## Purpose of Rev A

Rev A exists to:

- validate core power and system architecture
- provide a stable ESP32-S3-based development platform
- support experimentation with external modules and accessories
- serve as a documented reference for future revisions

It is not intended to be a finalized or production-optimized board.

---

## Key Characteristics

- **MCU:** ESP32-S3-WROOM-N16R2 - Selected for flash and RAM headroom, GPIO availability, and long-term flexibility.

- **Power Inputs:**  
    - USB-C (5 V)
    - Single-cell Li-Po battery

- **System Voltage:**  
  - 3.3 V regulated rail for MCU and peripherals

- **Design Focus:**  
  - modular interfaces  
  - clear power domains  
  - assembly-aware component selection

---

## Current Status

- Schematics in progress
- PCB layout has not yet begun
- Interfaces and GPIO allocation still evolving

Documentation for each subsystem will evolve in the sections below.

---

## Notes

This revision is expected to change as design assumptions are validated or disproven.  
All updates and decisions are tracked in the devlog and ADRs.