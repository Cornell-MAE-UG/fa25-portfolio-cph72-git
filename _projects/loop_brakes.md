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

## Initial CAD Concepts

<img src="{{ "/assets/images/early_design.png" | relative_url }}" alt="Early CAD Design" width="600">

Description of the initial concept and what design decisions were explored.

---

## Detailed Assembly Design

<img src="{{ "/assets/images/brakes_design.png" | relative_url }}" alt="Brake CAD Assembly" width="600">
<img src="{{ "/assets/images/Brakes_Cad_w_rail.png" | relative_url }}" alt="Brakes on Rails" width="600">

Improvements:
- Easier C-Bracket to manufacture 
- New double-acting mountable actuator
- Springs attached to plates still allow retraction
- Passed all preliminary Ansys tests

# Finite Element Analysis (FEA)

Finite element analysis was conducted in ANSYS to evaluate stress distribution, deformation, and structural integrity under expected loading conditions.

## Factor of Safety Analysis

<img src="{{ "/assets/images/FOS_brakes.png" | relative_url }}" alt="ANSYS FOS Analysis" width="600">
<img src="{{ "/assets/images/FOS_brakes_scale.png" | relative_url }}" alt="ANSYS FOS Results" width="600">

Loads:
- Braking force (150N calculated to stop pod in 5 seconds)
- Spring forces on brake plates and brake pad backing plates
- Supports forces (Screws)

---

## Deformation Analysis

<img src="{{ "/assets/images/Ansys_image.jpg" | relative_url }}" alt="ANSYS Deformation Plot" width="600">
<img src="{{ "/assets/images/ansys_mov.svg" | relative_url }}" alt="ANSYS Deformation Animation" width="600">

Explanation of observed deformation and any resulting design iterations.

---

# Manufacturing & Assembly

Following the design validation process, the brake system components were manufactured and assembled using a combination of machining and standard fastening methods.

## Machined Components

## PUT DRAWINGS PHOTOS HERE
<img src="{{ "/assets/images/brakes_parts.jpg" | relative_url }}" alt="C-Bracket Top Plate and Brake Pad Backing Plate" width="600">
<img src="{{ "/assets/images/no_pads_assembly.jpg" | relative_url }}" alt="Partial Assembly" width="600">

Discussion of:
- Materials used
- Machining operations
- Manufacturing tolerances
- Challenges encountered during fabrication

---

## Final Assembly

<video controls width="600">
  <source src="{{ "/assets/video/shortened_brakes.MOV" | relative_url }}" type="video/mp4">
</video>

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
