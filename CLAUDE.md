# Working on Microdog

Notes for anyone, human or AI agent, picking up work in this repo.

## Where things are

- `docs/`: the design. Start with `docs/cad-plan.md`, which covers the gated CAD process, the Step 0 ground rules, the component library table and the decision log.
- `hardware/bom.csv`: every part, with links and notes.
- `cad/`, `software/`: finished, approved work only. Both are empty until something graduates.
- `internal/`: work in progress, **git-ignored and never pushed**. If it exists on this machine, read `internal/STATUS.md` first: it says where the work stands and what's next.

## How CAD work is done

- **One part at a time, four gates:** A Brief (words only), B Block-out (boxes around real component models), C Detail, D Print + fit. **Nothing moves to the next gate without the owner's explicit approval.** Order: body, then rear, front, neck, head.
- **Real numbers only.** Every dimension comes from a vendor model, a datasheet, a measurement or an approved decision, with its source written next to it. Unknown values are `TBD` and stop the gate. Don't invent pinouts, servo IDs or dimensions.
- **Tool:** build123d (Python, OpenCASCADE). Reviews happen in the OCP CAD Viewer at `http://localhost:3939`.
- Each decision goes into the decision log at the bottom of `docs/cad-plan.md`.

## Conventions

- The owner reviews every step, so keep changes small and explain them in plain words.
- Ask before pushing, publishing, or creating anything outside the repo.
