# Endoskeleton

A DIY animatronic head and neck build — an original mechanical design in the boxy, exposed-endoskeleton style you'd see in a maker workshop, not a reproduction of any licensed character. This is a personal project I'm building from scratch, from concept sketches through to a working motorized head.

## What this is

The goal is a functional robotic skull with a fully articulated neck: it can pan, tilt, and roll, and the jaw opens and closes on its own servo. Everything here — proportions, panel layout, mechanism placement — is original, worked out over a series of design passes rather than copied from an existing character or product.

## Design direction

The look settled into something boxy and geometric: a square skull frame, square eye housings holding round ball-and-socket eyes, and a hinged lower jaw with a segmented teeth block. This wasn't the starting point — the project began with a smoother, more organic chrome concept, and shifted after working through some animatronic-style reference material. The full reasoning behind that (and other design choices) is written up in [`docs/design-decisions.md`](docs/design-decisions.md).

Finish is still open — polished chrome, brushed matte, or a mix of the two with darker mechanical joints are all on the table.

## How it moves

Four servos, base to head:

1. **Yaw** — pans the head left and right
2. **Roll** — tilts the head side to side
3. **Tilt** — nods the head up and down
4. **Jaw** — internal servo with a lever arm and spring return, for the mouth

I went with this 3-axis neck instead of a simpler 2-servo pan/tilt because it moves a lot more naturally, and picked it over a cable-driven segmented neck (which looks even better, but adds a lot of tensioning and calibration headaches) to keep the build realistic for where my skills are right now. The cable-driven version is a tempting upgrade for a future revision.

Planning to run this on an Arduino-class board — an Uno has enough PWM output for four servos, though a Nano or ESP32 would leave more room to grow.

## Repo layout

```
cad/                3D model files (Fusion 360 / SolidWorks / Blender / STL exports)
docs/               Design notes, build log, reference material
docs/references/    Sketches, mood boards, and reference images used along the way
firmware/           Microcontroller code
electronics/        Wiring diagrams, BOM, servo/actuator specs
```

## Progress

- [x] Settle on an overall style direction
- [x] Define neck degrees of freedom and servo layout
- [x] First concept sketch — joint layout and skull silhouette
- [x] Revise silhouette after reviewing animatronic reference designs
- [ ] Lock final proportions and dimensions
- [ ] Finalize finish/material
- [ ] CAD — skull shell
- [ ] CAD — neck articulation
- [ ] Pick actual servo models and check torque requirements
- [ ] Wiring and control electronics
- [ ] Firmware for basic pose control

## Build log

**2026-08-11**
Set up the repo and worked through the early design decisions. Started with a sleek, organic chrome concept and a 3-axis neck plus jaw servo, and sketched out the first joint layout. After looking at some animatronic endoskeleton reference blueprints, pivoted the whole silhouette to something boxier and more geometric, with round ball-and-housing eyes and a segmented teeth block for the jaw. Put together a second concept sketch reflecting the new direction.

## License

This project is open source, under two licenses depending on the content:

- Firmware and code (`/firmware`) — [MIT](firmware/LICENSE)
- Everything else — design files, docs, images (`/cad`, `/docs`, `/electronics`) — [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), meaning anyone can use or build on it, commercially or not, as long as they credit this project.

See [LICENSE](LICENSE) for details.
