# Template Pack v1: Coming Soon

Everything you need to build your own solar beacon.

Not just schematics. Not just code. A complete, measured, tested implementation.

---

## What's included

### Altium Project (source of truth)
- Full schematic + all design decisions
- PCB layout (2-layer, manufacturing-ready)
- Gerber files + drill files + assembly notes
- BOM with alternates + quiescent current callouts for each part
- Design rules + electrical constraints documented

### Firmware Skeleton
- BLE packet structure + encoding/decoding
- Sensor read cycle (temp/humidity as default)
- Sleep/wake state machine
- Power-state measurements + current logging
- Everything needed to customize

### Bring-up & Validation
- Step-by-step bring-up checklist (cold start, diode switching, light behavior)
- Test points + measurement procedures
- How to validate your build actually works
- Known gotchas + how to debug them

### Porting Guide
- How to swap the sensor (different temp/humidity chip, or different sensor entirely)
- How to change wake interval without rewriting firmware
- How to change solar panel / supercap / coin-cell values
- How to adjust packet format (add fields, change encoding)
- Real examples (do X if you want Y)

### Measurement Records
- Your first baseline measurements (sleep, wake, TX, charge balance)
- Test methodology + equipment list
- How to reproduce measurements on your build
- Data sheets: what we measured and how

### Everything Versioned
- Git history showing what changed and why
- Design decisions documented at each revision
- "What went wrong and how we fixed it"

---

## Who this is for

**Engineers building low-power IoT products:**
You get 4–6 months of measured design work, not theories. Copy, modify, ship.

**Students in embedded systems courses:**
Real power-path design. Real measurements. Real tradeoffs documented.

**Hardware teams optimizing for battery/solar:**
Packet format, measurement methodology, and firmware patterns you can adapt.

---

## What you can do with it

- Build 1, 10, or 100 units
- Modify the design (swap sensors, change intervals, revise power-path)
- Use the firmware as a foundation for your own BLE product
- Adapt the measurement methodology for your own hardware
- **One purchase, unlimited use**

---

## Pricing

**Template Pack v1: $99 (one-time)**

Includes everything above. One purchase, lifetime access.

---

## Timeline

**Locked (in progress):**
- [x] Beacon architecture + block diagram
- [x] Packet format v1 (LOCKED)
- [x] Measurement methodology (LOCKED)
- [ ] First baseline measurements (target: Feb)
- [ ] Hardware bring-up complete (target: Feb)
- [ ] Template Pack v1 ready (target: March)

**Launch: Early March 2026**

---

## Get notified when it's ready

No spam. One email when it launches.

[Join the waitlist](https://nodifyr.io/waitlist){ .md-button .md-button--primary }

Or email: `kyle@nodifyr.io`

---

## FAQ

**Can I use this commercially?**
Yes. Build products, sell them, whatever. One-time $99 purchase covers it.

**What if I want support?**
Direct email support included for the first month after purchase.

**Will the design change after I buy?**
The packet format and measurement methodology are locked. Everything else (schematic, firmware, layout) will improve over time. You get all updates for free.

**Can I share this with my team?**
No. One purchase per person/organization. But you can collaborate however you want internally.

**What if I find a bug?**
Report it, get updates. You're supporting the development of better tools.

---

## Why this price?

$99 is:
- Cheap enough that buying is the obvious choice vs. trying to reverse-engineer it
- High enough that it's real value, not giving away your work
- Low enough that it's accessible to students and early-stage teams
- Simple (no tiers, no licenses, no complexity)

You're paying for 4–6 months of measured design work, packaged so you don't have to redo it.
