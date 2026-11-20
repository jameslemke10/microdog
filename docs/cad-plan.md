# CAD plan

Microdog's parts are designed **one at a time, with an approval at every gate**. Mistakes made early, like a wrong servo pocket or a battery that doesn't fit, get expensive once other parts are built around them. Small steps catch them while they're still cheap. Each part also teaches something that makes the next one better, so lessons are written down in the [decision log](#decision-log).

## Order

```mermaid
flowchart LR
    S0[0. Ground rules] --> B[1. Body core] --> R[2. Rear lower body] --> F[3. Front lower body] --> N[4. Neck + pegs] --> H[5. Head] --> A[6. First attachment]
```

The body comes first because everything else bolts to it. Then work rearward to finish the base, then forward and up to the head.

| # | Part | Holds / does | Depends on |
|---|---|---|---|
| 0 | Ground rules | Printer, material, fasteners, tolerances, review format, size and payload targets | — |
| 1 | Body core | Battery bay, Pi 5, URT-2, regulator, switch, power hub, wire paths, and the mounting faces for the legs and neck | 0 |
| 2 | Rear lower body | Rear wheels and their servos, plus any rear height or steering joint | 1 |
| 3 | Front lower body | Front wheels and their servos, plus the front height joint ("this is height" in the sketch) | 1, 2 |
| 4 | Neck + pegs | Neck pitch and lift joints, pegs for attachments, and the peg spec that attachments follow | 1–3 |
| 5 | Head | 4 head servos, camera, mics, speaker, ToF, and button pressing | 4 |
| 6 | First attachment | A broom that hooks onto the pegs. This proves the whole idea. | 4, 5 |

## The loop for every part

Each part goes through four gates. **Nothing moves to the next gate without an explicit approval.**

```mermaid
flowchart LR
    A["A · Brief<br/>(words only)"] -->|approve| B["B · Block-out<br/>(boxes)"] -->|approve| C["C · Detail<br/>(real features)"] -->|approve| D["D · Print + fit"] -->|approve| E[Graduate]
    B -. rework .-> A
    C -. rework .-> B
    D -. rework .-> C
```

| Gate | What gets made | What gets reviewed |
|---|---|---|
| **A · Brief** | A short page: what the part must do, what it touches, the hard constraints (real measured dimensions only), 2–3 options with trade-offs, and a recommendation | Pick an option, fix anything misunderstood. **No geometry yet.** |
| **B · Block-out** | Simple boxes and cylinders: part envelope, the real parts it holds as placeholders, joint axes, and range of motion | Renders from the standard views, overall size, centre of mass, clearances through the full joint range |
| **C · Detail** | Real features: servo pockets, screw holes, wire channels, fillets, print orientation | Renders, section cuts through every mating feature, and a table of key dimensions with where each number came from |
| **D · Print + fit** | A test print, and **test coupons first** for anything risky (servo pocket, screw boss, peg fit) | Photos, what fit, what didn't, print time, filament used |
| **Graduate** | Script and STL/STEP move into `cad/`. BOM, servo map and decision log are updated. | — |

### Rules that keep mistakes small

- **Real numbers only.** Every dimension comes from a datasheet, a caliper measurement or an approved decision, and its source is written next to it in the script. Anything else is `TBD` and stops the gate.
- **Measure first.** Before the brief for a part, measure the real components it holds (servo, battery plate, Pi with cooler, regulator) and record them.
- **One part per review.** Don't start the next part's geometry while the current one is waiting.
- **Same views every time** (iso, front, side, top, plus sections) so reviews are quick to compare.
- **Interfaces get named.** Where two parts meet (for example "rear leg mounting face"), the interface is defined once in the earlier part and reused by the later one, not re-guessed.

## Step 0: ground rules to decide before the body

| Decision | Options / notes | Decision |
|---|---|---|
| CAD tool | Code-generated (CadQuery or build123d) so parts are reviewable as text | TBD |
| Printer and bed size | Sets the maximum single-part size, and therefore where the body splits | TBD |
| Material | PLA (easy) vs PETG (tougher, better for pegs and mounts) | TBD |
| Fasteners | Heat-set inserts vs screws straight into plastic, and which sizes (M2/M3) | TBD |
| Fit tolerances | Clearance for servo pockets and pegs, found with a test coupon on your printer | TBD |
| Overall size | Target length × width × height, standing and crouched | TBD |
| Payload | Heaviest attachment it must lift or push | TBD |
| Wheels | Size, tyre (printed TPU vs bought), and servo-direct drive or not | TBD |
| Servo split | Confirm 4 lower body / 3 upper body / 4 head, and what each joint is | TBD |

## Decision log

Every approved decision goes here, newest at the bottom, with what was learned.

| Date | Part / gate | Decision | Why / lesson |
|---|---|---|---|
| 2026-11-20 | Plan | Body first, then rear, front, neck, head; four gates per part | Approving one part at a time catches mistakes early |
