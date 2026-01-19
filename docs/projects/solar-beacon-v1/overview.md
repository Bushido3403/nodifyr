# Solar Beacon v1 (nRF54)

A palm-sized **BLE sensor beacon** powered by **solar + storage** with a **coin-cell backup**. It wakes on a schedule, samples one sensor, broadcasts a compact packet, then returns to deep sleep.

Built on **measured power** and **repeatable methods**, not vibes.

---

## The mantra

**One sensor + one payload + one measurement path.**

Everything optional is DNP by default. This is how you finish on time.

---

## Locked pieces (don't change these)

These two things prevent rewrites later. Lock them early.

**[Packet spec](packet-spec.md)** — Versioned BLE payload format
- Sensor readings
- Battery/energy status
- Timestamp (or not)
- Reserve bytes for future sensors

Once shipped, this stays stable. New fields go in reserved slots.

**[Measurement methodology](measurement-plan.md)** — How to measure
- Sleep current (equipment, settings, procedure)
- Wake energy (time + current profile)
- Charge balance (solar input, average consumption)
- Cold start behavior

Document the method once. Then ship results continuously.

---

## Everything else evolves

Part numbers → change
Power-path details → evolve
Firmware → iterate
Layout → revise

But packet format + measurement format stay stable.

---

## v1 scope

### Hardware
**Core**
- nRF54 + BLE antenna
- Solar input → supercap + coin-cell backup (ideal diode OR-ing)
- **One sensor** populated by default (temp/humidity)
- Current measurement headers (for bring-up)

**Optional (DNP by default)**
- Light sensor (skip for v1)
- Battery voltage measurement (skip for v1)
- Anything else (skip for v1)

### Firmware
- Simple cycle: sleep → wake → sample → encode → advertise → sleep
- One sensor read per cycle
- Configurable interval + one sensor enable flag
- Power states documented with measured numbers

### What's NOT v1
- Nodifyr Cloud™
- Custom mobile app
- Multi-sensor expansion
- Wireless config or OTA updates
- Anything that adds debug surface area

---

## What ships

### Free (proof)
- Architecture + block diagram
- Power-path explanation + design rationale
- **[Packet spec](packet-spec.md)** (locked)
- **[Measurement methodology](measurement-plan.md)** (locked)
- Real measured numbers (sleep, wake, TX, charge balance)
- Design decisions + tradeoffs
- "What went wrong" logs and revisions

### Paid — Template Pack v1
- Altium project + manufacturing outputs
- BOM with alternates + quiescent-current callouts
- Bring-up + validation checklist
- Firmware skeleton (packet + sensor + sleep cycle)
- Porting guide (swap sensor / change interval / change panel)

---

## Status

- [x] Strategic direction locked
- [x] BLE PoC validated
- [ ] Packet spec v1 finalized (LOCKED)
- [ ] Measurement methodology documented (LOCKED)
- [ ] First baseline numbers captured
- [ ] Hardware bring-up complete
- [ ] Template Pack v1 ready

Once these are locked, everything else is iteration.

---

## v1 hardware scope
**Core**
- nRF54 + BLE antenna solution
- Solar input → storage (supercap) + coin-cell backup OR-ing (ideal diode approach)
- Temp + humidity sensor footprint populated by default
- Current measurement provision (headers/test points) built-in

**Optional (DNP by default)**
- Storage/battery voltage measurement (divider that is **gated**)
- Light measurement (prefer gated divider or digital ALS)

---

## v1 firmware scope
- Simple cycle: **sleep → wake → sample → encode → advertise → sleep**
- Versioned packet format documented early
- Configurable interval + sensor enable flags
- Power behavior documented with measured numbers (not "should be low")

---

## What's free vs paid
**Free (docs + proof)**
- Architecture, power-path explanation, packet spec
- Measurement methodology + results
- "What went wrong" logs and revisions

**Paid (Template Pack v1)**
- Altium project files + manufacturing outputs
- BOM with alternates + quiescent-current callouts
- Bring-up checklist + validation plan
- Firmware skeleton (packet + sensor + sleep cycle)
- Porting guide (swap sensor / change interval / change energy stack)

---

## Status (today)
- Schematics: mostly complete (needs organization + review)
- BLE PoC: validated on a simple nRF board (flash + advertise confirmed)
- Docs: starting now (structure + plan + packet spec)
- Open questions: parts selection + energy storage behavior under real light

---

## Next milestones (non-detailed)
- Publish measurement plan + initial "targets"
- Finalize packet format (v1)
- Capture first baseline power numbers (even if "bad")
- Package Template Pack v1 outline (contents + deliverables)
