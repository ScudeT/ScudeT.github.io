---
title: "Sailing Team: Modular ROS2 & Docker Software Architecture"
excerpt: "Designing a modular, industry-standard software system on ROS2 and Docker to help the team develop more effectively"
collection: portfolio
order: 5
header:
  teaser: "portfolio/sailing-team.png"
---
> September 2023 - June 2024

**Developed & learned:** ROS2 · Docker · modular software architecture · onboarding & mentoring new team members

**My role:** software architect, second year on the [Polimi Sailing Team](https://scudet.github.io/portfolio/2_sailing-lateral-dynamics/).

## Building a foundation meant to last

I spent the start of the second year abroad, working remotely. I used the distance to focus on something durable: a software architecture that would survive across generations of students; robust, modular enough for continuous development, and built on industry standards so the team would learn infrastructure useful well beyond this project. Drawing on a course I was taking and a [parallel project](https://scudet.github.io/portfolio/3_auto-hokey/) at my host university, I built the system around ROS2 and Docker.

ROS2 gave us an industry-standard approach to robotics software; the same framework used on most autonomous vehicles at the R&D stage. It splits development into separate programs that communicate with each other, so different students could own different parts and then deploy them together. Docker solved a practical problem on top of that: ROS2 ties each version to a specific operating system, so Docker let everyone develop on their own machine regardless of OS and deploy to the robot with no uncertainty about whether it would run.

In parallel, the rest of the team built a modular communication infrastructure on STM microcontrollers and a CAN bus running NMEA2000, the standard protocol in marine electronics. The STM chips let us design our own PCBs, and the protocol let us integrate proprietary hardware without building a custom board for every device. When I returned from abroad, I taught the incoming students how the system worked and tuned it based on their feedback.

The hardware's complexity made it hard to work with; it took a full year just to get the communication running reliably. Our report was one of the reasons we won the SuMoth Challenge overall in 2023/24, but we still weren't satisfied: the system hadn't flown.

That came the following year, when I took over as head of department — see [leading the 2024/25 project](https://scudet.github.io/portfolio/9_sailing-team-management/).
