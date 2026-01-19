# Packet Spec (v1)

This page defines the beacon's **advertising payload** so:
- gateways/phones can decode it immediately
- future cloud work is easy (stable contract)
- we can version and extend without breaking old decoders

---

## Transport
- BLE Advertising
- Payload carried in **Manufacturer Specific Data** (`0xFF`)
- Endianness: **little-endian** for multi-byte fields

---

## Manufacturer data layout (v1)
> Total bytes below (excluding the 2-byte Company ID) = 15 bytes  
> This comfortably fits common advertising payload limits.

| Byte(s) | Field | Type | Notes |
|---:|---|---|---|
| 0 | `ver` | u8 | Packet version (start at `0x01`) |
| 1 | `msg_type` | u8 | `0x01 = sensor` (reserve others) |
| 2–4 | `device_id` | u24 | 24-bit unique ID (printed on board / derived from HW ID) |
| 5 | `seq` | u8 | increments each transmission (wrap ok) |
| 6 | `flags` | u8 | bitfield (see below) |
| 7–8 | `temp_c_x100` | i16 | temp in °C * 100 (e.g., 23.45°C → 2345) |
| 9–10 | `rh_x100` | u16 | relative humidity % * 100 (45.12% → 4512) |
| 11–12 | `vsys_mv` | u16 | system/storage voltage in mV |
| 13 | `energy_state` | u8 | 0–255 (simple bucket/estimate; define later) |
| 14 | `reserved` | u8 | set 0 for now |

---

## Flags bitfield (byte 6)
| Bit | Name | Meaning when 1 |
|---:|---|---|
| 0 | `LOW_LIGHT` | charging input insufficient / in energy-saving mode |
| 1 | `LOW_VOLT` | VSYS below threshold |
| 2 | `COLD_START` | just recovered from brownout/cold start |
| 3 | `SENSOR_ERR` | sensor read failed (temp/rh invalid) |
| 4 | `CFG_CHANGED` | configuration changed since last boot |
| 5–7 | reserved | set to 0 |

---

## Invalid / missing data conventions
- If sensor read fails:
  - `flags.SENSOR_ERR = 1`
  - `temp_c_x100 = -32768` (0x8000)
  - `rh_x100 = 65535` (0xFFFF)

---

## Example decode
- temp: `temp_c_x100 / 100.0`
- humidity: `rh_x100 / 100.0`
- voltage: `vsys_mv` as integer mV

---

## Versioning rules
- v1 decoders must ignore unknown `msg_type`
- New fields should be introduced by:
  - bumping `ver`, OR
  - using `reserved` or appending bytes only when space allows

---

## TODO (later)
- Decide how `device_id` is generated (printed ID vs derived)
- Define `energy_state` meaning (e.g., supercap percent buckets)
- Decide if we need a tiny checksum (likely unnecessary for v1)
