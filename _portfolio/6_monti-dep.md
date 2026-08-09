---
title: "Monti - development"
excerpt: "Repair and Deployment of a Snake inspired robot desinged to swim through CPG with feedback"
collection: portfolio
order: 6
header:
  teaser: "portfolio/monti-dev.jpg"
---

* The project began with an existing prototype: a well-conceived, navigation-oriented design that hadn't yet reached reliable execution. Its architecture was already solid — eight independently actuated modules, each with its own circuitry for power-on and recharging through a central unit, all linked over a shared I2C bus. The main gap was feedback: giving the central unit true state feedback required reprogramming the modules, but the existing procedure broke every connection, forcing them to be rebuilt from scratch each time.
* Building on that foundation, I designed and hand-built compact perfboard circuits sized to fit the original enclosures, making the whole system far easier to work on and iterate.
* I rewrote the module firmware to support fast I2C communication with the main board, exposing clean per-module commands — MOVE, READ_ENCODER, TURN_OFF and RESET — plus a startup routine that zeroes each motor so the encoder output is centered on the motor's position, which also simplified mounting. To eliminate the servo jitter caused by I2C interrupts disrupting PWM control, I moved the signal onto the hardware PWM of the Arduino Nano Every instead of the usual Arduino Servo library.
* To achieve smooth actuation, I redesigned the main-board code around the microcontroller's real limits. While swimming, a single loop had to update the CPG at high frequency, read the encoders, communicate with an IMU and a GPS, refresh command values for high-level heading control, combine CPG and heading control across all modules, dispatch commands to every module, and log data to an SD card. On a single-core microcontroller this meant profiling execution times and hardcoding a deterministic schedule — keeping the CPG update fast enough to avoid instability while accumulated delays never built up into visible jitter.

> All the code and a little readme is available at the following [public Repo](https://github.com/ScudeT/monti-ardu)

// video