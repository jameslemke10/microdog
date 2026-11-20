# Microdog docs

Suggested reading order:

1. [**concept.md**](concept.md): the idea, the sketch, and how attachments work.
2. [**cad-plan.md**](cad-plan.md): how the printed parts get designed, one approved step at a time.
3. [**architecture.md**](architecture.md): the "brain". What runs on the Pi, what runs off-board, and how data flows.
4. [**power.md**](power.md): battery to servos and Pi, voltage limits, and the meter checks to do first. **Read before powering anything.**
5. [**wiring.md**](wiring.md): Pi 5 pin assignments and every signal connection.
6. [**servo_map.md**](servo_map.md): servo IDs, roles and sign conventions.
7. [**audio.md**](audio.md): I2S mics and speaker.
8. [**bring-up.md**](bring-up.md): the step-by-step checklist from a bare Pi to driving.
9. [**open-questions.md**](open-questions.md): what's undecided or unmeasured. Good places to help.

Conventions used throughout:

- **TBD** means nobody has measured or decided it yet. Don't guess it in code.
- Voltages are at the battery side unless stated. "Pack" is the NP-F970 battery.
- Robot frame: X forward, Y left, Z up, millimetres.
