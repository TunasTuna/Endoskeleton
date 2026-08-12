# Eye mechanism — third-party design

These files are **not original to this project**. They're used here as
the eye movement mechanism for the head, with credit and license
preserved as required.

## Source

- **Design**: "Animatronic eyes FNAF"
- **Creator**: Aqua_Cat (Thingiverse)
- **Original page**: https://www.thingiverse.com/thing:6782900
- **License**: Creative Commons — Attribution — Share Alike (CC BY-SA)
  See `LICENSE.txt` in this folder for the exact license statement
  as provided by the creator.

## What's here

| File | Part |
|---|---|
| `jjj1.stl` | Eye front cover / retaining ring |
| `jjj2.stl` | Eyeball sphere |
| `jjj3.stl` | Eye back cap / socket dome |
| `jjj4.stl` | Mounting bracket + pivot posts |
| `jjj5.stl` | Pivot pin |
| `eyelids.stl` | Eyelid shutter |

Mechanism uses 3 servos: one under the assembly with a string linkage
driving both eyelids, and two paired servos (one per eyeball) linked
by cable so both eyes track together.

## Why this matters for licensing

The rest of this repo's design files (`/cad`, `/docs`, `/electronics`)
are licensed CC BY 4.0 — see the root `LICENSE`. This folder is a
**carve-out**: because the source design is CC BY-**SA** ("Share
Alike"), any build or derivative that incorporates these specific
files needs to stay under CC BY-SA terms for the parts that came
from here, not the more permissive CC BY the rest of the project
uses. That's a condition of the original creator's license, not this
project's choice, so it's kept isolated in its own folder rather than
applied to the whole repo.

In practice: if you build or share something using this eye
mechanism specifically, credit Aqua_Cat and keep it CC BY-SA. The
rest of the head/neck design (skull, jaw, servo mounts) is unaffected
and remains under this project's own CC BY license.

## Fit check against final skull dimensions (2026-08-11)

Skull is now 183mm wide (17cm scale, see docs/specs.md). Checked
whether these files fit as-is or need adjustment:

- **Native size doesn't fit**: two full-size brackets (112.4mm each)
  side by side would need 225mm — wider than the 183mm skull.
- **Scaling to 60% fits**: at 60% scale, the eyeball comes out to
  ~44mm (matches our 60mm eye housing target), and two scaled
  brackets fit comfortably within the skull width (~148mm used of
  183mm available).
- **Servo clearance checked, not just geometry**: at 60% scale, the
  bracket's smallest dimension is still ~50mm — comfortably larger
  than the real micro servo's largest dimension (~29mm), so the
  actual SG90-class hardware should still physically fit inside the
  scaled bracket, not just the outer shape.

**Action before printing**: scale all 6 STL files in this folder to
60% in your slicer (or when importing to CAD) before printing.
Re-check clearance once printed, since slicer-scaled parts can
sometimes need minor hole/tolerance adjustments that don't scale
linearly (screw holes, pin diameters).

## Note

This is also, by its own title, a fan-derivative design referencing
Five Nights at Freddy's. It's used here purely for its mechanism
(servo/linkage layout), not to replicate any character's likeness —
consistent with the rest of this project's original, non-replica
direction.
