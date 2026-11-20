# Servo map

All 11 actuators are **Feetech STS3215 7.4 V (C001, 1:345 gearing)** serial bus servos on one bus at **1 Mbaud** through a URT-2 adapter.

## Joints

The sketch splits them 4 / 3 / 4. Each row gets filled in when the [CAD plan](cad-plan.md) step for that part is approved.

| Group | Joint | ID | Mode | Notes |
|---|---|---|---|---|
| Lower body | TBD | TBD | | |
| Lower body | TBD | TBD | | |
| Lower body | TBD | TBD | | |
| Lower body | TBD | TBD | | |
| Upper body | Body height | TBD | position | |
| Upper body | Neck pitch | TBD | position | |
| Upper body | TBD | TBD | | |
| Head | TBD | TBD | | |
| Head | TBD | TBD | | |
| Head | TBD | TBD | | |
| Head | TBD | TBD | | |

**ID convention (proposed):** number by group, so IDs read like a map: lower body 10–19, upper body 20–29, head 30–39.

## Setting up a new servo

1. Plug in **one** servo alone. New servos all answer as ID 1, so two at once collide.
2. Give it its ID from the table.
3. Raise its over-voltage limit to 9.0 V (see below).
4. Mark the servo body with its ID.

Tooling for these steps lands in `software/` once it's been tested on the new build.

## Registers worth knowing

| Address | Name | Notes |
|---|---|---|
| 0x05 | ID | EEPROM |
| 0x0E / 0x0F | Max / min voltage | 0.1 V units. Factory max is 80 (8.0 V), below a full pack (8.4 V). Set 88–90. |
| 0x21 | Mode | 0 position, 1 wheel (continuous), 2 PWM, 3 step |
| 0x28 | Torque enable | |
| 0x37 | Lock | Write 0 to unlock EEPROM, then 1 to relock |
| 0x38 | Present position | 0..4095 = 360° |
| 0x3E | Present voltage | 0.1 V units |
| 0x45 | Present current | 6.5 mA units |

Source: [STS3215 datasheet](https://files.seeedstudio.com/products/Feetech/108090023_STS3215-C001_Datasheet.pdf).
