---
title: "Sailing Team: Leading the 2024/25 Project"
excerpt: "Head of department for a 30-person mechatronics project, from PCB and comms to the first autonomous foiling flight"
collection: portfolio
order: 9
header:
  teaser: "portfolio/sailing-team.png"
---
> September 2024 - June 2025

**Developed & learned:** STM32 low-level programming · custom PCB design · CAN bus / NMEA2000 · sensor fusion · waterproof hardware design · team leadership & technical mentoring · project management

**My role:** head of department, third year on the [Polimi Sailing Team](https://scudet.github.io/portfolio/2_sailing-lateral-dynamics/), overseeing the full mechatronics system through the work of about 30 people.

> The full body of work is collected in a public repository, including some of what was developed while I was head of department: [Sailing-Team-Polimi / 2025_SOFTWARE](https://github.com/Sailing-Team-Polimi/2025_SOFTWARE)

## Leading the project

In the third year I was made responsible for the project, following on from the [lateral dynamics model](https://scudet.github.io/portfolio/2_sailing-lateral-dynamics/) and [ROS2/Docker architecture](https://scudet.github.io/portfolio/5_sailing-ros2-docker/) built in the previous two years. I chose to build on the previous year's work rather than restart: hardening the PCBs so the most fundamental layer would be reliable, passing on the know-how behind the software system, and giving the mechanical side the attention it needed. The actuator design in particular demanded care, since a failure there could break the boat outright. For the first time, we watched the boat lift itself out of the water under autonomous control.

By then the system consisted of:
- a sensor reading the angle of the existing probe, giving an estimate of the boat's height
- a prototype ultrasonic sensor for boat height
- a prototype ultrasonic sensor for wind speed and direction
- an IMU for global heading estimation
- a servo mechanism actuating the main rudder
- a GPS for position and velocity
- a Raspberry Pi 4/5 running ROS2
- an NMEA2000 CAN communication system with waterproof cabling
- a custom 24V lithium battery, stepped down to 12V for the system
- separate 12V LiPo batteries for the computer and servo motor, whose current draw exceeded the limit of the waterproof cables

For each piece of hardware, the work broke down into four parts:
- **custom electronics** for CAN communication; first prototyped on breadboards with STM32 development boards, then designed as custom PCBs with STM chips
- **casings** designed around both a mounting strategy (on a boat never intended to carry electronics) and waterproofing (typically a hydrophobic gel)
- **a low-level program** on the STM32 to read and interpret the sensor's data and send it on, and/or to receive commands from the main computer and act on them
- **the main-computer counterpart** to interpret incoming data, fuse each estimate into a shared model of the boat's state, and decide how to drive each actuator toward stable flight

All of this data was then available to anyone simply by logging into the same network; the power of ROS2.

As I later put it, the laws I was working under turned out to be less Newton's than Murphy's. The mechatronics didn't fully show at the competition: the main computer unexpectedly fried, probably from heat, after five minutes in the sun, and a few microcontrollers went with it, making on-the-spot repairs slow and costly. Fortunately the system was robust enough to run without the computer; driving the main flap directly from the height sensor's feedback; and on the final day of the competition, the boat flew.

When I finished and moved on to my PhD, I kept following the team's work, helping with suggestions and support. I'm proud to have left behind a healthy group that carried the work forward beautifully; and I still can't quite describe the excitement of watching the boat lift out of the water on a fully working mechatronics system, with the live data coming through on the custom app.

This project was ultimately the effort of many people who gave time out of their studies to leave their mark on it. I'm glad to have led it to that result; and maybe to have taught the students who came after a few things I'd had to learn on my own.
