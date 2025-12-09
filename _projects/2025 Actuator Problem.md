---
layout: project
title: Actuator Height/Weight Optimization
description: Design for lifting a weight the highest height
image: /assets/images/HW5Design.jpeg
---

## Objective

This project involved designing a planar lifting mechanism within a fixed 150 cm by 50 cm design space using a rigid bar, three pin supports with two mounted on the ground, and a linear actuator selected from an online industrial catalog using only its maximum force rating. The objective was to lift the maximum possible weight to the greatest achievable height while satisfying all geometric and support constraints. In the first phase, the bar was treated as a rigid body and a full static analysis was performed to determine the optimal mechanism geometry, actuator placement, and resulting lifting capacity. In the second phase, the bar was reanalyzed as a flexible beam subject to transverse loading from both the applied weight and actuator force. Maximum beam deflection was computed under clearly stated assumptions, and a beam cross-section and material were selected to limit vertical deflection.

---

### a) Problem Definition

Design a planar lifting mechanism within a 150 cm by 50 cm space using one bar, three pin supports, and a linear actuator to lift the maximum possible weight to the greatest possible height.

---

### Constraints and Objectives

**Constraints**
- Design space limited to 150 cm (length) by 50 cm (height)
- Exactly three pin supports, with two mounted on the ground
- One linear actuator selected from the catalog using max force only
- Bar and supports assumed rigid for static analysis

**Objectives**
- Maximize the lifted weight
- Maximize the vertical lifting height

---

### Design Degrees of Freedom

- Bar length and orientation
- Location of the ground pins
- Location of the actuator attachment on the bar
- Choice of actuator from the catalog

---

### Rigid-Bar Static Analysis (HW5)

#### Model and Assumptions

- Bar treated as a rigid body  
- Ground pin at point A  
- RSX actuator attached at x = 0.75 m  
- Load applied at the bar tip x = 1.58 m  
- RSX maximum actuator force: 294 kN  
- Static equilibrium conditions applied:  
  ΣFx = 0, ΣFy = 0, ΣMA = 0  

#### HW5 Analysis Method

A free body diagram of the bar was constructed including the actuator force, the lifted weight at the tip, and the reaction forces at the ground pin. Moment equilibrium was taken about point A to eliminate the unknown reaction forces and directly relate the actuator force to the lifted weight. The lifted mass was placed at the end of the bar to maximize its moment arm and therefore maximize the lifting capacity.

#### Final Outcome

Using the RSX actuator at its maximum rated force and applying moment equilibrium, the maximum liftable load was determined. This rigid-body static analysis defined the final geometry and loading configuration used for the beam deflection analysis.

---

### Beam Deflection Analysis

#### Assumptions

- Beam follows Euler–Bernoulli beam theory  
- Constant Young’s modulus E and moment of inertia I  
- Small deflections and linear elastic behavior  
- Fixed support at point A (cantilever beam)  
- Beam self-weight neglected  
- Only transverse load components considered  

Let:
- Beam length L = 1.58 m  
- Actuator location a = 0.75 m  
- Transverse weight at the tip W⊥  
- Transverse actuator force F⊥ ≈ 294,000 N  

---

### Final Beam Design (Flexible)

![HW5 Design](/assets/images/Hw5Design.jpeg)

---

### Step 2a – Maximum Beam Deflection

For a cantilever beam:

Tip load deflection at x = L:  
δW = (W⊥ · L³) / (3 · E · I)

Point load deflection at x = a:  
δF = (F⊥ · a² · (3L − a)) / (6 · E · I)

Using superposition, total maximum deflection:

δmax = (W⊥ · L³) / (3 · E · I)  
  + (F⊥ · a² · (3L − a)) / (6 · E · I)

Substituting L = 1.58 m and a = 0.75 m:

δmax = (1 / (E · I)) · (1.315 · W⊥ + 0.374 · F⊥)

This equation gives the maximum vertical deflection of the beam as a function of the transverse load components, material stiffness, and cross-section.

### Step 2b – Beam Selection for Stiffness and Mass Efficiency

The flexible bar was selected as a rolled wide flange steel section **W150x13.5**.  
The material is structural steel with Young’s modulus:

E = 200 GPa

From the steel section table, the properties of the W150x13.5 beam are:

Area:
A = 1,730 mm²

Strong-axis moment of inertia:
Ix = 6.83 × 10⁶ mm⁴ = 6.83 × 10⁻⁶ m⁴

From Step 2a, the maximum beam deflection is:

δmax = (1 / (E · I)) · (1.315 · W⊥ + 0.374 · F⊥)

The allowable deflection is limited to 2 percent of the beam length:

δallow = 0.02 · L  
δallow = 0.02 · 1.58  
δallow = 0.0316 m

Applying the deflection limit:

(1 / (E · I)) · (1.315 · W⊥ + 0.374 · F⊥) ≤ 0.0316

Substituting E = 200 × 10⁹ Pa and I = 6.83 × 10⁻⁶ m⁴:

1.315 · W⊥ + 0.374 · F⊥ ≤ 4.32 × 10⁴ N

This condition is satisfied for the operating actuator force and lifted weight in this design, so the vertical deflection of the W150x13.5 beam remains below 2 percent of the beam length. Since W150x13.5 is the lightest available W150 section, it is the most mass-efficient beam that satisfies the deflection requirement.

#### Step 2 C) Final Design:
![HW12 Design](/assets/images/Hw12Design.jpeg)

---
