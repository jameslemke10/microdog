# Open questions

Things that are undecided or unmeasured. Mechanical questions get settled one part at a time in the [CAD plan](cad-plan.md). If you can answer one with a measurement or a sourced part, open an issue.

## Mechanics

1. **What runs through the neck?** The Pi is in the head, so the neck carries power, USB to the URT-2 in the body, the servo chain, and I2C from the body IMU. Open points: does the 5 V regulator sit in the body or the head (pack voltage through the neck means less current), does I2C hold up over the neck's length at 400 kHz, and how much cable slack the neck and head joints need.
2. **Payload.** How much should it carry or push? This drives servo torque, peg strength, wheel grip and battery placement.
3. **Attachment interface.** Peg size and spacing, how an attachment stays on, and how the robot lets go.
4. **Which IMUs?** On hand: 2× HW-123 (MPU-6050) and 1× GY-BNO08X. Proposed: the BNO08X in the body (fused orientation and heading for driving), one MPU-6050 in the head. Their addresses (0x4A/0x4B and 0x68) don't clash.
5. **Wheels.** Size, tyre, and whether the wheels are driven directly by servos.
6. **Quiet head?** STS3215s are metal-geared and audible. Microduck's Dynamixel XL330s are quieter but cost more.
7. **Camera cable length** through the neck: 300 mm, or the 500 mm option.

## Electrical

8. **NP-F battery plate.** Plate chosen (~100 × 90 × 15 mm, 75 mm VESA holes, ~49 g). Its stock DC barrel lead gets replaced with 16–18 AWG; confirm the contacts handle the current and caliper it for the CAD.
9. **Main switch and fuse rating.** The switch on hand is a round KCD1 marked 6(3)A on its body, although the listing says 20 A at 12 V DC. Several servos stalling can draw more than 6 A. Options: a switch marked for 15 A DC or more, or the XT60 plug as the main disconnect. Then reconcile the 15 A fuse with the switch and the pack's own 11 A trip.
10. **URT-2 USB isolation.** The listing says dual TTL + RS485 ports over USB-C, so two servo chains plug straight in. Still meter whether USB VBUS is isolated from the servo supply.
11. **ToF board.** A VL53L7CX breakout is on hand; identify the board maker for its drawing, address and driver (ST's ULD driver, loaded at start-up).
12. **I2S overlay** for simultaneous mic capture and amp playback.

## Project

13. **Battery for a public kit.** The removable NP-F970 is the current plan; cells in holders are cheaper but more DIY.
14. **License for hardware files.** Everything is MIT for now. Something like CERN-OHL-P could fit the CAD better.
