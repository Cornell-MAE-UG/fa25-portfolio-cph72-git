---
layout: project
title: Thermofluid System Analysis
description: Counter flow vs. Parallel flow Heat Exchangers
technologies: []
image: /assets/images/heat-exchanger-collage.jpg
---

Team Members: Connor Hyde and Andrew Peene
A heat exchanger is a device that transfers thermal energy between two fluids while keeping them physically separate. One fluid is hotter and releases heat, and the other is cooler and absorbs that heat. They move through different channels, such as tubes or plates, divided by a solid wall that conducts heat but prevents mixing. As they pass through the exchanger, the temperature difference between the fluids drives heat from the hotter stream to the colder one.
The way the fluids flow determines how the exchanger performs. In parallel flow, both fluids enter from the same side and travel in the same direction, so the temperature difference is highest at the start and drops off quickly. In counter-flow, the fluids travel in opposite directions, which keeps the temperature difference more consistent and improves overall heat transfer.
In general, a heat exchanger’s role is to transfer thermal energy efficiently for heating, cooling, or energy recovery in applications like power plants, refrigeration systems, car radiators, and a wide range of industrial processes.




## Data

### Counter Flow

| Run | State   | TC (°C) | TH (°C) | THE (°C) |
|-----|---------|---------|---------|----------|
| 1   | Initial | 2.1     | 28.0    | 22.0     |
| 1   | Final   | 11.3    | 10.0    | 23.1     |
| 2   | Initial | 7.0     | 21.0    | 21.5     |
| 2   | Final   | 13.2    | 11.5    | 19.0     |


### Parallel Flow

| Run | State   | TC (°C) | TH (°C) | THE (°C) |
|-----|---------|---------|---------|----------|
| 1   | Initial | 7.3     | 23.0    | 23.0     |
| 1   | Final   | 12.0    | 13.9    | 20.0     |
| 2   | Initial | 8.5     | 21.1    | 22.5     |
| 2   | Final   | 12.2    | 13.6    | 20.1     |


Analysis:
In the counter-flow setup, the cold fluid warmed up significantly in both trials, and the hot fluid cooled by a large amount, indicating strong heat transfer. Interestingly, the cold outlet temperature rose above the hot outlet temperature, which at first seemed to violate the second law of thermodynamics. After looking into it further, I learned that this can occur only in counter-flow exchangers. Because the two fluids move in opposite directions, the cold stream continually encounters hotter fluid upstream, allowing it to reach temperatures close to the hot inlet. This also explains why the effectiveness values were higher than those of the parallel-flow runs, reaching about 35 to 45 percent compared with 29 percent.
In the parallel-flow configuration, both fluids showed smaller temperature changes than in the counter-flow tests. The hot outlet temperature always stayed above the cold outlet temperature, and the temperature difference between the two streams dropped quickly along the exchanger. This leads to weaker heat transfer. Parallel flow has an inherent limitation: the fluids begin with their maximum temperature difference, but because they travel in the same direction, their temperatures converge quickly. As soon as this happens, the driving force for heat transfer falls off, resulting in lower effectiveness and more modest temperature changes.
Overall, counter-flow consistently produced larger temperature shifts and higher cold outlet temperatures, while parallel flow produced smaller changes and no temperature crossing. These outcomes match the expected thermal behavior of each configuration. Counter-flow preserves a strong temperature difference throughout the exchanger, enabling more complete heat transfer, whereas parallel flow loses its gradient early on, restricting performance. Both setups behaved exactly as theory predicts, clearly demonstrating the contrast between the two designs.







