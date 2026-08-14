---
title: "Autonomous Hokey Player"
excerpt: "Project work for the Mobile Robotics course at NYCU-Taiwan"
collection: portfolio
order: 3
header:
  teaser: "portfolio/auto-hokey.png"
---

> September 2023 - December 2023

> **Goal of the course:** develop a differential-drive robot to play hockey autonomously against other players.

## Skills at a glance

**Developed & learned:** ROS2 · Arduino ↔ Raspberry Pi serial communication · PID tuning · differential-drive control · odometry estimation · state machines · sensor integration (IR, light) · working within hardware constraints

**My role:** main developer of a group of 2 — hardware bring-up, low-level control, and high-level autonomy.

## The build

We were given a fixed kit to work with:
- a Raspberry Pi 3 and an Arduino Uno
- 2 DC motors with an I2C motor driver
- a differential-drive robot frame
- buttons, a light sensor, and an IR receiver
- LEGO bricks for bumpers and other appendages

I split the architecture across the two boards. The Arduino ran a low-level controller with PIDs tuned to make the two aging motors behave alike, and communicated over serial with the Raspberry Pi, which held the robot's main "brain" first in ROS melodic, then upgraded to ROS2 once Docker was learned. Buttons were wired directly to the Pi's digital pins, while the IR receiver and light sensor were read through the Arduino.

## Challenges along the way

The course was structured as a series of milestones building toward the final goal, each with a tight delivery deadline:
- demonstrate reliable communication between the two boards
- drive perfectly straight for 2m using velocity commands from the Pi and well-tuned PIDs
- recover after hitting an obstacle
- detect the puck (an LED disk) and drive toward it
- detect the goal (marked by an IR emitter broadcasting a known code)

## Working around the hardware

The hardware was basic, and much of the learning came from engineering around its limits:
- **Mismatched motors.** The motors were old and behaved very differently from each other. Because their transient responses didn't match, a step command made the robot veer toward the slower motor before straightening once the PID caught up. Ramping the command signal fixed it cleanly — but the tight deadlines left little room to refine each solution.
- **A "blind" light sensor.** Its quality wasn't good enough to distinguish the puck from ambient light, so the robot effectively couldn't see the puck.
- **A "deaf" IR receiver.** It only picked up the emitter when almost perfectly aligned and head-on, so detecting the goal was unreliable.

None of this took away from the project — it was the first time I'd tackled any of these problems, and working around the constraints is where most of the learning happened.

## Why ROS2

A lot of my time went into learning ROS2, managing control and the different game scenarios through state machines and odometry estimation. Several classmates avoided it, since it was easier to program everything on the Arduino with a single switch-case loop. The extra investment paid off: it fed directly into a follow-up [project](https://ScudeT.github.io/portfolio/4_HA_to_SLAM/), where the same system was rebuilt in ROS2 using the latest SLAM packages, with Docker handling deployment onto the same aging hardware.

> All the code and a short readme are available in the [public repository](https://github.com/ScudeT/Hokey-autonomous-challenge).