---
layout: project
title: Thermofluid System Analysis
description: Counter flow vs. Parallel flow Heat Exchangers
image: /assets/images/heat-exchanger-collage.jpg
---

<style>
  .thermo-table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 6px;
    margin: 16px 0 28px 0;
  }
  .thermo-table td, .thermo-table th {
    border: 1px solid #ccc;
    border-radius: 6px;
    padding: 10px 14px;
    text-align: center;
  }
  .thermo-table th {
    background-color: #f0f0f0;
    font-weight: 700;
  }
  .section-divider {
    border: none;
    border-top: 1px solid #ddd;
    margin: 36px 0;
  }
</style>

<div style="text-align: center; margin-bottom: 8px;">
  <em>Connor Hyde &amp; Andrew Peene</em>
</div>

<div style="text-align: center; margin: 24px 0;">
  <img src="{{ "/assets/images/heat-exchanger-collage.jpg" | relative_url }}" 
       alt="Heat Exchanger Setup" 
       width="600" 
       style="border: 1px solid #ccc; border-radius: 8px; padding: 8px;">
</div>

<hr class="section-divider">

# Overview

A heat exchanger transfers thermal energy between two fluids while keeping them physically separate. One fluid releases heat and the other absorbs it as they pass through separate channels divided by a conductive wall. The temperature difference between the streams drives heat transfer from the hotter fluid to the cooler one.

The flow configuration determines how effectively this transfer occurs. In **parallel flow**, both fluids enter from the same side and travel in the same direction — the temperature difference is highest at the inlet and drops off quickly. In **counter-flow**, the fluids travel in opposite directions, maintaining a more consistent temperature difference throughout and enabling more complete heat transfer.

Heat exchangers are used across a wide range of applications including power plants, refrigeration systems, car radiators, and industrial processes.

<hr class="section-divider">

# Experimental Data

### Counter Flow

<table class="thermo-table">
  <tr>
    <th>Run</th><th>State</th><th>T<sub>C</sub> (°C)</th><th>T<sub>H</sub> (°C)</th><th>T<sub>HE</sub> (°C)</th>
  </tr>
  <tr><td>1</td><td>Initial</td><td>2.1</td><td>28.0</td><td>22.0</td></tr>
  <tr><td>1</td><td>Final</td><td>11.3</td><td>10.0</td><td>23.1</td></tr>
  <tr><td>2</td><td>Initial</td><td>7.0</td><td>21.0</td><td>21.5</td></tr>
  <tr><td>2</td><td>Final</td><td>13.2</td><td>11.5</td><td>19.0</td></tr>
</table>

### Parallel Flow

<table class="thermo-table">
  <tr>
    <th>Run</th><th>State</th><th>T<sub>C</sub> (°C)</th><th>T<sub>H</sub> (°C)</th><th>T<sub>HE</sub> (°C)</th>
  </tr>
  <tr><td>1</td><td>Initial</td><td>7.3</td><td>23.0</td><td>23.0</td></tr>
  <tr><td>1</td><td>Final</td><td>12.0</td><td>13.9</td><td>20.0</td></tr>
  <tr><td>2</td><td>Initial</td><td>8.5</td><td>21.1</td><td>22.5</td></tr>
  <tr><td>2</td><td>Final</td><td>12.2</td><td>13.6</td><td>20.1</td></tr>
</table>

<hr class="section-divider">

# Analysis

**Counter-flow** produced strong heat transfer in both trials. The cold fluid warmed significantly while the hot fluid cooled by a large margin. Notably, the cold outlet temperature rose above the hot outlet temperature — something that initially appears to violate the second law of thermodynamics. This phenomenon is actually unique to counter-flow exchangers: because the two fluids move in opposite directions, the cold stream continuously encounters hotter fluid upstream, allowing it to approach temperatures near the hot inlet. This sustained temperature gradient resulted in effectiveness values of roughly 35–45%, noticeably higher than the parallel-flow results.

**Parallel-flow** produced smaller temperature changes in both fluids across all runs. The hot outlet temperature always remained above the cold outlet, and no temperature crossing occurred. This is an inherent limitation of parallel flow — both fluids start with the largest possible temperature difference at the inlet, but as they travel in the same direction their
