---
layout: project
title: Actuator Height/Weight Optimization
description: Design for lifting a weight the highest height
image: /assets/images/HW 5 Design.jpeg
---

**Objective** This project involved designing a planar lifting mechanism within a fixed 150 cm by 50 cm design space using a rigid bar, three pin supports with two mounted on the ground, and a linear actuator selected from an online industrial catalog using only its maximum force rating. The objective was to lift the maximum possible weight to the greatest achievable height while satisfying all geometric and support constraints. In the first phase, the bar was treated as a rigid body and a full static analysis was performed to determine the optimal mechanism geometry, actuator placement, and resulting lifting capacity. The final rigid-body mechanism was documented through force balance equations, moment equilibrium, and a detailed design drawing. In the second phase, the bar was reanalyzed as a flexible beam subject to transverse loading from both the applied weight and actuator force. Maximum beam deflection was computed under clearly stated assumptions, and an optimized beam cross-section and material were selected to limit vertical deflection to less than 2 percent of the beam length while minimizing mass. The final beam design was presented with supporting calculations and engineering drawings.

### a) Problem Definition  
Design a planar lifting mechanism within a 150 cm by 50 cm space using one bar, three pin supports, and a linear actuator to lift the maximum possible weight to the greatest possible height.

### Constraints and Objectives  
**Constraints:**  
- Design space limited to 150 cm (length) by 50 cm (height)  
- Exactly three pin supports, with two mounted on the ground  
- One linear actuator selected from the catalog using max force only  
- Bar and supports assumed rigid for static analysis  

**Objectives:**  
- Maximize the lifted weight  
- Maximize the vertical lifting height  

### Design Degrees of Freedom  
- Bar length and orientation  
- Location of the ground pins  
- Location of the actuator attachment on the bar  
- Choice of actuator from the catalog  

### Rigid-Bar Static Analysis (HW5)

#### Model and Assumptions
- Bar treated as a rigid body
- Ground pin at point A
- RSX actuator attached at \(x = 0.75\ \text{m}\)
- Load applied at the bar tip \(x = 1.58\ \text{m}\)
- RSX maximum actuator force:  
  \(F_{\text{act,max}} = 294\ \text{kN}\)
- Static equilibrium conditions applied:  
  \(\sum F_x = 0\), \(\sum F_y = 0\), \(\sum M_A = 0\)

#### b) HW 5 Analysis Method
A free body diagram of the bar was constructed including the actuator force, the lifted weight at the tip, and the reaction forces at the ground pin. Moment equilibrium was taken about point A to eliminate the unknown reaction forces and directly relate the actuator force to the lifted weight. The lifted mass was placed at the end of the bar to maximize its moment arm and therefore maximize the lifting capacity.

#### Final Outcome
Using the RSX actuator at its maximum rated force and applying moment equilibrium, the maximum liftable load was determined. This rigid-body static analysis defined the final geometry and loading configuration used for the beam deflection analysis in Part (a).

### Beam Deflection Analysis

#### Assumptions
- The bar behaves as a prismatic Euler–Bernoulli beam  
- Constant Young’s modulus \(E\) and second moment of area \(I\)  
- Small deflections, linear elastic material response  
- Fixed support at point A, so the beam is a cantilever  
- Self weight of the beam is neglected  
- Only the components of the external forces transverse to the beam are included  

Let
- Beam length: \(L = 1.58\ \text{m}\)  
- Actuator attachment from A: \(a = 0.75\ \text{m}\)  
- Transverse component of the lifted weight: \(W_\perp\) at \(x = L\)  
- Transverse component of the actuator force: \(F_\perp\) at \(x = a\)  

In my geometry the weight and actuator are essentially vertical, so  
\(W_\perp \approx W\) and \(F_\perp \approx 294\ \text{kN} = 2.94\times10^{5}\ \text{N}\).

#### Step 2 a) Analysis

For a cantilever beam, the tip deflection due to a single point load is known:

- Tip load \(W_\perp\) at \(x = L\):  
  \[
  \delta_W = \frac{W_\perp L^{3}}{3EI}
  \]

- Point load \(F_\perp\) at \(x = a\) from the fixed end:  
  \[
  \delta_F = \frac{F_\perp a^{2}(3L - a)}{6EI}
  \]

Using superposition, the total maximum deflection at the free end is

\[
\delta_{\max} = \delta_W + \delta_F
= \frac{W_\perp L^{3}}{3EI}
+ \frac{F_\perp a^{2}(3L - a)}{6EI}
\]

Substituting \(L = 1.58\ \text{m}\) and \(a = 0.75\ \text{m}\):

\[
\boxed{
\delta_{\max}
= \frac{1}{EI}\Big(1.315\,W_\perp + 0.374\,F_\perp\Big)
}
\]

This expression gives the maximum vertical deflection of my beam as a function of
the transverse load components, the material stiffness \(E\), and the section
moment of inertia \(I\).

