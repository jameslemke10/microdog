# Hardware

## Bill of materials

The full list with links is in [`bom.csv`](bom.csv) (it opens as a table on GitHub). Prices were checked in November 2026 before tax and shipping, so expect them to drift.

| Category | Sourced cost (USD) | What's in it |
|---|---:|---|
| Actuation | $269.88 | 11× STS3215 servos, URT-2 bus adapter |
| Compute | $147.10 | Pi 5 4 GB, Active Cooler, microSD |
| Sensors | $82.07 | Camera Module 3 Wide + Pi 5 cable, BNO086 IMU + Qwiic lead |
| Power | $121.28 | NP-F970 battery, switch, 5 V regulator, wire, lever nuts, caps |
| Audio | $26.34 | I2S amp, speaker, 2 mics (sold in multi-packs) |
| Misc | $5.93 | Jumper wires |
| **Total** | **$652.60** | |

**Not yet in the total:** ToF sensor (~$20), NP-F battery plate (~$15), 15 A fuse, filament and screws, and a USB-C PD charger (36 W+) if you don't have one. The optional Hailo AI HAT+ is about $70–110.

### Column guide

| Column | Meaning |
|---|---|
| `qty` | How many the robot uses |
| `price_usd` / `price_for` | What the linked listing cost, and what that price buys (some listings are multi-packs) |
| `required` | `yes`, `planned` (part not chosen yet), or `optional` |
| `notes` | Alternatives, gotchas, and anything still TBD |

When a part is chosen or a link dies, update `bom.csv` and this table in the same PR.

## Build notes

Assembly instructions arrive with the body CAD. Until then:

- Wiring and power: [`docs/power.md`](../docs/power.md), [`docs/wiring.md`](../docs/wiring.md)
- Order of first power-up: [`docs/bring-up.md`](../docs/bring-up.md)

Photos and wiring images go in `hardware/img/`.
