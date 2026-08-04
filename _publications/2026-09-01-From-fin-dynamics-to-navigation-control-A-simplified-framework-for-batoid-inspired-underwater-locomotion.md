---
title: "From fin dynamics to navigation control: A simplified framework for batoid-inspired underwater locomotion"
collection: publications
category: manuscripts
permalink: /publication/2026-09-01-From-fin-dynamics-to-navigation-control-A-simplified-framework-for-batoid-inspired-underwater-locomotion
excerpt: 'The design of a simple 6-axis model-independent control strategy for bathoid inspired robots. The low level velocity controller based on simplified dynamics allowes higher level controllers to act on the robot steering it for navigation.'
date: 2026-09-01
venue: 'Ocean Engineering'
paperurl: 'https://doi.org/10.1016/j.oceaneng.2026.127077'
bibtexurl: 'https://ScudeT.github.io/files/maui/OE-2026-09/OE-2026-09.bib'
giturl: 'https://github.com/ScudeT/Maui'
---

![helix](https://ScudeT.github.io/files/maui/OE-2026-09/video1.mp4)

## Highlights

* Hydrodynamic fin–body parametrization enables model-free 6-DOF control of ray AUV
* Fully onboard cascaded control: quaternion attitude, depth and target reach
* Open-water tests: attitude RMSE 1.3°–4.4°, helical depth-tracking RMSE 0.073 m
* Resurfacing GPS fixes enable multitarget following; accuracy limited by sensors

![graph_abstract](https://ScudeT.github.io/files/maui/OE-2026-09/graph_abstract.png)

## Abstract

This work presents a simplified and control-oriented framework enabling closed-loop navigation of an underwater robot inspired by a cownose ray and propelled by flexible pectoral fins. This study provides novel fully onboard, open-water demonstrations of closed-loop 6-DOF motion control for a batoid-inspired AUV driven by flexible fins, without external tracking systems: attitude and depth are regulated continuously from onboard sensing, while planar position is corrected intermittently from GPS fixes acquired during resurfacing. A reduced set of kinematic variables is identified to map fin actuation to body forces and moments, allowing the fins to be treated as generalized thrusters without relying on complex hydrodynamic modeling. This abstraction guides the design of a cascaded control architecture integrating quaternion-based attitude regulation, depth control, and absolute heading control. The approach is implemented on a ray-inspired robot equipped with a ROS2-based modular software stack and a lightweight sensor suite. Open water experiments demonstrate reliable orientation control, dynamic reference tracking, helical trajectory execution, and preliminary waypoint navigation, achieving attitude-maintenance RMSE (Root Mean Square Error) of 1.3°–4.4°across yaw/pitch/roll and depth-tracking RMSE of 0.073 m in helical motion. The results show that a control architecture independent of a dynamic model, with control variables related to fin kinematics, provides an effective methodology for autonomous underwater navigation with soft, bioinspired AUVs.
