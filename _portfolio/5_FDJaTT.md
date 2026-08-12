---
title: "Distributed localization"
excerpt: "Reproducing a paper on convergence of distributed position estimation in robot networks"
collection: portfolio
order: 5
header:
  teaser: "portfolio/FDJaTT.png"
---

> **Goal of the project:** reproduce and verify the central convergence result of a published paper through simulation.

## Skills at a glance

**Developed & learned:** distributed estimation · multi-robot systems · convergence analysis · MATLAB simulation · nonlinear control · sensor/communication error modeling

**My role:** sole author — implementation and verification in simulation.

## The paper

[*Fully Distributed Joint Localization and Target Tracking With Mobile Robot Networks*](https://doi.org/10.1109/TCST.2020.2991126) addresses how a robot in a network can estimate its own position online and locally, while only communicating sparsely with nearby robots. It proves that the estimate converges — it does not diverge over time — under a realistic set of assumptions:
- not every robot can independently estimate its own position
- every robot can measure its distance to nearby robots, with some error
- every robot can communicate with nearby robots, but transmissions may occasionally fail
- every robot starts with an estimate of its initial position

Under these conditions, each robot propagates its position over time using its internal velocity estimate, then corrects that estimate simply by exchanging positions and measurements with its neighbors. The paper's result is that this local, sparse correction is enough to keep the estimate stable.

## What I did

During a course in Nonlinear Control taken abroad, I was tasked with verifying this result. I reproduced it by simulating *n* robots moving through space in a random walk, implementing the distributed estimation scheme and confirming that the position estimates stayed bounded rather than drifting. The simulation was written primarily as MATLAB script.

> All the code is available in the [public repository](https://github.com/ScudeT/FDJaTT-paper-simulation).
