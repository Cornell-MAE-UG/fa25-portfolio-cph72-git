---
layout: project
title: Actuator Height/Weight Optimization
description: Design for lifting a weight the highest height
image: /assets/images/TOL-8674-RSX080-RSX096-no-background-600x541.png
---

<style>
  .section-divider {
    border: none;
    border-top: 1px solid #ddd;
    margin: 36px 0;
  }
  .eq-box {
    background: #f7f7f7;
    border-left: 3px solid #aaa;
    border-radius: 4px;
    padding: 12px 20px;
    margin: 16px 0;
    font-family: monospace;
    font-size: 1rem;
  }
  .param-list {
    margin: 8px 0 16px 20px;
    line-height: 2;
  }
</style>

# Overview

This project involved designing a planar lifting mechanism within a fixed 150 cm × 50 cm design space using a rigid bar, three pin supports, and a linear actuator selected from an industrial catalog. The objective was to lift the maximum possible weight to the greatest achievable height while satisfying all geometric and support constraints.

The project was completed in two phases. In the first, the bar was treated as rigid and a full static analysis determined the optimal geometry, actuator placement, and lifting capacity. In the second, the bar was reanalyzed as a flexible beam under transverse loading, and a cross-section and material were selected to limit deflection.

<hr class="section-divider">

# Phase 1 — Rigid Bar Analysis

## Problem Definition

**Design space:** 150 cm × 50 cm

**Constraints:**
- Exactly three pin supports, two mounted on the ground
- One linear actuator selected from catalog by maximum force rating
- Bar and supports assumed rigid for static analysis

**Objectives:**
- Maximize the lifted weight
- Maximize the vertical lifting height
- Keep the mechanism simple and lightweight

**Degrees of Freedom:** The mechanism has one degree of freedom, defined by the rotation of the rigid bar driven by the actuator.

## Static Analysis

Using the 150 cm × 50 cm design window and the Pythagorean theorem, a bar length of 158 cm was selected to fit within the frame. A free body diagram was drawn with the RSX actuator force applied 0.75 m from the ground pin and the load at the bar tip. Taking moments about the ground pin and applying the RSX maximum force of 294 kN gives a maximum tip load of approximately **788 N (~80 kg)**.

<div style="text-align: center; margin: 28px 0;">
  <img src="{{ site.baseurl }}/assets/images/hw5design.jpeg" width="500"
       style="border: 1px solid #ccc; border-radius: 8px; padding: 8px;">
  <p style="margin-top: 8px; font-size: 0.9rem; color: #666;">Figure 1 — Rigid and flexible beam geometry used in the analysis</p>
</div>

<hr class="section-divider">

# Phase 2 — Flexible Beam Analysis

## 2a. Maximum Beam Deflection

When flexibility is introduced, the bar becomes a beam subjected to two transverse forces: the weight of the lifted load and the transverse component of the actuator force.

**Assumptions:**
- Prismatic, linearly elastic beam
- Small-deflection Euler–Bernoulli beam theory
- Only transverse forces considered
- Bar behaves as a simply supported beam between the ground pin and actuator connection

For a simply supported beam with a transverse point load P, maximum deflection takes the standard form:

<div class="eq-box">
  δ_max = (P · a² · b²) / (3 · E · I · L)
</div>

<div class="param-list">
  <strong>L</strong> — distance between supports<br>
  <strong>a</strong> — distance from left support to load<br>
  <strong>b</strong> — distance from right support to load (b = L − a)
</div>

Applying superposition for both transverse forces with the mechanism geometry (L = 1.58 m, a = 0.75 m):

<div class="eq-box">
  δ_max = (1 / (E · I)) · (1.315 · W⊥ + 0.374 · F⊥)
</div>

## 2b. Beam Design to Limit Deflection

**Requirement:** δ_max < 0.02 · L

Rearranging the deflection expression gives a minimum required moment of inertia:

<div class="eq-box">
  I_req > (1.315 · W⊥ + 0.374 · F⊥) / (0.02 · L · E)
</div>

**Selected Section: W150×13.5**

- Material: Structural steel, E = 200 GPa
- Strong-axis moment of inertia: I_x = 6.83 × 10⁻⁶ m⁴
- Cross-sectional area: A = 1,730 mm²
- Mass per meter: 13.5 kg/m

The required inertia from the loading conditions falls below I_x, confirming the W150×13.5 keeps deflection within the 2% limit (δ_max < 31.6 mm for L = 1.58 m). Among the W150 family, this section also has the smallest area and lowest mass per meter, making it the most mass-efficient choice that still satisfies the deflection requirement.

## 2c. Final Beam Design

<div style="text-align: center; margin: 28px 0;">
  <img src="{{ site.baseurl }}/assets/images/Hw12Design.jpeg" width="500"
       style="border: 1px solid #ccc; border-radius: 8px; padding: 8px;">
  <p style="margin-top: 8px; font-size: 0.9rem; color: #666;">Figure 2 — Final flexible beam design</p>
</div>
