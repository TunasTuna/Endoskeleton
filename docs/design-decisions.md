# Design decisions log

Rationale for key choices, so future-you (or collaborators) know why
things are the way they are.

## Not a replica

Early on we considered closely replicating a well-known chrome
endoskeleton character. Decided against it — even non-commercial fan
replicas carry copyright risk, and it's more interesting to design
something original in the same aesthetic family anyway. This project
uses "chrome biomechanical skull" as a style reference point, not a
model to copy.

## Neck: 3-DOF pan/tilt/roll (not cable-driven vertebrae)

Considered three options:

| Option | Motion quality | Build complexity |
|---|---|---|
| 2-servo pan/tilt | Basic | Low |
| 3-servo pan/tilt/roll | Good, lifelike | Medium |
| Cable-driven segmented neck | Best, most organic | High |

Went with 3-DOF pan/tilt/roll. Cable-driven segments look great but
add cable tensioning, stretch, and multi-point calibration — more
trouble than it's worth for a first pass at this scale of project.
Could revisit as a v2 upgrade.

## Jaw: single-pivot hinge + servo lever + spring return

Simple, reliable, easy to tune. A double-hinge (rear pivot point) is
more anatomically accurate and could be a later refinement if the
single-pivot motion looks too flat.

## Silhouette: boxy/geometric (revised from original sleek/organic)

Initial direction was smooth organic chrome curves. After reviewing
animatronic-endoskeleton reference blueprints, switched to a boxy,
geometric skull frame — square housings, flat panels, angular jaw.
Reads more mechanical/deliberate, and is also considerably easier to
model in CAD and 3D print than compound organic curves.

## Eyes: round ball-and-housing

Mechanical eyeball (sphere) set inside a square housing, visible
pupil/bearing detail. Chosen over glowing hollow horror-sockets and
flat boxy camera-lens eyes — keeps some expressiveness (round eye)
while staying consistent with the boxy frame (square housing).

## Jaw: upper plate + hinged lower jaw with segmented teeth block

Still single-pivot hinge + servo lever + spring return (see above),
but visual treatment updated to a grid of individual teeth rather
than a plain strip, matching the boxy/mechanical style.

## Open questions

- Finish/material — chrome vs matte vs mixed
- Eye optics — is the "ball" lit/LED, or just a static painted/machined sphere?
- Exact skull box proportions (width/height/depth ratios) and wall thickness
- Specific servo models + torque requirements (depends on final
  skull weight, which depends on material/print settings)
- How much panel-seam/exposed-mechanism detail on the boxy shell
