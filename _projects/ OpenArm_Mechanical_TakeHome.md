---
layout: project
title: "OpenArm Mechanical Take Home - Connor Hyde"
description: "You are designing the mechanical exterior and structural integration for our robot
platform: the OpenArm 2.0 robotic arm (docs: docs.openarm.dev) and a mobile
manipulator that combines the arm with a wheeled mobile base. The arm carries 4
cameras (two wrist Arducams, one ceiling Arducam, one ZED stereo head) and routes
CAN FD wiring internally. The platform is used to collect teleoperation demonstrations
for robot learning, so the design must look like a clean, credible product while staying
serviceable and manufacturable in a small-shop / 3D-print + sheet-metal context."
image: /assets/images/shell.png
---

<style>
  h1.project-title, .page-title, h1 { text-align: center; }
</style>

<div style="text-align: center;">
  <img src="{{ "/assets/images/shell.png" | relative_url }}" alt="Final OpenArm Shell" width="600">
</div>

---

# 1. Industrial design concept

Before modeling, dimensions and joint motion were mapped directly onto reference imagery to establish the working envelope and range of motion ahead of CAD work.

<div style="display: flex; justify-content: center;">
<table class="design-table">
  <tr>
    <th>Dimensional and joint-motion analysis</th>
    <th>Chest housing and wiring reference</th>
  </tr>
  <tr>
    <td>
      <img src="{{ "/assets/images/rough_estimating.png" | relative_url }}" alt="Hand-annotated dimensional analysis" width="300">
    </td>
    <td>
      <img src="{{ "/assets/images/partial_sketch.png" | relative_url }}" alt="Chest housing and wiring reference annotation" width="300">
    </td>
  </tr>
</table>
</div>

Two directions were explored for the exterior. Direction A is fast, primitive-based blocking: each component approximated with the closest-fitting cylinder or box, placed quickly to validate the overall envelope and joint layout rather than to look finished. It has no surface refinement, splits, ventilation, or camera integration, it's a blocking pass, not a design.

<div style="text-align: center;">
  <img src="{{ "/assets/images/blocky_image.png" | relative_url }}" alt="Direction A: fast primitive blocking" width="450" style="border: 1px solid #ccc; border-radius: 8px; padding: 12px;">
  <p style="font-style: italic; margin-top: 8px;">Primitive-based envelope used to validate overall proportions and joint layout before committing to a refined shell.</p>
</div>

Direction B is a separately developed, more detailed CAD model of the same overall arm. It adds smooth filleted transitions between segments, tapered proportions from shoulder to wrist, ventilation slots over the actuator zones, and integrated camera housings at the chest and wrist. It reads as one unified product rather than a stack of separate parts.

<div style="text-align: center;">
  <img src="{{ "/assets/images/shell.png" | relative_url }}" alt="Direction B: refined, form-fitting shell" width="450" style="border: 1px solid #ccc; border-radius: 8px; padding: 12px;">
  <p style="font-style: italic; margin-top: 8px;">Final shell direction, with filleted transitions, ventilation slots over the actuator zones, and integrated camera housings at the chest and wrist.</p>
</div>

Direction B was carried forward. It takes more modeling effort, but it's the only one that actually satisfies the brief, service splits, heat venting, and camera integration are all real requirements Direction A doesn't address. Direction A's value was mainly as a fast, separate sanity check on overall proportions and joint layout, run in parallel with the more detailed modeling that produced Direction B.

---

# 2. Exterior CAD model (arm)

## Assumptions

- Reach (shoulder center to gripper tip) is approximately 606mm, based on published OpenArm specs.
- Internal actuator and component sizes were estimated from a reference photo on docs.openarm.dev, since exact internal CAD wasn't available.
- Actuator temperatures are assumed to stay within a safe range for PETG, full reasoning is in the Camera & Cable Integration section.
- The shop has printers large enough to produce all panels at their designed size.
- Joint rotation ranges are limited to roughly match human-arm motion, consistent with how the arm is trained via teleoperation.
- The gripper/hand assembly is kept as-is, since it already includes the friction material needed on the fingers.
- The base is assumed to intersect the bottom of the shoulder housing rather than the top, a simplification compared to OpenArm's demo video.
- Envelope shapes were sized up beyond initial estimates so the 5mm offset and 2.5mm shell would generate successfully; the resulting shell sits roughly 2.5mm beyond those original estimates.
- Panel splits are modeled at each joint transition, but exact fastener and snap-fit placement per panel wasn't finalized in this pass.
- Cameras mount to the top of the central piece and the wrist piece; if they end up too exposed, the next pass would add enclosures or reposition them.
- The ceiling Arducam is assumed to mount to the surrounding OpenArm Cell room framing rather than to the arm shell itself.
- Mounting bosses are assumed to align with the real frame's hole pattern, see Manufacturability for the fallback plan if they don't.

## Modeling process

The shell was built by first creating a simplified internal envelope using Fusion's joint constraints, to validate pose and proportions against the reference geometry. Once that was locked in, the envelope was offset 5mm and shelled to generate the working shell, then clearance cuts, camera openings, and ventilation slots were added on top. Given the time constraints, sketches and features were not fully dimensionally/geometrically constrained throughout the model, so the design isn't yet robust to edits the way a fully parametric model would be. With more time I'd go back through and fully constrain every sketch, so the model could be confidently resized or modified later without features breaking or shifting unexpectedly.

<div style="display: flex; justify-content: center;">
<table class="design-table">
  <tr>
    <th>Envelope with joint constraints</th>
    <th>Final arm shell</th>
  </tr>
  <tr>
    <td>
      <img src="{{ "/assets/images/joint_cad.png" | relative_url }}" alt="Envelope with Fusion joint constraints" width="300">
    </td>
    <td>
      <img src="{{ "/assets/images/shell.png" | relative_url }}" alt="Final arm shell" width="300">
    </td>
  </tr>
</table>
</div>

In addition to the arm shell, a simple lofted cover was modeled for the base pillar, the vertical structural support beneath the arm, concealing the existing MISUMI aluminum framing beneath a clean tapered shape. Unlike the arm shell, this piece has no joints or curved transitions to account for, so it was modeled directly as a single flat-sided loft rather than through the envelope/offset/shell process used for the arm. It's purely a cosmetic cover at this stage, not a structural part, the actual load-bearing support still comes from the aluminum framing underneath.

<div style="text-align: center;">
  <img src="{{ "/assets/images/base_shell.png" | relative_url }}" alt="Base pillar cover concept" width="350" style="border: 1px solid #ccc; border-radius: 8px; padding: 12px;">
  <p style="font-style: italic; margin-top: 8px;">Simple lofted base pillar cover, designed to conceal the existing MISUMI aluminum framing. Flat-sided geometry with no joints or cutouts, well suited to sheet metal fabrication.</p>
</div>

---

# 3. Camera & cable integration

All four cameras are addressed. The ZED stereo head can be mounted forward-facing on the central peice, clear of joint rotation. One wrist Arducam mounts on the gripper housing; the second is assumed to mirror it on the opposite side. The ceiling Arducam is assumed to mount to the surrounding OpenArm Cell room framing rather than the arm itself.

Cameras are externally mounted in this pass rather than recessed, simpler for now, though if I had more time I would designing housing featuring a recessed cutout that would protect them better and look more finished.

CAN FD wiring and power route through the shell's hollow interior, sized so internal components can pass through during assembly. Panels are intended to open via snap-fit and magnetic clasps for service access, defined as intent here rather than modeled in detail.

Heat dissipation relies on ventilation slots over each actuator zone plus the air gap built into the shell's offset, since actuators can reach 40-70°C under load against PETG's ~80°C limit. The slots were sized quickly to demonstrate the idea rather than from real airflow calculations, and they're currently open enough that wires could snag or work their way out, a finer mesh or smaller openings would fix that without losing the cooling benefit.

---

# 4. Mobile base + manipulator integration

This task wasn't attempted, time went to the design concept, CAD model, camera integration, and manufacturability sections instead. If continued, the approach would start with a footprint wide enough to keep the system's center of gravity within a safe margin when the arm is fully extended, likely wider than the arm's own base given its 4.1kg nominal payload and ~600mm reach. Batteries and compute would sit low in the base, both for protection and to keep the center of mass down, and the structural interface between arm and base would need to handle reaction torque across the arm's full range of motion, not just its static weight. See the closing section for how this fits into broader next steps.

---

# 5. Manufacturability & materials

The shell is 3D-printed PETG. Sheet metal didn't seem like a good fit for the curved, multi-segment shape, and injection molding's tooling cost only makes sense at much higher production volumes, so PETG felt like the practical choice for a small shop.

The one exception is the base pillar cover. It's a simple flat-sided shape with no curves or cutouts, so bent sheet metal seemed like a better, more durable fit there, and it could be made from a single flat pattern with a few bends.

Wall thickness is 2.5mm for the PETG shell, enough to resist warping while keeping print time reasonable. The sheet metal cover would use a thinner gauge, maybe 1-1.5mm, since it's not load-bearing.

Assembly mixes fasteners and snap-fits: snap-fits at panel seams for quick access to wiring and cameras, fasteners holding panels to the frame structurally. If a smoother finish is wanted, the panels could be wet-sanded afterward.

A couple things would likely need an outside vendor: threaded inserts for the PETG panels (printed threads wear out fast), and the actual sheet metal bending, since most small shops don't have a brake press.

---

# What I'd do with more time

The idea I'd prioritize first is rethinking the shell material entirely, moving toward a flexible, fabric-like outer covering instead of a rigid PETG shell. The concept is close to the robot wearing a fitted sweatshirt rather than a hard plastic case, a taut, slightly raised textile or coated-nylon layer stretched over the frame with no rigid panel seams at all. This would be inherently flexible across the joints rather than needing separate rigid panels that split at each one, naturally breathable, and since it sits slightly off the surface rather than against it, it would open up a built-in ventilation path underneath for actuator heat, similar in spirit to the air gap and vent slots in the current design, but achieved through the material itself rather than cut features. This is a separate concept from the PETG shell, not a refinement of it, and would be a genuine alternative direction worth prototyping.

Beyond that, with more time I would: design actual snap-fit or magnetic panel connections rather than leaving that as a stated intent, finalize camera mounting with recessed cutouts instead of external mounts, refine the base pillar cover into a more polished, less purely functional shape, complete task 4 (mobile base integration), explore alternative materials and processes beyond PETG and sheet metal, and validate that the shell's mounting bosses actually align with the real OpenArm frame rather than the assumed locations used here.

---

# Sources & tools

- [docs.openarm.dev](https://docs.openarm.dev/) — reference specifications, hardware documentation, and reference imagery for the OpenArm 2.0 platform.
- Fusion 360 — used to model the internal envelope, generate the shell via offset and shell operations, and produce the renders shown throughout this write-up.
- Claude (Anthropic) — used for general assistance throughout this project, including research and explanations, help organizing this write-up, and formatting it for GitHub.
