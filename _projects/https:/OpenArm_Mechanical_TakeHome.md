---
layout: project
title: "OpenArm Mechanical Take Home - Connor Hyde"
description: You are designing the mechanical exterior and structural integration for our robot
platform: the OpenArm 2.0 robotic arm (docs: docs.openarm.dev) and a mobile
manipulator that combines the arm with a wheeled mobile base. The arm carries 4
cameras (two wrist Arducams, one ceiling Arducam, one ZED stereo head) and routes
CAN FD wiring internally. The platform is used to collect teleoperation demonstrations
for robot learning, so the design must look like a clean, credible product while staying
serviceable and manufacturable in a small-shop / 3D-print + sheet-metal context.
image:
---

## 1. Industrial design concept

Two directions were explored for the exterior. Direction A is fast, primitive-based blocking: each component approximated with the closest-fitting cylinder or box, placed quickly to validate the overall envelope and joint layout rather than to look finished. It has no surface refinement, splits, ventilation, or camera integration, it's a blocking pass, not a design.

Direction B builds on that same envelope but adds smooth filleted transitions between segments, tapered proportions from shoulder to wrist, ventilation slots over the actuator zones, and integrated camera housings at the chest and wrist. It reads as one unified product rather than a stack of separate parts.

Direction B was carried forward. It takes more modeling effort, but it's the only one that actually satisfies the brief, service splits, heat venting, and camera integration are all real requirements Direction A doesn't address. Direction A's value was mainly as a fast sanity check on proportions and joint layout before investing time in the refined surface.

## 2. Exterior CAD model (arm)

### Assumptions

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

### Modeling process

The shell was built by first creating a simplified internal envelope using Fusion's joint constraints, to validate pose and proportions against the reference geometry. Once that was locked in, the envelope was offset 5mm and shelled to generate the working shell, then clearance cuts, camera openings, and ventilation slots were added on top.

((PHOTO OF IT))

## 3. Camera & cable integration

All four cameras are addressed in the design. The ZED stereo head mounts forward-facing on the chest housing, clear of any joint that could rotate into its view. One wrist Arducam mounts directly on the gripper housing with a clear line of sight to the working area; the second is assumed to mirror that mount on the opposite side. The ceiling Arducam is assumed to mount to the surrounding OpenArm Cell room framing rather than the arm itself, consistent with how OpenArm documents its standardized evaluation setup.

In this pass, all cameras are externally mounted to the outer shell rather than recessed behind a cutout. That keeps things simpler for now and leaves the camera fully visible for alignment, but a recessed mount with just the lens exposed would give better protection and a more finished look with more time.

CAN FD wiring and power route through the shell's hollow interior, which was sized with enough clearance that all internal components can pass through during assembly, rather than needing the shell built around an already-assembled arm. Panel access is intended to use a mix of snap-fit and magnetic clasps at the seams, allowing tool-less opening for service, though this was defined as design intent rather than modeled in detail given the time available.

Heat dissipation relies on two strategies working together: ventilation slots cut directly into the shell over each actuator zone for convective cooling, and a consistent air gap, built into the 5mm offset, that keeps the shell wall from touching the actuator housings directly. This matters because actuators can reach roughly 40-70°C under sustained load, while PETG's glass transition point is around 80°C, a fairly tight margin that the venting and air gap are meant to protect.

## 4. Mobile base + manipulator integration

This task wasn't attempted, time went to the design concept, CAD model, camera integration, and manufacturability sections instead. If continued, the approach would start with a footprint wide enough to keep the system's center of gravity within a safe margin when the arm is fully extended, likely wider than the arm's own base given its 4.1kg nominal payload and ~600mm reach. Batteries and compute would sit low in the base, both for protection and to keep the center of mass down, and the structural interface between arm and base would need to handle reaction torque across the arm's full range of motion, not just its static weight.

## 5. Manufacturability & materials

The shell is designed for 3D-printed PETG construction. Sheet metal doesn't suit the shell's curved, multi-segment geometry, and injection molding's tooling cost only makes sense at production volumes well beyond this platform's scale, so PETG is the practical fit, it prints reliably without needing an enclosed chamber, which matters in a small-shop context.

The one exception is the base pillar cover, a simple flat-sided, lofted shape with no curves or cutouts to accommodate. That geometry suits bent sheet metal better, it's more durable where the base takes repeated handling, and it can be made from a single flat pattern with a few straight bends.

Wall thickness is 2.5mm for the PETG shell, thick enough to resist warping under repeated servicing while keeping print time and cost reasonable. The sheet metal base cover would use a thinner 1-1.5mm aluminum gauge, since it's a non-structural cosmetic piece. Draft allowance doesn't apply since nothing here is molded or cast, but bend allowance does apply to the sheet metal cover's fold lines.

Assembly mixes fasteners and snap-fits by function rather than uniformly. Snap-fits sit at the seams between shell panels for quick, tool-less access to wiring and camera connections, while fasteners hold each panel rigidly to the frame underneath. The base cover uses fasteners only, since it's rarely opened. If a smoother finish than what comes off the printer is wanted, the panels can be wet-sanded afterward, a low-cost step that needs no extra equipment.

A few things would need to go to an outside vendor: threaded inserts for the PETG panels, since printed plastic threads wear out fast under repeated fastening, the actual bending of the sheet metal cover, since most small shops don't have a brake press on hand, and custom-machined adapter brackets if the real frame's mounting holes don't line up with the boss locations assumed here.
