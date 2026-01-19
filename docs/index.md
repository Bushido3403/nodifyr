# Nodifyr

Measured, portfolio-grade embedded systems — focused on **ultra-low-power**.

[Start here: Solar Beacon v1](projects/solar-beacon-v1/overview.md){ .md-button .md-button--primary }
[Docs philosophy](about/philosophy.md){ .md-button }

---

## Welcome

This site documents **Nodifyr**, an ongoing open-source IoT project developed by me, Kyle Buchanan.

I'm building this as openly as I can, and this documentation is a living record of architecture, design decisions, hardware revisions, experiments, and lessons learned along the way.

Keep in mind, this is not a finished product (yet), it's a transparent build process.

---

## The flagship: Solar Beacon v1 (nRF54)
A palm-sized **solar + coin-cell** BLE sensor beacon that actually balances energy — with real measurements and a template pack you can build from.

This is the **differentiated product**. Ultra-low-power architecture, power-path switching, and energy harvesting done right. It's tight scope, finishable, and creates a high-value implementation pack.

**Quick links**
- [Overview](projects/solar-beacon-v1/overview.md)
- [Power path](projects/solar-beacon-v1/power-path.md)
- [Packet spec](projects/solar-beacon-v1/packet-spec.md)
- [Measurement plan](projects/solar-beacon-v1/measurement-plan.md)

---

## The hub: ESP32-S3 Dev Board (later)
A mains-powered gateway/hub reference that receives BLE packets and forwards via Wi-Fi. Clean power-path design with USB-C charging and backup battery.

This comes **after the beacon v1 ships**. It's useful, but "ESP32 dev board with charging" is crowded territory. The beacon is where we differentiate.

---

## What Nodifyr ships
- **Free:** architecture + measurements + lessons learned (the proof)
- **Paid:** implementation-ready template packs (the leverage)

## Where should you start?

If you're new, start with **[What is Nodifyr?](https://docs.nodifyr.io/start-here/what-is-nodifyr/)**

That page explains my motivation behind the project, its long-term direction, and the kind of problems I aim to solve.

From there, you can explore:

- system architecture and interfaces
- board-specific documentation and revisions
- design decisions and tradeoffs
- measurements, testing notes, and known issues I discover
- devlogs on my ongoing progress

## About this site

I made this website using **Material for MkDocs** and it's built directly from Markdown files in my `nodifyr` [GitHub repository](https://github.com/Bushido3403/nodifyr).

My goal in documentation is durability and accuracy:

- documentation lives alongside the project itself
- changes are versioned
- assumptions and unknowns are tracked for future reference
- everything lives as context for future development

This page is intended to be a source of truth for the project, not a marketing page.

---

### P.S.

Where things are unfinished, uncertain, or untested, I will do my best to state that explicitly.

---

## Contact

- Email: `kyle@nodifyr.io`
- GitHub: [Bushido3403](https://github.com/Bushido3403/)
- Instagram: [`@nodifyr_io`](https://www.instagram.com/nodifyr_io/)