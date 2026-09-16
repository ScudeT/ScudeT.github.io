---
title: "Ringo - walks"
excerpt: "Repair and update an old Arbotix 6 legged Robot for future development"
collection: portfolio
order: 14
header:
  teaser: "portfolio/ringo-walks.jpg"
---

> February 2026 - September 2026

Meet **Ringo** — a 6-legged bug of a robot named after a certain Beatle, because what else do you call a hexapod? Ringo is built on the PhantomX platform (18 DOF: 6 legs × coxa/femur/tibia, Dynamixel AX-12A servos) and has been sitting around for about 10 years. This repo is the story of getting him back on his feet: reviving decade-old hardware, rewriting the stack on ROS 2, and teaching him to walk again — first in simulation, then for real.

It covers the full pipeline from low-level firmware to high-level control: ArbotiX-M motor control, a ROS 2 teleop → gait → IK → estimation stack, robot description for simulation, and the Docker environments that tie it together on the Jetson and a dev PC.

## Demo: sim vs. real

<video src="/files/ringo/ringo-walks.mp4" controls playsinline style="max-width: 100%;"></video>

The same commands, sent to the simulated Ringo (Isaac Sim) and the real hardware, side by side.

> All the code and a little readme is available at the following [public Repo](https://github.com/ScudeT/Ringo-walks)

// video