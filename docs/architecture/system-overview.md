# System Overview

Nodifyr is a focused IoT product line built around **ultra-low-power hardware**, **energy harvesting**, and **measured results**.

Right now, that means two products:\n1. **Solar beacon (nRF54)** — the flagship\n2. **ESP32-S3 hub** — the gateway (ships later)

---

## Current focus: Solar beacon (flagship)

A palm-sized **solar + coin-cell** BLE sensor beacon that wakes, samples sensors, broadcasts a packet, and returns to deep sleep. Built around measured power and repeatable methods.

**Why this is the flagship:**
- It's differentiated (not \"yet another ESP32 dev board\")
- It matches the core strength: ultra-low-power + energy harvesting + power-path design
- It creates a high-value Template Pack (design files + firmware + bring-up guide)
- The scope is tight and finishable

**Stage A shipping list:**
- Free: architecture + measurements + energy budget + proof
- Paid: Template Pack v1 (Altium project + firmware skeleton + bring-up checklist + porting guide)

[Read more: Solar Beacon v1 Overview](../projects/solar-beacon-v1/overview.md)

---

## Later: ESP32-S3 hub (gateway)

A mains-powered receiver/forwarder that bridges BLE beacons to Wi-Fi. Clean power-path design with USB-C charging and backup battery.

**Why this is later:**
- \"ESP32 dev board with charging\" is crowded territory
- It's useful, but not the differentiator
- It makes more sense as the **second product** after the beacon ships

**Stage B shipping list:**
- Free: clean schematic + design notes + measured quiescent currents
- Optional paid: \"Gateway Pack\" (BLE receiver + Wi-Fi forwarder) if it makes sense after beacon v1 sells

---

## Staged approach (cloud comes later)

**Stage A (now): BLE beacon + local receiver**
- Beacon advertises packets
- Receiver is phone (generic BLE scanner) or simple hub
- Output is local: logs, CSV, simple UI

**Stage B (later): BLE → Wi-Fi → somewhere dumb**
- Hub forwards to: MQTT / webhook / Home Assistant / basic endpoint
- Still not \"Nodifyr Cloud,\" just a bridge

**Stage C (much later): dashboards/accounts/cloud**
- Only if there's paying demand
- Only after beacon + hub are shipped and selling

---

## Design principles (what guides this project)

**Measured, not assumed.**
If it's not measured, it's labeled as TBD. Real sleep currents, real charge balance, real energy budgets.

**Repeatable methods.**
Document *how* you measured it, so others can validate or adapt. Test procedures, equipment, conditions.

**Tight scope, finishable products.**
BLE-only beacon with a defined duty cycle is finishable. Wi-Fi + cloud + dev board ecosystem is not (not in 10 months).

**Free proof, paid leverage.**
Architecture + measurements are free (the proof). Template Packs are paid (the leverage).

**Revenue + portfolio in 10 months.**
The goal is a shipped product that demonstrates skills *and* creates income. The beacon does both.

---

## What this is not (yet)

- Not a \"full IoT ecosystem\" (at least not for the next 10 months)
- Not Nodifyr Cloud™ with dashboards and accounts (maybe later, not now)
- Not a startup (but it could fund itself)

This is a focused product line with a clear flagship and a realistic shipping plan.