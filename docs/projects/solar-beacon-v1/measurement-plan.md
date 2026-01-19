# Measurement Plan (v1)

This plan makes power claims **repeatable**. Numbers go here as soon as we have them, even if they're ugly.

---

## Targets (v1)
> Fill these with your best current guess. You can tighten later.

- **System OFF baseline:** ___ µA (goal)
- **System OFF + timed wake:** ___ µA (goal)
- **Wake duration:** ___ ms (goal)
- **Sensor sample time:** ___ ms (goal)
- **Advertise burst duration:** ___ ms total (goal)
- **Default interval:** ___ s / ___ min

---

## Measurement setup
Pick one primary instrument and document it.

- **Primary instrument:** (PPK2 / Joulescope / DMM + shunt / other)
- **Inline method:** (jumper header / shunt footprint / series measurement point)
- **Sampling rate:** ___ (e.g., 1 ksps / 100 ksps / 1 Msps)
- **Burden voltage considerations:** (notes)
- **Environment notes:** (temperature, light level, etc.)

### Required test points
- VSYS: ___
- VSTOR / supercap: ___
- Coin cell: ___

---

## Test matrix
> "Expected" can be qualitative until you have real numbers.

| Test | Expected | Measured | Notes |
|---|---|---:|---|
| System OFF baseline | lowest possible (no timer) |  |  |
| System OFF + timed wake | slightly higher than baseline |  |  |
| Wake + sensor read | short burst then off |  |  |
| Advertise burst | short TX spikes |  |  |
| Interval average current | matches energy budget math |  |  |
| Cold start behavior | deterministic recovery |  |  |
| Low-light balance | reduces duty cycle or flags low light |  |  |
| Dark survival | coin cell sustains interval |  |  |

---

## Reporting format (how results will be published)
For each test, publish:
- Firmware config (interval, advertise parameters, sensor enabled)
- Supply conditions (light level, storage voltage starting point)
- A plot/screenshot + a summary:
  - peak current (mA)
  - burst charge/energy (µC/µJ if available)
  - average current over interval (µA)

---

## TODO (later)
- Add energy budget worksheet link
- Add first plotted capture once instrumentation is chosen
