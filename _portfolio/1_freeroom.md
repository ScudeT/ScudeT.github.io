---
title: "FreeR%m: Student Startup"
excerpt: "People counting for Universities and public spaces"
collection: portfolio
order: 1
header:
  teaser: "portfolio/freeroom.jpg"
---
> October 2022 - April 2025

FreeR%m started as a course project on innovative ideas. Four friends of mine, all students at Politecnico, set out to solve a problem we all faced: finding a free space to study on campus during exam season. The university offered study rooms and areas, but at peak times they were nearly impossible to find. Their idea was to monitor real-time occupancy in each room and combine it with the university's class-scheduling data, so students could quickly locate a quiet place to work. The same data would also give the university insight it needed for course planning and cleaning schedules.

I wasn't enrolled in the course myself, but since we were already friends, I'd been following their work from the start. When their professor encouraged them to enter an accelerator program in Valencia focused on improving student life, they went for it and won. The funding came with a mandate: build a working prototype. That's when I formally joined the team with another member, tasked with turning the concept into a functioning sensor.

I took on part of the concept and hardware design, along with development and field testing of the sensor. It worked. We validated it on campus and later deployed it in a private company's premises as well. The project was eventually shelved as we grew in different directions, but the prototype delivered on what it set out to prove.

The design philosophy was to build fast and produce real data that demonstrated the idea's potential. Privacy was central: rather than streaming camera footage over the network, the system processed each frame locally and transmitted only the count of people detected. That privacy-preserving pipeline was the core of the product.

My specific contributions:
- **3D design of the sensor housing**, engineered so the camera could be aimed without complex joints, using mainly 3D-printable parts for easy production and assembly.
- **Low-level setup and environment configuration** for each sensor unit, preparing the runtime the detection software depended on.
- **Field testing and deployment**, both on campus and at an external commercial site.