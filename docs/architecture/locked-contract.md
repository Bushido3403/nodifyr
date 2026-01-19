# Locked Contract: Never Rewrite

Two things are worth locking **before you ship**. Changing these later means rebuilding everything.

Everything else can evolve. Part numbers change. Layouts change. Firmware iterates. But these two stay stable.

---

## 1. Packet Spec (BLE payload format)

**Why it matters:**
Once customers have hardware, the packet format is *permanent*. Change it and their hardware breaks. Change it again and you've rewritten firmware, cloud, logging, analysis, everything.

**What to lock:**
- Sensor readings (bit width, order, encoding)
- Battery/energy status (voltage, charge state, solar status)
- Timestamp (if included)
- Versioning (so you can extend without breaking old devices)
- **Reserve bytes** for future sensors (so you don't need to change the whole spec)

**Once locked:**
New features go in reserved slots. Old devices keep working.

See: [Beacon Packet Spec](../projects/solar-beacon-v1/packet-spec.md)

---

## 2. Measurement Methodology (repeatable test procedure)

**Why it matters:**
If your measurement method changes, all your historical data becomes incomparable. "Sleep current was 50 nA" means nothing if you change test equipment, settings, or conditions.

**What to lock:**
- Test equipment (oscilloscope, power supply, current meter make/model)
- Measurement conditions (temperature, voltage, light level)
- Procedure (how many samples, averaging, duration)
- Data format (timestamps, CSV columns, precision)
- What constitutes "valid" data (noise thresholds, outlier removal)

**Once locked:**
You can measure continuously. New data is always comparable to old data. You build a track record.

See: [Beacon Measurement Plan](../projects/solar-beacon-v1/measurement-plan.md)

---

## Everything else evolves

| Can change | Reason |
|-----------|--------|
| Part numbers | Sourcing, obsolescence |
| Power-path topology | Better trade-offs discovered |
| Firmware logic | Bug fixes, optimization |
| PCB layout | Manufacturing feedback |
| Schematic detail | Testing reveals issues |
| Sensor type | Different use case, DNP default |

These things *will* change. Don't freeze them early.

---

## How this prevents rewrites

**Scenario: You lock the packet spec and measurement method**

Month 1: Ship beacon v1 with measurements
Month 2: Find a better power-path topology → change schematic, firmware still works
Month 3: Part becomes obsolete → swap in BOM, firmware still works
Month 4: Want to add optional light sensor → firmware reads it, includes in reserved bytes
Month 5: Want to measure something new → add to optional fields, old devices keep working

You ship *continuously* without invalidating anything.

**Scenario: You don't lock the packet spec**

Month 1: Ship beacon v1
Month 2: "We should add light sensor" → rewrite packet format → all old devices broken
Month 3: "Actually voltage too" → rewrite again → everything broken again
Month 5: "Let's make it cloud-compatible" → cloud format doesn't match old data → rewrite entire logging system

You rewrite constantly and ship nothing.

---

## For the Template Pack

Once the packet spec and measurement method are locked:

- Every new batch of hardware uses the same packet format
- Every measurement uses the same methodology
- Customers can build with confidence (format won't change under them)
- You can add features without touching "locked" pieces

The pack becomes **truly** reusable.
