# Repo Map

Lost? Here's where everything lives.

---

## Start here

- **[What is Nodifyr?](what-is-nodifyr.md)** — The motivation, vision, and core ideas
- **[Roadmap](roadmap.md)** — The staged plan (Stage A: beacon, Stage B: hub, Stage C: cloud later)
- **[Docs Philosophy](../about/philosophy.md)** — Measured numbers, not vibes

---

## Architecture

- **[System Overview](../architecture/system-overview.md)** — The big picture: flagship beacon + gateway hub
- **[Hub vs. Node](../architecture/hub-vs-node.md)** — Why beacon is flagship, hub comes later

---

## Flagship: Solar Beacon v1

- **[Overview](../projects/solar-beacon-v1/overview.md)** — Goals, scope, and why this is the differentiated product
- **[Power Path](../projects/solar-beacon-v1/power-path.md)** — Solar + supercap + coin-cell backup design
- **[Packet Spec](../projects/solar-beacon-v1/packet-spec.md)** — BLE data format
- **[Measurement Plan](../projects/solar-beacon-v1/measurement-plan.md)** — How to measure sleep current, charge balance, etc.

---

## Boards (hardware details)

- **[Nodifyr S3 DevBoard](../boards/nodifyr-s3-devboard/revA/overview.md)** — ESP32-S3 hub/gateway (ships later)

---

## Engineering decisions

- **[ADR-0001: ESP32-S3 Choice](../engineering/decisions/adr-0001-esp32-s3-choice.md)** — Why ESP32-S3 for the hub

---

## Interfaces (design rules)

- **[Module Port Spec](../interfaces/module-port-spec.md)** — Connector standards (future expansion)
- **[Electrical Rules](../interfaces/electrical-rules.md)** — Voltage levels, protection, etc.
- **[Accessory ID Spec](../interfaces/accessory-id-spec.md)** — How accessories identify themselves

---

## Testing

- **[Bring-up Checklist](../testing/bringup-checklist.md)** — How to validate new hardware
- **[Measurements](../testing/measurements.md)** — Recorded data (power, charge, etc.)

---

## Devlog (progress updates)

- **[2025-12-20: Rev A Schematic Checkpoint](../devlog/2025-12-20-revA-schematic-checkpoint.md)** — Progress snapshot

---

## External repos

- **[Hardware](https://github.com/Bushido3403/nodifyr-hardware)** — Schematics, layouts, manufacturing files
- **[Firmware](https://github.com/Bushido3403/nodifyr-firmware)** — Embedded code for beacon + hub
- **[Software](https://github.com/Bushido3403/nodifyr-software)** — Gateway forwarding logic (later: cloud, if needed)

---

## Quick navigation by task

**"I want to understand the project"**
→ Start with [What is Nodifyr?](what-is-nodifyr.md) and [System Overview](../architecture/system-overview.md)

**"I want to see the flagship product"**
→ [Solar Beacon v1 Overview](../projects/solar-beacon-v1/overview.md)

**"I want to understand the plan"**
→ [Roadmap](roadmap.md) (Stage A: beacon, Stage B: hub, Stage C: cloud later)

**"I want to see measurements"**
→ [Measurement Plan](../projects/solar-beacon-v1/measurement-plan.md) and [Measurements](../testing/measurements.md)

**"I want to build this"**
→ Wait for Template Pack v1 (coming after beacon v1 ships)
