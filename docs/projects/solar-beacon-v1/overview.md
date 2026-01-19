# Solar Beacon v1 (nRF54)

A palm-sized **BLE sensor beacon** powered by **solar + storage** with a **coin-cell backup**. It wakes on a schedule, samples one or two sensors, broadcasts a compact packet, then returns to deep sleep.

This project is designed around **measured power** and **repeatable methods**, not vibes.

---

## Why this is the flagship

This is the **differentiated product**. Here's why it's the right choice for revenue + portfolio in 10 months:

**It's more differentiated.**
"ESP32 dev board with Li-ion + USB-C charging" is useful, but it's also crowded. People compare you to a million existing boards. "Solar-powered BLE beacon with measured nanoamp sleep currents and real energy-harvesting validation" is rare and sticky.

**It matches the strongest edge.**
Ultra-low-power architecture + power-path switching + energy harvesting + quiescent current optimization. That's the stuff engineers will follow and pay for. This product showcases those skills.

**It naturally creates a paid Template Pack.**
Power-path design + harvesting strategy + sleep current choices + test procedure = high-value implementation assets. People will pay for this.

**The scope is tight.**
BLE-only beacon with a defined duty cycle is finishable during a heavy semester. Wi-Fi + cloud + dev board ecosystem is not.

---

## Goals (v1)
- BLE-only beacon (advertising burst, no app required to prove functionality)
- Solar input with storage (supercap) and coin-cell backup
- Timed wake from deep sleep
- Real measurements: sleep current, wake energy, TX energy, charge balance
- Template Pack v1 that someone else can actually build and modify

## Non-goals (v1)
- Nodifyr Cloud™ (dashboards, accounts, databases)
- Custom mobile app (phone can be generic BLE scanner/logger)
- Multi-sensor expansion beyond bring-up set
- Multiple beacon MCU variants (nRF52 "budget beacon" is later, not now)

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
