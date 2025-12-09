---
layout: project
title: Actuator Height/Weight Optimization
description: Design for lifting a weight the highest height
image: /assets/images/TOL-8674-RSX080-RSX096-no-background-600x541.png
---

## Objective

This project involved designing a planar lifting mechanism within a fixed 150 cm by 50 cm design space using a rigid bar, three pin supports with two mounted on the ground, and a linear actuator selected from an online industrial catalog using only its maximum force rating. The objective was to lift the maximum possible weight to the greatest achievable height while satisfying all geometric and support constraints. In the first phase, the bar was treated as a rigid body and a full static analysis was performed to determine the optimal mechanism geometry, actuator placement, and resulting lifting capacity. In the second phase, the bar was reanalyzed as a flexible beam subject to transverse loading from both the applied weight and actuator force. Maximum beam deflection was computed under clearly stated assumptions, and a beam cross-section and material were selected to limit vertical deflection.

---

### Step 1: Rigid Bar Analysis  
### a) Problem Definition, Constraints/Objectives, Degrees of Freedom

**Problem Definition:**  
Design a planar lifting mechanism that uses a linear actuator to lift a load within a 150 cm by 50 cm design space. The mechanism includes a bar that is initially assumed to be rigid.

**Constraints:**  
- Overall design space limited to 150 cm (length) by 50 cm (height)  
- Exactly three pin supports, with two mounted on the ground  
- One linear actuator selected from the catalog using its maximum force  
- Bar and supports assumed rigid for static analysis  

**Objectives:**  
- Maximize the lifted weight  
- Maximize the vertical lifting height  
- Keep the mechanism simple and lightweight  

**Degrees of Freedom (DOF):**  
The mechanism has **one degree of freedom**, defined by the motion of the rigid bar driven by the actuator.

### b) Static Analysis of the Rigid Bar

Treating the bar as rigid, I performed a simple static analysis:

- Used the 150 cm by 50 cm design window and the Pythagorean theorem to choose a bar length of 158 cm that fits inside the frame.  
- Drew a free body diagram with the RSX actuator force at 0.75 m from the ground pin and the load at the bar tip.  
- Took moments about the ground pin to relate the actuator force to the lifted load.  
- Applied the RSX maximum force of 294 kN to solve for the maximum allowable load at the tip, which is approximately 788 N (about 80 kg).

This analysis produced the final rigid bar configuration and maximum load used for the later beam deflection study.

### Final Beam Design (Flexible)

Rigid and flexible beam geometry used in the analysis:

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/Hw5Design.jpeg" width="500">
</p>

---

### Step 2: Beam (Flexible Bar) Analysis  
### a) Maximum Beam Deflection

Once flexibility is considered, the rigid bar becomes a beam subjected to two transverse forces:

1. The weight of the lifted load  
2. The transverse component of the actuator force  

**Assumptions:**

- Beam is prismatic and linearly elastic  
- Small deflection Euler–Bernoulli beam theory applies  
- Only transverse forces are considered  
- The bar behaves as a **simply supported beam** between the ground pin at A and the actuator connection  

For a simply supported beam with a transverse point load P located between the supports, the maximum deflection can be written in the standard form

δ_max = (P · a² · b²) / (3 · E · I · L)

where:  

- L is the distance between the two supports  
- a is the distance from the left support to the load  
- b is the distance from the right support to the load (b = L − a)  

In my mechanism, the two transverse forces are:

- W⊥ from the lifted weight  
- F⊥ from the actuator  

I treated these as equivalent transverse point loads acting between the supports and used superposition to obtain a combined expression for the maximum deflection. With my geometry (L = 1.58 m, a = 0.75 m) this leads to

δ_max = (1 / (E · I)) · (1.315 · W⊥ + 0.374 · F⊥)

This expression gives the maximum vertical deflection of the pinned beam as a function of the applied transverse loads, the beam stiffness, and the chosen cross section.

### Step 2b – Beam Design to Limit Deflection Below 2% of Length

**Requirement**

The vertical deflection of the flexible bar must satisfy

δ_max < 0.02 · L

Using the deflection expression from Step 2a,

δ_max = (1 / (E · I)) · (1.315 · W⊥ + 0.374 · F⊥)

the requirement can be written as a minimum required moment of inertia:

I_req > (1.315 · W⊥ + 0.374 · F⊥) / (0.02 · L · E)

**Chosen Beam**

To satisfy this, I selected a rolled wide-flange steel section **W150x13.5** with

- Material: structural steel, E = 200 GPa  
- Strong-axis moment of inertia:  
  Ix = 6.83 × 10⁻⁶ m⁴  

From the inequality above, my design load combination (W⊥ and F⊥ from Step 2a) gives a required inertia that is **less than** Ix, so the W150x13.5 beam keeps

δ_max < 0.02 · L  (δ_max < 0.0316 m for L = 1.58 m).

The W150x13.5 shape also has the smallest cross-sectional area (A = 1,730 mm²) and lowest mass per meter in the W150 family (13.5 kg/m). Therefore, among the steel W-sections I considered, it is a **very mass-efficient beam** that still meets the 2% deflection limit.

### Step 2c – Final Beam Choice

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/Hw12Design.jpeg" width="500">
</p>
---
