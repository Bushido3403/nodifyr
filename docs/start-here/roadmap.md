# Roadmap

This is the plan. Not promises, not dreams — just the sequence of work.

---

## The commitment (next 8–12 weeks)

**Ship the nRF solar beacon as v1.**

That means:
- Finalized schematic + layout
- Measured power numbers (sleep, wake, TX, charge balance)
- Documented packet format
- Bring-up checklist that works
- Template Pack v1 ready to sell

The ESP32-S3 hub stays in the plan as the gateway/receiver, but it does **not** become a parallel project until beacon v1 exists.

---

## Stage A: BLE beacon + local receiver (now)

This is the tight, finishable scope.

**What gets built:**
- nRF54 solar beacon (flagship hardware)
- Beacon advertises or sends BLE packets
- Receiver is a phone (generic BLE scanner) or simple hub (ESP32/nRF on mains power)
- Output is local: logs, simple UI, or even a CSV

**What gets shipped (public):**
- System overview + block diagram (solar + supercap + coin cell + ideal diodes)
- Measurement methodology (how you measure nanoamp/µA sleep, charge current, cold start)
- "Energy budget" page (duty cycle → average current → viability)
- Proof posts: sleep current, advertising interval tests, charge balance behavior

**What gets shipped (paid Template Pack v1):**
- Altium project + BOM/alternates (with quiescent currents called out)
- Firmware skeleton (BLE packet structure, sensor read cadence, power states)
- Bring-up + validation checklist (cold start, diode switching, low-light behavior)
- Porting guide (swap sensor / change interval / change panel / change storage)

**What does NOT get built:**
- Nodifyr Cloud™
- Custom mobile app
- Multi-sensor expansion (beyond bring-up sensors)
- Dashboards or accounts

---

## Stage B: Minimal gateway (later, after beacon ships)

This is the **BLE → Wi-Fi → somewhere dumb** bridge.

**What gets built:**
- ESP32-S3 hub (mains-powered, receives BLE packets)
- Forwards to: MQTT broker / webhook / Home Assistant / a basic endpoint
- Still not "Nodifyr Cloud," just a bridge people can use

**What gets shipped:**
- Clean schematic + design notes (charging/power-path, backup battery behavior)
- Gateway firmware (BLE receiver + Wi-Fi forwarder)
- Sample forwarding script or config

**Optional paid add-on:**
- "Gateway Pack" (BLE receiver + Wi-Fi forwarder) or "ESP32 low-power reality check" pack
- Only if it makes sense after beacon v1 is selling

---

## Stage C: Cloud (much later, only if pulled by demand)

This is dashboards, accounts, multi-tenant cloud.

**Only build this if:**
- You have paying customers asking for it
- Beacon v1 + gateway are shipped and stable
- You have time/resources to maintain it

**What to do now (even though cloud is later):**
- Define the data contract: payload format, timestamps, sensor IDs, battery/energy status
- Design the beacon + gateway so cloud work is **incremental**, not a rewrite

---

## Decision rule (when you're torn)

Choose the one that best satisfies all three:

1. **Unique** (people can't get it everywhere)
2. **Finishable** (you can ship v1 during a heavy semester)
3. **Sellable as files + process** (template pack makes sense)

That's the solar beacon.

The ESP32-S3 board is valuable — but it's better as:
- Your hub reference
- A later release
- Or a free "credibility magnet"

---

## Current status (as of Jan 2026)

- [x] Strategic direction set (beacon is flagship)
- [x] BLE PoC validated on nRF board
- [ ] Beacon schematic finalized
- [ ] First baseline power measurements captured
- [ ] Packet format v1 published
- [ ] Measurement plan documented
- [ ] Template Pack v1 outline defined
- [ ] Beacon v1 hardware ordered
- [ ] Beacon v1 bring-up complete
- [ ] Template Pack v1 packaged and ready to sell

Once beacon v1 ships, we move to Stage B (gateway).
