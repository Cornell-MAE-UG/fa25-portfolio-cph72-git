---
layout: project
title: "Hyperloop Braking System Redesign"
description: A custom-designed pneumatic braking mechanism developed using CAD, FEA validation, and precision manufacturing.
---

# Pneumatic Dual-Pad Brake System

<img src="{{ "/assets/images/brakes_assembly.jpeg" | relative_url }}" alt="Final Brake Assembly" width="600">

---

# Overview

This project involved the design, analysis, and manufacturing of a compact pneumatic brake system intended to provide reliable clamping force, structural rigidity, and repeatable operation. The system was designed with an emphasis on manufacturability, efficient force transmission, and mechanical robustness.

The project included the complete engineering workflow from initial concept generation and CAD modeling to finite element analysis (FEA), machining, assembly, and testing.

---

# Design Objectives

- Develop a compact and reliable pneumatic braking mechanism
- Maximize clamping force while minimizing unnecessary mass
- Ensure repeatable engagement and release
- Design components for manufacturability and assembly
- Maintain structural rigidity under braking loads

---

# Design Process

The brake system was initially developed through iterative CAD modeling and mechanism evaluation. Special attention was given to actuator placement, pad alignment, spring return behavior, and assembly simplicity.

<div style="display: flex; justify-content: center;">
<table class="design-table">
  <tr>
    <th>Initial CAD Concepts</th>
    <th>Detailed Assembly Design</th>
  </tr>
  <tr>
    <td>
      <img src="{{ "/assets/images/early_design.png" | relative_url }}" alt="Early CAD Design" width="400"><br>
      <img src="{{ "/assets/images/old_design_rails.png" | relative_url }}" alt="Old Design on Rails" width="400">
    </td>
    <td>
      <img src="{{ "/assets/images/brakes_design.png" | relative_url }}" alt="Brake CAD Assembly" width="400"><br>
      <img src="{{ "/assets/images/Brakes_Cad_w_rail.png" | relative_url }}" alt="Brakes on Rails" width="400">
    </td>
  </tr>
</table>
</div>

**Improvements:**
- Easier C-Bracket to manufacture
- New double-acting mountable actuator
- Springs attached to plates still allow retraction
- Passed all preliminary Ansys tests

# Finite Element Analysis (FEA)

Finite element analysis was conducted in ANSYS to evaluate stress distribution, deformation, and structural integrity under expected loading conditions.

<style>
  .fea-table, .design-table { width: 100%; border-collapse: separate; border-spacing: 10px; }
  .fea-table td, .design-table td {
    border: 1px solid #ccc;
    border-radius: 8px;
    padding: 12px;
    vertical-align: top;
    text-align: center;
  }
  .fea-table th, .design-table th {
    border: 1px solid #ccc;
    border-radius: 8px;
    padding: 12px;
    text-align: center;
  }
</style>

<div style="display: flex; justify-content: center;">
<table class="design-table">
  <tr>
    <th>FOS Analysis</th>
    <th>Deformation Analysis</th>
  </tr>
  <tr>
    <td>
      <img src="{{ "/assets/images/FOS_brakes.png" | relative_url }}" alt="ANSYS FOS Analysis" width="400"><br>
      <img src="{{ "/assets/images/FOS_brakes_scale.png" | relative_url }}" alt="ANSYS FOS Scale" width="200">
    </td>
    <td>
      <img src="{{ "/assets/images/Ansys_image(new).jpg" | relative_url }}" alt="ANSYS Deformation Plot" width="400"><br>
      <img src="{{ "/assets/images/ansys_mov.svg" | relative_url }}" 
     alt="ANSYS Deformation Animation" 
     width="400" height="292">
    </td>
  </tr>
</table>
</div>

**Loads:**
- Braking force (150N calculated to stop pod in 5 seconds)
- Spring forces on brake plates and brake pad backing plates
- Supports forces (Screws)

**Results:**

The FEA results confirmed the structural integrity of the brake system under expected loading conditions. Maximum deformation was found to be 6.6465e-6 m (~0.0002 in), indicating an effectively rigid structure with negligible deflection during braking. The minimum factor of safety was 6.5058, well above the acceptable threshold, demonstrating a robust design with significant safety margin.

---

# Manufacturing & Assembly

Following the design validation process, the brake system components were manufactured and assembled using a combination of machining and standard fastening methods.

## Machined Components

## PUT DRAWINGS PHOTOS HERE
<img src="{{ "/assets/images/no_pads_assembly.jpg" | relative_url }}" alt="Partial Assembly" width="600">

Discussion of:
- Materials used
- Machining operations
- Manufacturing tolerances
- Challenges encountered during fabrication

---

## Final Assembly

<style>
  .video-modal-overlay {
    display: none;
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    background: rgba(0,0,0,0.75);
    z-index: 1000;
    justify-content: center;
    align-items: center;
  }
  .video-modal-overlay.active { display: flex; }
  .video-modal-box {
    position: relative;
    background: #111;
    border-radius: 10px;
    overflow: visible;
    width: 480px;
    max-width: 90%;
    padding: 12px;
  }
  .video-modal-close {
    position: absolute;
    top: -16px; right: -16px;
    width: 32px; height: 32px;
    border-radius: 50%;
    background: #fff;
    color: #111;
    font-size: 1rem;
    font-weight: bold;
    cursor: pointer;
    border: 2px solid #ccc;
    display: flex;
    align-items: center;
    justify-content: center;
    line-height: 1;
  }
  .video-modal-close:hover { background: #eee; }
  .video-watch-link {
    display: inline-block;
    margin-top: 8px;
    padding: 12px 24px;
    background: #2c2c2c;
    color: #fff !important;
    border-radius: 6px;
    font-size: 1.1rem;
    font-weight: bold;
    text-decoration: none;
    border: 2px solid #555;
  }
  .video-watch-link:hover { background: #444; }
</style>

<a class="video-watch-link" href="#" onclick="document.getElementById('videoModal').classList.add('active'); return false;">▶ Watch Brake Movement Demo</a>

<div id="videoModal" class="video-modal-overlay" onclick="if(event.target===this){closeVideo();}">
  <div class="video-modal-box">
    <button class="video-modal-close" onclick="closeVideo()">✕</button>
    <video id="modalVideo" controls muted controlslist="novolume" width="100%">
      <source src="{{ "assets/video/movement_vid(new).mp4" | relative_url }}" type="video/mp4">
    </video>
  </div>
</div>

<script>
  function closeVideo() {
    document.getElementById('videoModal').classList.remove('active');
    document.getElementById('modalVideo').pause();
  }
</script>

Description of the completed assembly and overall system integration.

---

# Results & Performance

The completed brake system successfully demonstrated reliable pneumatic actuation and repeatable braking behavior. Structural performance aligned with FEA expectations, and the final assembly maintained rigidity during operation.

Potential future improvements include:
- Weight optimization
- Improved pad alignment
- Increased manufacturing precision
- Enhanced mounting geometry

---
## Next Steps


---
# Skills & Tools

- SolidWorks
- ANSYS Mechanical
- Mechanical Design
- Finite Element Analysis (FEA)
- Pneumatic Systems
- CNC Machining
- Manual Machining
- Assembly & Testing
- Engineering Documentation

---

# Additional Media

## Project Gallery

| CAD Model | FEA | Final Assembly |
|---|---|---|
| <img src="{{ "/assets/images/brakes_design.png" | relative_url }}" alt="CAD Model" width="200"> | <img src="{{ "/assets/images/Ansys_image.jpg" | relative_url }}" alt="FEA" width="200"> | <img src="{{ "/assets/images/brakes_assembly.jpeg" | relative_url }}" alt="Final Assembly" width="200"> |

---

# Author

Connor Hyde  
Mechanical Engineering Student at Cornell University

[LinkedIn](https://www.linkedin.com/in/connorphyde/)
