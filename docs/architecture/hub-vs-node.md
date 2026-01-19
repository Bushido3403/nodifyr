# Hub vs. Node Architecture

Here's how the system fits together, and why each piece exists.

---

## The beacon (node) — flagship

**nRF54 solar-powered BLE sensor beacon**

This is the **differentiated product**. It's battery/solar-powered, ultra-low-power, and designed to run for months or years on harvested energy + a coin-cell backup.

**What it does:**
- Wakes on a schedule (e.g., every 60 seconds)
- Samples sensors (temp, humidity, light, etc.)
- Broadcasts a BLE advertising packet or sends structured data
- Returns to deep sleep (nanoamp-level current draw)

**Why it's the flagship:**
- It's rare and hard to do right
- It showcases ultra-low-power design + power-path switching + energy harvesting
- It creates a high-value Template Pack (design files + firmware + bring-up checklist)
- The scope is tight and finishable

**Shipping order:** Stage A (now)

---

## The hub (gateway) — later

**ESP32-S3 mains-powered receiver/forwarder**

This is the **bridge device**. It's mains-powered (USB-C or wall adapter), receives BLE packets from beacons, and forwards them somewhere useful (Wi-Fi, MQTT, Home Assistant, webhook, etc.).

**What it does:**
- Receives BLE advertising packets or connection-based data from beacons
- Forwards to: MQTT broker, HTTP endpoint, local UI, or CSV log
- Runs continuously (no sleep, no battery worries)

**Why it's not the flagship:**
- \"ESP32 dev board with charging\" is crowded territory
- It's useful, but not differentiated
- It makes more sense as the **second product** after the beacon ships

**Shipping order:** Stage B (later, after beacon v1 exists)

---

## How they work together

**Stage A (now): Beacon + phone**
- Beacon advertises BLE packets
- Phone (generic BLE scanner app) logs them locally
- Output is CSV, logs, or simple UI
- No hub needed yet

**Stage B (later): Beacon + hub**
- Beacon advertises or connects to hub via BLE
- Hub receives packets and forwards via Wi-Fi
- Hub sends to: MQTT / webhook / Home Assistant / basic endpoint
- Still not \"Nodifyr Cloud,\" just a bridge

**Stage C (much later): Beacon + hub + cloud**
- Only if there's paying demand pulling you there
- Dashboards, accounts, multi-tenant cloud
- But don't build this until beacon + hub are shipped and selling

---

## Design constraints (why this split works)

**Beacon:**
- Must be ultra-low-power (nanoamps in sleep)
- Must balance energy (solar input = average consumption over time)
- BLE-only (Wi-Fi would kill the battery)
- Coin-cell backup for dark periods

**Hub:**
- Mains-powered (no sleep, no battery worries)
- Wi-Fi + BLE (can bridge between protocols)
- Always-on receiver (can log/forward 24/7)
- Clean power-path design (USB-C charging + backup battery for brief outages)

---

## Data flow (simple version)

```
Beacon → [BLE advertising] → Hub → [Wi-Fi] → Somewhere (MQTT / webhook / HA)
```

**Data contract (defined now, even though cloud is later):**
- Payload format: versioned, documented packet structure
- Timestamps: beacon timestamp (if RTC) or hub-added timestamp
- Sensor IDs: unique beacon ID + sensor type
- Battery/energy status: voltage, charge state, solar input state

This way, when you add cloud later, it's an incremental step, not a rewrite.

---

## Why not both at once?

**Focus.**

Building two products in parallel is a great way to ship neither. The beacon is the differentiated product that creates revenue + portfolio value. The hub is useful, but it's better as a **later release** or a free credibility artifact.

Commit to the beacon for 8–12 weeks. Once it ships, move to the hub.