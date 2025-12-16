---
layout: project
title: MAE 4272 Blade Design Project
description: Advanced Design Project
technologies: [Autodesk Fusion, Ansys Fluent, Matlab]
image: /assets/images/Blade.png
---
## Introduction

Our goal for this project was to design a wind turbine blade to extract power from oncoming wind in a wind tunnel. This project involved an analysis of the fluid mechanics on the blade, a structural analysis of the blade, manufacturing the blade, and an analysis of the overall performance of the blade. 

## Key Constraints
We had to implement a few key constraints on the design, operation, and conditions of the blade in order to make sure that the blade would operate safely and in a controlled testing environment. 

- Maximum blade length of 6"
- Fixed angular velocity
- Max RPM of 2000
- Wind in wind turbine follows Weibull probability distribution with parameters k = 5 and c = 5
- Blade compatible with a standard hub piece, 1 inch in radius,
- SG66043 airfoil

## Approach to Design
We decided on a few key universal variable values:
- Blade Length: 5.5 inches
- Ideal Wind Speed: 4.75 m/s
- Optimized Rotation Rate: 2000 rpm <br>
All of these initial design choices were made in order to maximize power production while staying within the boundaries of the constraints. The ideal wind speed was chosen as the mean of the weibull distribution and the subsequent rotation rate was chosen through an assumed standard tip speed ratio value of 6.<br>

We used the Blade Element Momentum theory to develop the relationship displayed below for the pitch angle at varying distances across the blade:<br>
<img src="{{ "assets/images/pitch.png" | relative_url }}" width="650">
The objective of these pitch angles are to ensure that the oncoming wind is hitting the airfoil at the angle of attack which optimizizes the aerodynamic lift to drag ratio.
<br>
Likewise, BEM theory was used to develop the following relationship for the chord length at varying distances along the blade:
<img src="{{ "assets/images/chord.png" | relative_url }}" width="650">
<br>
Once all of these values were obtained, we could create many 2D airfoil cross sections across the blade using the local pitch and chord values, and loft them to form the 3D blade model for printing<br>
![Profile Picture]({{ "assets/images/Blade.png" | relative_url }})

## My Main Contribution: Approach to Blade Testing 
Constructing the approach to analyze the performance of the blade was the section of the project which I led on. Although I helped throughout the process in the planning, design, testing, and post processing of data, the main piece which I led on was generating these key questions and strategies to assess the performance of the blade.

Key Questions:
- What is the blade performance at different wind speeds?
- What is the blade performance at different TSRs?
- At what oncoming velocity does the blade start free spinning?

Key Strategies:
- Observe Power, Cp, and qualitative notes at various wind speeds
- Increase voltage input into torque break in order to adjust RPM
- Ensure that the blade is operating within its rated parameters<br>

Ultimately, we wanted to generate graphs showing how the power output of the turbine changes for various angular velocities. These angular velocities are adjusted by adjusting the voltage input to the torque break, which adjusts the angular velocity of the wind turbine. Our goal was to produce 3 such graphs, for 3 different oncoming velocity speeds.

## Findings
![Profile Picture]({{ "assets/images/4.7.png" | relative_url }})<br>
- Optimal RPM: 1068.4
- optimal 𝜆 = 3.599
- Max Cp = 0.029
<br>

![Profile Picture]({{ "assets/images/5.6.png" | relative_url }})
- Optimal RPM: 1488.6
- optimal 𝜆 = 4.27
- Max Cp = 0.032
<br>

![Profile Picture]({{ "assets/images/6.8.png" | relative_url }})
- Optimal RPM: 1805.8
- optimal 𝜆 = 4.24
- Max Cp = 0.034<br>

## Physical Observations
A number of qualitative observations were made during data collection:
- the blade did not start free spinning, overcoming its internal friction, until the oncoming wind speed was at 4.75 m/s. This was surprising as this was the mean velocity it was designed for.
- The blade began vibrating and rattling at higher RPMs, drawing concerns of structural safety and possible impact on power production<br>

<img src="{{ "assets/images/sideview.png" | relative_url }}" width="650">
- Upon manufacturing, the blade was actually much thinner and "twistier" than we expected, since we did not internalize the values we input into the CAD, and ignored some physical intuition related to pitch and chord measurements.<br>

<img src="{{ "assets/images/frontview.png" | relative_url }}" width="650">
## Takeaways
The blade was able to spin and produce power at an expected level given the design conditions. Despite this, we were surprised that the blade did not perform optimally at the expected velocity that it was designed for, but rather its Cp continuously increased as the oncoming wind speed increased. In the future, we might want to refine our models to take into account wake rotation and more precise physics. We would also want to consider the ease of manufacturing of our design, based on how much twist is in our blade and how thing our blade is. Simplifying these design choices may make for more realistic engineering. 

