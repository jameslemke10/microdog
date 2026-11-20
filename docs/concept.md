# Concept

<img src="../hardware/img/concept-sketch.jpg" alt="Microdog concept sketch: side view and isometric view" width="600">

*The first sketch (November 2026). Nothing here is final. The [CAD plan](cad-plan.md) turns it into decisions one part at a time.*

## The idea

Microdog is a small wheeled robot with a long neck and an expressive head, inspired by Pollen Robotics' Microduck. Instead of walking, it rolls. Its servos go into **reach and height** instead, so it can use tools.

**Attachments are the point.** Microdog has **pegs** on its sides, and attachments are made to hook onto them. It picks one up by lining up with it and lifting with its neck or by raising its body. Once an attachment is on, the robot works it by moving its whole body:

| Attachment | How Microdog uses it |
|---|---|
| Broom / sweeper | Hook on, set the height so the bristles touch, drive |
| Mop pad | Hook on, press down with body height, drive in passes |
| Small vacuum | Hook on, press its power button, drive. Weight is the open question. |

It can be told what to do ("sweep the kitchen"), or notice a mess on its own with the camera and deal with it.

## The 11 servos (from the sketch)

| Group | Count | What it does |
|---|---:|---|
| Lower body | 4 | TBD: wheels, legs, or both |
| Upper body | 3 | Body height, neck pitch, and one more (TBD) |
| Head | 4 | Head joints; one may press buttons ("turn on") |

The exact joints get decided part by part in the [CAD plan](cad-plan.md). See also [servo_map.md](servo_map.md).

## What it should feel like to build

- **Hobbyist-grade:** printable on a normal 3D printer, with off-the-shelf parts and screws. No machining.
- **Copyable:** every part comes with a link, a price and a reason in the [BOM](../hardware/bom.csv).
- **Understandable:** each part's design decisions are written down, so you can change one without breaking the others.

## Questions the sketch raises

- How much can it carry? This sets servo torque, peg strength and wheel grip.
- How does an attachment stay on, and how does the robot let go of it?
- Where does the battery sit so it doesn't tip when the neck reaches forward with a load?
