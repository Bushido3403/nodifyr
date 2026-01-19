# What is Nodifyr?

Nodifyr is an **open-source IoT project** focused on ultra-low-power hardware, energy harvesting, and power-path design done right.

I'm building real products with measured results, transparent documentation, and implementation packs you can actually use. Not vaporware. Not "coming soon." Actual hardware with real numbers.

This project is being developed in public and documented as it grows.

---

## The flagship (right now)

**A palm-sized solar + coin-cell BLE sensor beacon that actually balances energy, with real measurements and a template pack.**

That's the one-sentence story I'm committing to for the next 6–10 months.

Why this product?

- **It's differentiated.** "ESP32 dev board with charging" is useful but crowded. Everyone has one. "Solar-powered BLE beacon with measured nanoamp sleep currents and real energy-harvesting validation" is rare.

- **It matches my strongest edge:** ultra-low-power architecture, power-path switching, quiescent current optimization, and energy harvesting. That's the stuff engineers will follow and pay for.

- **It creates a high-value template pack.** Power-path design + harvesting strategy + sleep current optimization + test procedure = implementation assets people will buy.

- **The scope is tight.** BLE-only beacon with a defined duty cycle is finishable. Wi-Fi + cloud + dev board ecosystem is not (not in 10 months).

---

## The motivation

A lot of IoT projects fail quietly for the same reasons:

- hardware is tightly coupled to one use case
- interfaces are undocumented or inconsistent
- firmware grows organically without structure
- revisions overwrite history instead of explaining it
- knowledge lives in people's heads instead of artifacts

Nodifyr exists to do it differently:
**Bring industry-level IoT hardware and firmware knowledge to the public, with measured proof and implementation leverage.**

---

## Ready to build?

**Template Pack v1** (Altium + firmware + validation checklist) launches **March 2026**.

$99 one-time. Or join the **Founders Program** for early access at $69.

[Get notified →](https://nodifyr.io/waitlist){ .md-button .md-button--primary } [Founders Program →](../founders-program.md){ .md-button }

---

## What Nodifyr is (and is not)

### Nodifyr *is*:

- a focused product line (flagship: solar BLE beacon, hub: ESP32-S3 gateway)
- measured, portfolio-grade hardware with real power numbers
- a documented design process, not just finished outputs
- free proof (architecture + measurements) + paid leverage (template packs)
- an experiment in building revenue + reputation from transparent engineering

### Nodifyr is *not*:

- a "full IoT ecosystem" (at least not for the next 10 months)
- Nodifyr Cloud™ with dashboards and accounts (maybe later, not now)
- a startup (but it could fund itself)

Some ideas will be wrong. Some designs will need revision.

Those outcomes are expected, and documented.

---

## Core ideas

While the implementation is evolving, Nodifyr is guided by a few consistent principles:

- **Measured, not assumed** - Real sleep currents, real charge balance, real energy budgets. If it's not measured, it's labeled as TBD.

- **Transparency** - Design decisions, tradeoffs, and mistakes are recorded rather than hidden.

- **Tight scope** - Ship finishable products. BLE-only beacon is finishable. Wi-Fi + cloud + ecosystem is not (not in 10 months).

- **Free proof, paid leverage** - Architecture + measurements are free. Template Packs are paid.

- **Real constraints** - Components are chosen with manufacturing, sourcing, and assembly in mind.

---

## How this project is structured

Nodifyr is split into multiple repositories and documentation sections:

- **[Hardware](https://github.com/Bushido3403/nodifyr-hardware)** - Board designs, schematics, revisions, and electrical rules.

- **[Firmware](https://github.com/Bushido3403/nodifyr-firmware)** - Embedded code, power states, sensor logic, and BLE packet handling.

- **[Software](https://github.com/Bushido3403/nodifyr-software)** - Gateway code, forwarding logic (later: cloud endpoints, if needed).

- **Documentation (You are here!)** - Architecture, measurements, design decisions, energy budgets, and devlogs.

This documentation site is the **source of truth** tying all of that together.

**Current focus:** Solar beacon (Stage A). Hub/gateway comes later (Stage B).

---

## Why everything is documented

This site exists for a few reasons:

- to force clarity while designing
- to capture intent before it's forgotten
- to make future revisions easier
- to create a readable engineering narrative

My goal is not perfection, it's **a realistic way to develop**.

If something changes, the history of *why* should still exist.

---

## Who this is for

Nodifyr is for:

- **Engineers and students** interested in ultra-low-power design, energy harvesting, and power-path switching
- **Hardware developers** who want measured proof and implementation leverage (not just schematics)
- **Anyone curious** about how hardware projects actually evolve (transparent build process)
- **Businesses** looking to implement low-power IoT sensors with real energy budgets
- **Future me**, when today's decisions no longer feel obvious

If you care about nanoamp sleep currents, quiescent current optimization, and real energy-harvesting validation, this is for you.

---

## Current status

Nodifyr is in active development.

**Right now (Jan 2026):**

- Strategic direction set: **solar beacon is the flagship**
- BLE PoC validated on nRF board (flash + advertise confirmed)
- Beacon schematics in progress (needs finalization + review)
- Documentation structure live (you're reading it)
- Measurement plan being defined
- Template Pack v1 outline in progress

**Next 8–12 weeks:**

- Finalize beacon schematic + layout
- Capture first baseline power measurements
- Document packet format v1
- Package Template Pack v1
- Ship beacon v1

ESP32-S3 hub comes after beacon v1 ships.
- interfaces are being defined
- documentation is growing alongside the project

Nothing here should be treated as final.

---

## Where to go next

Check out the current board I'm working on!

- [S3 Dev Board - Rev A](https://docs.nodifyr.io/boards/nodifyr-s3-devboard/revA/overview/)
    - [Power Tree Flowchart](https://docs.nodifyr.io/boards/nodifyr-s3-devboard/revA/power-tree/)
    - [2025-12-20 Devlog](https://docs.nodifyr.io/devlog/2025-12-20-revA-schematic-checkpoint/)

This project will change.  
The documentation will change with it :)