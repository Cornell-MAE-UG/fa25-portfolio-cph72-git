---
layout: project
title: "Hyperloop Pneumatic Dual-Pad Braking System Redesign"
description: A custom-designed pneumatic braking mechanism developed using CAD, FEA validation, and precision manufacturing.
image: /assets/images/brakes_assembly.jpeg
---

<style>
  h1.project-title, .page-title, h1 { text-align: center; }
</style>

<img src="{{ "/assets/images/brakes_assembly.jpeg" | relative_url }}" alt="Final Brake Assembly" width="600">

---

# Overview

This project involved the design, analysis, and manufacturing of a compact pneumatic brake system intended to provide reliable clamping force, structural rigidity, and repeatable operation. The system was designed with an emphasis on manufacturability, efficient force transmission, and mechanical robustness.

The project included the complete engineering workflow from initial concept generation and CAD modeling to finite element analysis (FEA), machining, assembly, and testing.

---
# Project Gallery

<style>
  .gallery-slider {
    position: relative;
    width: 100%;
    max-width: 640px;
    margin: 0 auto;
    overflow: hidden;
    border-radius: 10px;
    border: 1px solid #ccc;
  }
  .gallery-track {
    display: flex;
    transition: transform 0.4s ease;
  }
  .gallery-btn {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(0,0,0,0.5);
    color: #fff;
    border: none;
    font-size: 1.8rem;
    padding: 10px 16px;
    cursor: pointer;
    border-radius: 6px;
    z-index: 10;
  }
  .gallery-btn:hover { background: rgba(0,0,0,0.8); }
  .gallery-prev { left: 8px; }
  .gallery-next { right: 8px; }
  .gallery-dots {
    text-align: center;
    margin-top: 10px;
  }
  .gallery-dots span {
    display: inline-block;
    width: 10px; height: 10px;
    border-radius: 50%;
    background: #ccc;
    margin: 0 4px;
    cursor: pointer;
  }
  .gallery-dots span.active { background: #444; }
</style>

<div class="gallery-slider">
  <div class="gallery-track" id="galleryTrack">
    <div style="min-width: 100%; text-align: center; background: #111;">
      <img src="{{ "/assets/images/brakes_design.png" | relative_url }}" alt="CAD Model" style="height: 400px; object-fit: contain;">
      <p style="color: #fff; margin: 8px 0; font-weight: bold;">CAD Model</p>
    </div>
    <div style="min-width: 100%; text-align: center; background: #111;">
      <img src="{{ "/assets/images/ansys_mov.svg" | relative_url }}" alt="Ansys FEA" style="height: 400px; object-fit: contain;">
      <p style="color: #fff; margin: 8px 0; font-weight: bold;">FEA</p>
    </div>
    <div style="min-width: 100%; text-align: center; background: #111;">
      <img src="{{ "/assets/images/brakes_assembly.jpeg" | relative_url }}" alt="Final Assembly" style="height: 400px; object-fit: contain;">
      <p style="color: #fff; margin: 8px 0; font-weight: bold;">Final Assembly</p>
    </div>
  </div>
  <button class="gallery-btn gallery-prev" onclick="moveGallery(-1)">&#8249;</button>
  <button class="gallery-btn gallery-next" onclick="moveGallery(1)">&#8250;</button>
</div>
<div class="gallery-dots" id="galleryDots">
  <span class="active" onclick="goToSlide(0)"></span>
  <span onclick="goToSlide(1)"></span>
  <span onclick="goToSlide(2)"></span>
</div>

<script>
  let currentSlide = 0;
  const totalSlides = 3;

  function moveGallery(dir) {
    currentSlide = (currentSlide + dir + totalSlides) % totalSlides;
    updateGallery();
  }

  function goToSlide(index) {
    currentSlide = index;
    updateGallery();
  }

  function updateGallery() {
    document.getElementById('galleryTrack').style.transform = `translateX(-${currentSlide * 100}%)`;
    document.querySelectorAll('#galleryDots span').forEach((dot, i) => {
      dot.classList.toggle('active', i === currentSlide);
    });
  }
</script>

---

# Skills & Tools

- SolidWorks
- Excel
- ANSYS Mechanical
- Manufacturing Drawings
- Mechanical Design
- FEA through Ansys
- Pneumatic Systems
- Lathe and Mill Machining
- Off-The-Shelf Component Sourcing
- Engineering Documentation

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
      <img src="{{ "/assets/images/early_design.png" | relative_url }}" alt="Early CAD Design" width="300"><br>
      <img src="{{ "/assets/images/old_design_rails.png" | relative_url }}" alt="Old Design on Rails" width="300">
    </td>
    <td>
      <img src="{{ "/assets/images/brakes_design.png" | relative_url }}" alt="Brake CAD Assembly" width="300"><br>
      <img src="{{ "/assets/images/Brakes_Cad_w_rail.png" | relative_url }}" alt="Brakes on Rails" width="300">
    </td>
  </tr>
</table>
</div>

**Improvements:**
- Easier C-Bracket to manufacture
- New double-acting actuator that allows mountability
- Springs attached to plates still allow retraction

---

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
<table class="fea-table">
  <tr>
    <th>FOS Analysis</th>
    <th>Deformation Analysis</th>
  </tr>
  <tr>
    <td>
      <img src="{{ "/assets/images/FOS_brakes.png" | relative_url }}" alt="ANSYS FOS Analysis" width="300" style="display: block; margin-bottom: 16px;"><br>
      <img src="{{ "/assets/images/FOS_brakes_scale.png" | relative_url }}" alt="ANSYS FOS Scale" width="150">
    </td>
    <td>
      <img src="{{ "/assets/images/Ansys_image(new).jpg" | relative_url }}" alt="ANSYS Deformation Plot" width="300"><br>
      <img src="{{ "/assets/images/ansys_mov.svg" | relative_url }}" 
     alt="ANSYS Deformation Animation" 
     width="300" height="292">
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


<div style="text-align: center;">
  <img src="{{ "/assets/images/no_pads_assembly.jpg" | relative_url }}" alt="Partial Assembly" width="450" style="border: 1px solid #ccc; border-radius: 8px; padding: 12px;">
</div>

The components were machined from aluminum stock using manual mills and manual lathes. Operations included milling, turning, drilling, and tapping, with additional finishing operations such as chamfering and countersinking. Raw stock was cut to size using a bandsaw prior to machining. All components were machined to a tolerance of ±0.05 in, with over 20 shop hours invested in fabrication.

---

# Final Assembly Movement Demonstration

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
    padding: 18px 48px;
    background: #2c2c2c;
    color: #fff !important;
    border-radius: 6px;
    font-size: 1.4rem;
    font-weight: bold;
    text-decoration: none;
    border: 2px solid #555;
  }
  .video-watch-link:hover { background: #444; }
</style>

<div style="text-align: center;">
  <a class="video-watch-link" href="#" onclick="document.getElementById('videoModal').classList.add('active'); return false;">▶ Watch</a>
</div>

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

# Next Steps

With the mechanical brake assembly complete, focus has shifted to the pneumatic subsystem. 
This has involved mapping out all required pneumatic components, evaluating off-the-shelf component 
sourcing to maximize braking force within system constraints, and developing a working understanding 
of pneumatic circuit behavior. A housing carriage is also being designed to package all 
components within the pod's volume constraints.

Remaining steps include:
- Refine off-the-shelf pneumatic component sourcing to maximize braking capacity
- Assemble and integrate the pneumatic circuit
- Test pneumatic actuation and verify braking performance
- Design and finalize mounting for both the brake assembly and pneumatic carriage
- Detail drawings for all machined components



