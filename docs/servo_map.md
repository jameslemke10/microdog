# Servo map

All 11 actuators are **Feetech STS3215 7.4 V (C001, 1:345 gearing)** serial bus servos on one bus at **1 Mbaud** through a URT-2 adapter.

## Joints

IDs follow the group: rear 10s, front 20s, neck and head 30s. That way an ID tells you roughly where the servo is. Sign conventions and limits get filled in at bring-up.

| ID | Group | Joint | Mode | Positive direction | Limits |
|---|---|---|---|---|---|
| 11 | Rear | Rear hip (yaw, steering) | position | TBD | TBD |
| 12 | Rear | Rear leg (pitch) | position | TBD | TBD |
| 13 | Rear | Rear-left wheel | wheel | TBD | continuous |
| 14 | Rear | Rear-right wheel | wheel | TBD | continuous |
| 21 | Front | Front leg (pitch) | position | TBD | TBD |
| 22 | Front | Front-left wheel | wheel | TBD | continuous |
| 23 | Front | Front-right wheel | wheel | TBD | continuous |
| 31 | Neck | Neck (pitch) | position | TBD | TBD |
| 32 | Head | Head pitch | position | TBD | TBD |
| 33 | Head | Head yaw | position | TBD | TBD |
| 34 | Head | Jaw | position | TBD | TBD |

The IDs are a proposal; confirm them before programming any servo. Your existing servos still carry IDs from an earlier project, so re-ID them to this table.

## Setting up a servo

1. Plug in **one** servo alone. New servos all answer as ID 1, so two at once collide.
2. Give it its ID from the table.
3. Raise its over-voltage limit to 9.0 V (see below).
4. Label the servo body with its ID.

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
