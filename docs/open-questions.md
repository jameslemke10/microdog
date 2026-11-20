# Open questions

Things that are undecided or unmeasured. Mechanical questions get settled one part at a time in the [CAD plan](cad-plan.md). If you can answer one with a measurement or a sourced part, open an issue.

## Mechanics

1. **Which joints get the 11 servos?** The sketch splits them 4 lower body / 3 upper body / 4 head. Each joint still needs choosing.
2. **Payload.** How much should it carry or push? This drives servo torque, peg strength, wheel grip and battery placement.
3. **Attachment interface.** Peg size and spacing, how an attachment stays on, and how the robot lets go.
4. **Wheels.** Size, tyre, and whether the wheels are driven directly by servos.
5. **Quiet head?** STS3215s are metal-geared and audible. Microduck's Dynamixel XL330s are quieter but cost more.
6. **Camera cable length** through the neck: 300 mm, or the 500 mm option.

## Electrical

7. **NP-F battery plate.** The exact listing and its current rating after rewiring with 16–18 AWG still need confirming.
8. **Fuse rating.** 15 A was chosen. Reconcile it with the 20 A switch and the pack's own 11 A trip.
9. **URT-2.** Does it have one or two TTL sockets, and is USB VBUS really isolated from the servo supply? Needs a meter check.
10. **ToF board.** VL53L7CX is intended, but no specific breakout, address or driver has been chosen yet. Pololu's VL53L5CX carrier is the fallback.
11. **I2S overlay** for simultaneous mic capture and amp playback.

## Project

12. **Battery for a public kit.** The removable NP-F970 is the current plan; cells in holders are cheaper but more DIY.
13. **License for hardware files.** Everything is MIT for now. Something like CERN-OHL-P could fit the CAD better.
