# Nodifyr

Measured, portfolio-grade embedded systems — focused on **ultra-low-power**.

[Start here: Solar Beacon v1](projects/solar-beacon-v1/overview.md){ .md-button .md-button--primary }
[Docs philosophy](about/philosophy.md){ .md-button }
{: .button-group }

---

## The one-minute version

I'm building a **solar-powered BLE sensor beacon** with real measurements, real power numbers, and a template pack you can buy.

Not vaporware. Not promises. Measured data, open schematics, and implementation files.

**The funnel:**
1. **Proof you can trust this** — measured sleep current, energy budgets, real test methodology
2. **Proof the approach works** — live measurements, charge balance behavior, cold-start validation
3. **Ready to build?** — paid Template Pack with Altium project, firmware skeleton, bring-up checklist

---

## Month 2 checkpoints (what "on track" looks like)

If this is working, you'll see:

- [x] Coherent project narrative (not scattered pages)
- [ ] First baseline measurements published (even if rough)
- [x] Stable packet format (LOCKED)
- [ ] Waitlist collecting emails
- [x] Clear Template Pack v1 outline (people can see what they'll pay for)

Every page = deliverable. Every measurement = content. Every revision = legitimacy.

---

## What you get

### Free (right now)
- Architecture + block diagrams (solar + supercap + coin-cell)
- Measurement methodology (how we measure, what we measure)
- Energy budget calculations (duty cycle → average current → viability)
- Live proof posts (sleep currents, charge behavior)
- Design decisions + tradeoffs

### Paid — Template Pack v1 (coming soon)
- Altium project + schematic + layout
- BOM with alternates + quiescent current callouts
- Firmware skeleton (packet structure, sensor read, sleep cycle)
- Bring-up + validation checklist
- Porting guide (swap sensor, change interval, change panel)
- **One-time purchase, build as many as you want**
- **$99 — [Full details](template-pack-v1.md)**

<div style="text-align: center; margin: 2em 0;">
  <a href="https://nodifyr.io/waitlist" class="md-button md-button--primary" style="margin: 0.5em;">Get notified when it launches</a>
</div>

---

## Where to start

**"Should I trust this?"**
→ [What is Nodifyr?](start-here/what-is-nodifyr.md) + [Measurement plan](projects/solar-beacon-v1/measurement-plan.md)

**"What's the current project?"**
→ [Solar Beacon v1 Overview](projects/solar-beacon-v1/overview.md) + [Roadmap](start-here/roadmap.md)

**"Show me the measurements"**
→ [Measurement results](projects/solar-beacon-v1/measurement-plan.md) + [Real numbers](testing/measurements.md)

**"I want the pack"**
→ Join the waitlist (coming soon)

---

## The flagship: Solar Beacon v1 (nRF54)

A palm-sized **solar + coin-cell** BLE sensor beacon that actually balances energy. Built on measured power, repeatable methods, tight scope.

**Why this one?**
- It's rare (solar + harvesting + real measurements)
- It shows real engineering (power-path, quiescent current, energy budgets)
- It's finishable (BLE-only, tight scope)
- It creates a high-value template pack

**Quick links**
- [Overview & goals](projects/solar-beacon-v1/overview.md)
- [Power path design](projects/solar-beacon-v1/power-path.md)
- [Packet spec (locked)](projects/solar-beacon-v1/packet-spec.md)
- [Measurement methodology (locked)](projects/solar-beacon-v1/measurement-plan.md)

---

## The hub: ESP32-S3 Gateway (later)

Mains-powered receiver that bridges BLE → Wi-Fi. Shipped **after beacon v1** as the second product.

Not the focus right now. The beacon is the flagship.

---

## Philosophy

**Measured, not vibes.**
If it's not measured, it's labeled TBD. Real sleep currents, real charge balance, real energy budgets.

**Tight scope, finishable.**
One sensor, one payload, one measurement path. Everything else is DNP by default.

**Free proof, paid leverage.**
Architecture + measurements are free. Implementation files are paid.

---

## Contact

- Email: `kyle@nodifyr.io`
- GitHub: [Bushido3403](https://github.com/Bushido3403/)
- Instagram: [`@nodifyr_io`](https://www.instagram.com/nodifyr_io/)