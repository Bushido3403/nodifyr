# Power Path (v1)

This page defines the **energy architecture** for the beacon: solar input, storage behavior, backup behavior, and how we avoid leaking current during sleep.

> v1 priority: a power path that is easy to measure and reason about.

---

## Block diagram (concept)

```text
          +-------------------+
Solar --->| Harvester / Reg   |-----> Storage Rail (VSTOR)
          +-------------------+              |
                                              |
                                     +----------------+
                                     | Supercap (C)   |
                                     +----------------+
                                              |
                                              +-----> Ideal Diode OR ---> VSYS ---> nRF54 + sensors
                                              |
Coin Cell ------------------------------------+
```

**Notes**

* The solar side feeds a storage rail (VSTOR) that charges a supercap.
* The coin cell is a backup source through an ideal diode (or ideal-diode controller).
* VSYS is the rail the system actually runs from.

---

## Design intent (what "good" looks like)

* **No always-on resistor dividers** bleeding current during deep sleep
* Backup coin cell should not "fight" the solar/storage rail
* Brownout/cold-start behavior is deterministic and testable
* System current measurement is easy (inline measurement point or shunt option)

---

## Power states (to design + measure)

1. **System OFF baseline**
   Everything as off as possible. Goal is "only what must be alive."

2. **System OFF with timed wake**
   Timer running so beacon can wake periodically.

3. **Active sampling**
   Sensors powered/used briefly, then shut down.

4. **Advertise burst**
   BLE TX dominates. Keep it short.

5. **Charge conditions**
   Full sun vs indoor light vs dark, and how the storage rail behaves.

---

## Measurement provisions (v1 requirement)

Include at least one of:

* A **current measurement header/jumper** that lets you insert a meter/PPK inline
* A defined **shunt footprint** option (0Ω default / shunt optional)
* Test points for **VSYS**, **VSTOR**, and **coin-cell voltage**

> Even if the first revision is imperfect, having intentional measurement points is a signature Nodifyr move.

---

## Known risks / gotchas (to watch for)

* Ideal diode controller quiescent current (can silently dominate sleep)
* Supercap leakage vs storage rail "always on" components
* ADC/divider leakage if not gated
* Harvester/regulator behavior near zero light (may oscillate or leak)

---

## TODO (fill in later)

* Choose harvester/regulator approach (part selection + rationale)
* Choose ideal diode approach (part selection + quiescent current target)
* Define brownout thresholds + cold-start sequence
* Add first measured numbers:

  * System OFF baseline: ___ µA
  * System OFF timed wake: ___ µA
  * Active sample energy: ___ µC (or µJ)
  * TX burst energy: ___ µC (or µJ)
