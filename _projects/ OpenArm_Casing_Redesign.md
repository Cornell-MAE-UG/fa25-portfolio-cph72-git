---
layout: project
title: "OpenArm Casing Redesign – Robotics Center of Silicon Valley"
description: "Ground-up exterior redesign of the OpenArm 2.0 bimanual robotic arm: angular consumer aesthetics, thermal management, integrated cable locking, and 3D-print production optimized to a single day."
image: /assets/images/openarm/openarm_V2-2.jpeg
---

<style>
  h1.project-title, .page-title, h1 { text-align: center; }
</style>

<div style="text-align: center;">
  <img src="{{ "/assets/images/openarm/openarm_V2-2.jpeg" | relative_url }}" alt="Finished OpenArm 2.0 with new casing at Robotics Center open house" width="600">
</div>

---

[Robotics Center of Silicon Valley](https://roboticscenter.com) (YC S25) builds bimanual robotic arms used to collect teleoperation demonstrations for robot learning. The flagship product is the OpenArm 2.0: a two-arm system that researchers and developers use to teach robots manipulation skills by showing them directly. The arm needs to look like a credible product to clients and investors while staying manufacturable in a small-shop environment.

I joined as a Robotics Engineering Intern in summer 2026. The first-generation arm left motors, frame, and wiring fully exposed. My main project was a ground-up redesign of the exterior casing.

---

# How it started: the take-home design exercise

The internship started with a take-home mechanical design challenge: design an exterior shell for the OpenArm 2.0 using only the published specs at docs.openarm.dev, with no access to internal CAD.

Two directions were explored. Direction A was fast primitive-based blocking — cylinders and boxes to validate the overall envelope. Direction B added filleted transitions, ventilation slots, and integrated camera housings, and was the only one that actually satisfied the brief's real requirements: service splits, heat venting, and camera integration. Direction B carried forward, modeled in Fusion 360 using an offset-and-shell workflow over a joint-constrained internal envelope.

<div style="display: flex; justify-content: center;">
<table class="design-table">
  <tr>
    <th>Direction A: envelope blocking</th>
    <th>Direction B: refined shell</th>
  </tr>
  <tr>
    <td>
      <img src="{{ "/assets/images/blocky_image.png" | relative_url }}" alt="Direction A primitive blocking" width="300">
    </td>
    <td>
      <img src="{{ "/assets/images/shell.png" | relative_url }}" alt="Direction B refined shell" width="300">
    </td>
  </tr>
</table>
</div>

The take-home became the basis for the internship offer. The summer project took the ideas from that exercise and built actual production hardware around them.

---

# Summer project: full casing redesign

## The starting point

V1 had no exterior casing — raw motors, bare aluminum frame, and loose cables running between every joint. It worked, but it didn't look like a product.

<div style="text-align: center;">
  <img src="{{ "/assets/images/openarm/OpenArm_V1.jpeg" | relative_url }}" alt="OpenArm V1 with no exterior casing" width="500" style="border: 1px solid #ccc; border-radius: 8px; padding: 12px;">
  <p style="font-style: italic; margin-top: 8px;">V1: functional but fully exposed — bare motors, aluminum frame, and unmanaged cable runs between joints.</p>
</div>

## Design direction

The redesign had two constraints: match the company's visual identity, and solve real engineering problems. Every decision tied to one of those two goals.

The geometry uses sharp, angular faceted surfaces to mirror the RC logo's aesthetic — the same visual language the company uses across its branding. Company identity is embedded directly into the physical form of the chest piece. The result is a 16-part casing system printed in PLA Matte black.

Four engineering problems drove the design:

**Thermal management.** Ventilation slots run over each actuator zone. The DAMIAO BLDC (brushless DC) motors can reach 40–70°C under sustained load against PLA's deflection threshold, so the slots create a direct airflow path over the hottest surfaces without requiring a fan.

**Cable locking.** An integrated cable-locking mechanism at each joint prevents connector disconnections during operation — a recurring failure mode on V1 that would drop the arm mid-task. The mechanism holds cables in place without requiring tools to service.

**Hardware coverage.** Panels close out all exposed frame and motor faces, protecting internal components from debris and contact.

**FEA (finite element analysis) validation.** Shell wall thickness was validated against regular impact loads using FEA before committing to a print run, confirming acceptable stress margins at the selected wall thickness.

## Print optimization

All 16 parts print in PLA Matte. Print orientation was chosen to align layer lines along the primary load axis for each panel — critical on any FDM (fused deposition modeling) print, where cross-layer bonds are the weak direction. The full arm fits across two Bambu Lab print plates, packed to maximize bed utilization.

<div style="text-align: center;">
  <img src="{{ "/assets/images/openarm/bambu_layout.png" | relative_url }}" alt="Bambu Studio layout showing all 16 casing panels across two print plates" width="600" style="border: 1px solid #ccc; border-radius: 8px; padding: 12px;">
  <p style="font-style: italic; margin-top: 8px;">Optimized Bambu Studio bed layout for a full arm set. Two plates, all 16 parts, total production time cut to 16 hours.</p>
</div>

Print-ready bed files were prepared for every robot variant the company ships — Anvil, Manufacturer, OA 1.0/2.0, and M1 — reducing future reproduction to loading a saved plate and hitting print. All associated CAD files (STEP and STL) were organized across every variant into a clean, maintainable file structure.

## Result

<div style="text-align: center;">
  <img src="{{ "/assets/images/openarm/openarm_V2.jpg" | relative_url }}" alt="Finished OpenArm 2.0 with new casing at Robotics Center open house" width="500" style="border: 1px solid #ccc; border-radius: 8px; padding: 12px;">
  <p style="font-style: italic; margin-top: 8px;">V2 at the Robotics Center open house. Angular branded geometry, ventilation slots over each actuator zone, and braided cable sleeves throughout.</p>
</div>

---

# Production and quality control

Five OpenArm shipments were prepared over the summer, coordinating with the business team on each deadline. Every unit went through a pre-shipment assembly inspection — catching and resolving errors before they reached customers.

For the M1 robot variant, raw PLA prints required finishing before the company's first open house. Bondo body filler was applied and sanded to achieve a smooth, consumer-grade surface ahead of paint. Braided cable sleeves were added across the full robot lineup, improving the appearance and perceived build quality of every unit in the shop.

---

# Additional work

**Custom camera mount.** A specific client requested a non-standard camera configuration. A custom mount was designed and printed to fulfill the request.

**Sensor calibration rig.** A testing fixture was designed to let a teammate perform AS5600 magnetic encoder calibrations quickly and repeatably, replacing an ad-hoc process.

**Injection molding evaluation.** Alternative manufacturing methods were researched and evaluated for the casing at higher production volumes, including an injection molding feasibility assessment.

**Events.** Demonstrated the M1 and Aloha arm teleoperation to 450 attendees across open houses and private events — clients, investors, and fellow startups.

---

# Sources & tools

- [docs.openarm.dev](https://docs.openarm.dev/) — OpenArm 2.0 hardware reference and specifications
- Onshape — primary CAD tool for the V2 casing design
- Bambu Studio — print preparation and bed layout optimization
- Fusion 360 — used for the take-home design exercise
