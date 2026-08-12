---
title: "Polimi Sailing Team"
excerpt: "Development of a mechatronics system on a Foiling Sail Boat"
collection: portfolio
order: 2
header:
  teaser: "portfolio/sailing-team.png"
---
> October 2022 - June 2025

## Role at a glance

| Year | Role | Focus & deliverables |
|------|------|----------------------|
| 2022/23 | Controls contributor | Modeled the boat's lateral dynamics for a model based controller; learned to prioritize foundational lab work over isolated software |
| 2023/24 | Software architect | Designed a modular, industry-standard software system on ROS2 and Docker; onboarded and mentored new team members |
| 2024/25 | Head of department | Led the project; hardened the PCB and communication layers, oversaw actuator design, and achieved the first autonomous foiling flight |

**Developed & learned:** ROS2 · Docker · system modeling · STM32 low-level programming · custom PCB design · CAN bus / NMEA2000 · sensor fusion · waterproof hardware design · team leadership & technical mentoring

> The full body of work is collected in a public repository, including some of what was developed while I was head of department: [Sailing-Team-Polimi / 2025_SOFTWARE](https://github.com/Sailing-Team-Polimi/2025_SOFTWARE)

# My experience there

At the start of my master's, I wanted to put what I was learning into practice on something real. My university ran several student competitions, and I chose the one closest to home: the [SuMoth Challenge](https://sumoth.org/), which brings student teams from around the world together to design, build, and race IMCA Moth-class foiling boats on Lake Garda, with the goal of making production in the field more sustainable.

In 2022, Politecnico's team decided it was time to add a mechatronics system to the boat; one that could assist the skipper with automatic control of the boat's lateral dynamics and give real-time feedback on performance. We were among the first teams to attempt this. That's when I joined: a new group, an ambitious goal, and plenty of obstacles in the way.

### Year one: learning the hard way

I was tasked with building a model of the boat's lateral dynamics to feed a model based controller. The model was sound, but with no working system underneath it, it was never deployed. In hindsight I made a mistake: I stayed behind the computer chasing the controller while my teammates were in the lab solving the foundational problems that needed solving first. We arrived at SuMoth with a boat that won several awards, but the mechatronics wasn't ready. The plan itself held up; our report earned recognition for it; and the lesson about where to spend my effort stayed with me.

### Year two: building the foundation

I spent the start of the second year abroad, working remotely again. I used the distance to focus on something durable: a software architecture that would survive across generations of students; robust, modular enough for continuous development, and built on industry standards so the team would learn infrastructure useful well beyond this project. Drawing on a course I was taking and a [parallel project](https://scudet.github.io/portfolio/3_auto-hokey/) at my host university, I built the system around ROS2 and Docker.

ROS2 gave us an industry-standard approach to robotics software; the same framework used on most autonomous vehicles at the R&D stage. It splits development into separate programs that communicate with each other, so different students could own different parts and then deploy them together. Docker solved a practical problem on top of that: ROS2 ties each version to a specific operating system, so Docker let everyone develop on their own machine regardless of OS and deploy to the robot with no uncertainty about whether it would run.

In parallel, the rest of the team built a modular communication infrastructure on STM microcontrollers and a CAN bus running NMEA2000, the standard protocol in marine electronics. The STM chips let us design our own PCBs, and the protocol let us integrate proprietary hardware without building a custom board for every device. When I returned from abroad, I taught the incoming students how the system worked and tuned it based on their feedback.

The hardware's complexity made it hard to work with; it took a full year just to get the communication running reliably. Our report was one of the reasons we won the SuMoth Challenge overall in 2023/24, but we still weren't satisfied: the system hadn't flown.

### Year three: leading the project

In the third year I was made responsible for the project. I chose to build on the previous year's work rather than restart: hardening the PCBs so the most fundamental layer would be reliable, passing on the know-how behind the software system, and giving the mechanical side the attention it needed. The actuator design in particular demanded care, since a failure there could break the boat outright. For the first time, we watched the boat lift itself out of the water under autonomous control.

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

This project was ultimately the effort of many people who gave time out of their studies to leave their mark on it. I'm glad to have left an impact; and maybe to have taught the students who came after a few things I'd had to learn on my own.