---
title: "Live SLAM Mapping"
excerpt: "Upgrading the hockey robot with LiDAR to map a lab in real time"
collection: portfolio
order: 4
header:
  teaser: "portfolio/auto-hokey.png"
---

> November 2023 - December 2023

> **Goal of the project:** upgrade the robot from the [hockey contest](https://ScudeT.github.io/portfolio/3_auto-hokey/) with new hardware to achieve a completely different capability — live mapping.

## Skills at a glance

**Developed & learned:** ROS2 · Nav2 · SLAM · LiDAR integration · Docker (legacy OS deployment) · networked multi-machine ROS2 · odometry

**My role:** sole developer — hardware integration and full software stack.

## What I built

I added a LiDAR sensor to the differential-drive robot I'd developed for the hockey challenge, this time to run SLAM and map the laboratory live during the presentation. The mapping ran through ROS2's Nav2 package.

The interesting constraint was the hardware: ROS2 had to run on the same aging Raspberry Pi 3 as before. I got it working through a Docker container built on a lightweight Ubuntu 18 image, which let a modern ROS2 stack run on hardware that couldn't otherwise support it.

I split the workload across two machines on a shared network:
- **On the robot**, the Raspberry Pi ran only the nodes needed to drive the robot and publish its LiDAR and odometry data.
- **On a networked Ubuntu computer**, I ran the SLAM algorithm — consuming the messages published by the robot — and drove the robot via keyboard commands.

Keeping the heavy computation off the robot let the underpowered Pi stay responsive while the mapping ran in real time.

> All the code and a short readme are available in the [public repository](https://github.com/ScudeT/MobileRoboticsProject).