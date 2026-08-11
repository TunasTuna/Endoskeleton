# Dimensions and hardware spec

Working numbers to design the CAD model and pick real hardware
against, based on a human-head-scale target (18-22cm tall) in
3D printed PLA/PETG.

## Skull dimensions

| Dimension | Value |
|---|---|
| Cranium width | ~14 cm |
| Cranium height | ~13 cm |
| Cranium depth | ~14 cm |
| Total head height (with jaw + neck mount) | ~19-20 cm |
| Shell wall thickness | 2.5 mm |
| Recommended infill | 15-20% (thin-wall shells are carried by the walls, not infill) |

## Estimated weight

Rough build-up for the full head assembly (shell + jaw + eye
hardware + internal jaw servo + misc brackets/wiring):

| Part | Est. weight |
|---|---|
| Skull shell (2.5mm PLA/PETG) | ~295 g |
| Jaw piece | ~90 g |
| Eye housings + eyeballs | ~40 g |
| Jaw servo | ~55 g |
| Hardware / wiring / misc | ~60 g |
| **Total** | **~540 g** |

Worth re-checking this once the CAD model exists — actual geometry
(how much is open/hollow, how much detail on the jaw, etc.) will
shift this number. Treat as a starting estimate for servo selection,
not a final spec.

## Servo torque requirements

Neck servos have to support the head's weight off-axis (except yaw,
which just rotates the stack rather than holding it against gravity).

Static torque at the pivot ≈ head weight × lever arm from pivot to
head's center of mass (estimated ~8cm). At ~540g and 8cm lever arm,
that's roughly **4.3 kg-cm static**. Applying a 3x safety factor for
dynamic loads (acceleration, off-axis torque, aging gears) gives a
**practical minimum of ~13 kg-cm** for the load-bearing axes.

| Servo | Role | Load-bearing? | Min. torque | Suggested class |
|---|---|---|---|---|
| Yaw | Pan left/right | No (rotates the stack, doesn't hold weight against gravity) | ~5-6 kg-cm | Standard/mini servo |
| Roll | Side tilt | Yes | ~13+ kg-cm | MG996R-class or stronger |
| Tilt | Nod up/down | Yes | ~13+ kg-cm | MG996R-class or stronger |
| Jaw | Mouth open/close | No (light lever, short throw) | Low | Micro servo (SG90-class is fine) |

**Stack order matters**: keep the load-bearing (roll/tilt) servos
closest to the head, so they're bearing the head's weight directly
rather than through an extra linkage. Yaw can sit lower in the stack
since it only needs to rotate the assembly, not hold it up.

## Selected hardware (decided 2026-08-11)

**Roll and tilt servos: MG996R** — confirmed. Standard-size metal-gear
servo, ~11 kg-cm typical torque at 6V (up to ~13 kg-cm at higher
voltage), comfortably covers the calculated minimum with the 3x
safety margin already applied above.

MG996R physical dimensions (needed for CAD mounting brackets):

| Measurement | Value |
|---|---|
| Body size (W × H × D) | ~40.7 mm × 42.9 mm × 19.7 mm |
| Mounting tab span (hole to hole) | ~49.5 mm |
| Mounting tab thickness | ~2.5 mm |
| Output spline | 25T (standard servo horn spline) |
| Weight | ~55 g each |
| Operating voltage | 4.8-7.2 V |
| Torque | ~9.4 kg-cm @ 4.8V, ~11 kg-cm @ 6V |

Two of these (roll + tilt) adds ~110g to the weight estimate above —
worth folding into the final CAD weight check.

Yaw and jaw servo models still open — yaw just needs a standard/mini
servo with the ~5-6 kg-cm minimum, jaw can be a lightweight micro
servo (SG90-class). Worth picking exact models once we know if
you're sourcing everything from one supplier (matching connector
types simplifies wiring).

## Open questions

- Exact eye housing / eyeball diameter (needs to fit real hardware —
  LED module or plain sphere, once decided)
- Final infill % once the CAD model shows how much is actually
  hollow vs. solid
- Whether to reinforce the neck-servo mounting points with metal
  brackets instead of pure printed plastic, given the torque these
  joints carry
