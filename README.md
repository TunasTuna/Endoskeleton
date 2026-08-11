# Chrome Skull Robot — Head & Neck Build

An original robotic head/neck design in a chrome-skeleton aesthetic —
exposed servos, articulated jaw, visible neck actuators. Inspired by
classic chrome-endoskeleton sci-fi robot designs, not a reproduction
of any specific licensed character. Own proportions, own skull shape,
own mechanism layout.

## Design Direction

- **Style**: sleek / organic chrome — smooth biomechanical curves,
  not a boxy/industrial look. Plates with visible seams; joints and
  mechanism exposed at the gaps rather than a fully open lattice.
- **End goal**: functional build — motorized neck and jaw, not just
  a static display piece.
- **Finish**: undecided (polished chrome / brushed matte / mixed —
  chrome skull with dark mechanical joints).

## Mechanical Layout

4 servos total, base to head:

1. **Yaw servo** (base) — full head pan, left/right
2. **Roll servo** — side-to-side head tilt ("curious tilt")
3. **Tilt/pitch servo** — nod up/down, mounted closest to skull
4. **Jaw servo** (internal, in skull) — lever-arm driven, spring-return close

Chosen over a simpler 2-servo pan/tilt for more lifelike motion, and
over a cable-driven segmented "vertebrae" neck to keep build
complexity manageable for an intermediate Arduino/servo skill level.
Cable-driven neck is a possible future upgrade path.

Controller: Arduino-class board (Uno has enough PWM pins for 4
servos; Nano/ESP32 leave more headroom for growth).

## Project Structure

```
cad/           3D model files (Fusion 360 / SolidWorks / Blender / STL exports)
docs/          Design notes, build log, iteration photos
docs/references/   Original sketches, mood boards, proportion studies
firmware/      Microcontroller code (Arduino / ESP32 / etc.)
electronics/   Wiring diagrams, BOM, actuator/servo specs
```

## Goals

- [x] Define overall style direction (sleek biomechanical chrome)
- [x] Define neck DOF and servo layout (yaw / roll / tilt / jaw)
- [x] Concept sketch — joint layout + skull silhouette
- [ ] Face/skull doodle from user, refined into detailed concept art
- [ ] Finalize material/finish
- [ ] CAD model — skull shell
- [ ] CAD model — neck articulation (pan/tilt/roll)
- [ ] Servo/actuator selection (specific models + torque calcs)
- [ ] Wiring + control electronics
- [ ] Firmware for basic pose control

## Build Log

### 2026-08-11
- Initial repo setup
- Locked design direction: sleek/organic chrome, functional build,
  3-DOF neck (yaw/roll/tilt) + jaw servo
- First concept diagram: joint stack + skull silhouette placement

## License

TBD — consider MIT for firmware/code, and CC-BY-NC or similar for
design files if you want to allow remixing but not commercial use.
