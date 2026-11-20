# Bring-up checklist

Bring up one subsystem at a time, in this order. When a step passes, its test script moves into `software/` and its findings go into the docs.

- [ ] **0. Power checks:** the meter sequence in [power.md](power.md#bring-up-checks-do-these-in-order), before any servo moves.
- [ ] **1. Pi boots on the regulator:** cooler fitted, `PSU_MAX_CURRENT=5000` set, `vcgencmd get_throttled` = `0x0` during camera preview.
- [ ] **2. Servo bus:** URT-2 shows up as `/dev/ttyACM*`. Scan the bus, assign IDs from [servo_map.md](servo_map.md), and set every servo's over-voltage limit to 9.0 V.
- [ ] **3. One joint at a time:** low torque, joints free to move, check direction and limits for each.
- [ ] **4. IMU:** heading and tilt from the BNO086 at 0x4B. Tilt the robot and check the signs.
- [ ] **5. Camera:** `rpicam-hello` preview, then a short `rpicam-vid --low-latency` stream to a laptop.
- [ ] **6. ToF:** once the exact sensor board is chosen.
- [ ] **7. Audio loopback:** mic → speaker once the I2S overlay is verified ([audio.md](audio.md)).
- [ ] **8. Vision benchmark:** YOLOv8n / YOLO11n at 320 and 640 px on the CPU. Record fps, model size and CPU %.
- [ ] **9. Stall test with logging:** pack voltage, servo voltages and the Pi's `EXT5V_V` during a deliberate stall with every servo connected.
- [ ] **10. Teleop:** drive from a laptop or gamepad, with the link watchdog on.

If you're building one too, a short write-up in an issue (photos, readings, surprises) helps everyone.
