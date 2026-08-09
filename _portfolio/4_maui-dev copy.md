---
title: "Maui - development"
excerpt: "Design and development of a full bathoid inspired robot starting from the propulsion prototype"
collection: portfolio
order: 4
header:
  teaser: "portfolio/maui-dev.JPG"
---

* The project started from an existing prototype where the propulsion system was designed and simple feedforward strategy was implemented on an Arduino Board
![old_system](/files/maui/old_system.jpg)

* The Microcontroller was upgraded to an Embedded computer (Raspberry pi 5) and sensors where added to allow the estimation of the 6 degrees of freedom
* The new hardware required a redesign of the robot to recover close to 0 buoyancy, that was done following a more organic and bio-inspired approach
* The software was developed following a more scalable, modular and rubost architecture basesd on ROS2. Made possible on a raspberry through the deployment on a docker container, also allowing easier development and testing on a personal computer
* The two cameras added where linked to the ROS2 container through custom python scripts allowing for code inside the container to access simultaneous camera caputure through the strip connections (available only through the raspiOS) through api calls on a specific port. (ignored due to the rushed design of the camera enclosure, ruining image quality underwater)
* Given the availability of only an [MPU9250-IMU](https://www.amazon.it/ARCELI-MPU-9250-magnetico-accelerometro-giroscopico/dp/B07CDD8B14) (fusion-less) a custom driver was created to comunicate with it thorugh ROS2 and fuse the 9 raw values of gyro-accel-mag to obtain a quaternion estimate through the MADGWICK filter present in its [Arduino Library](https://github.com/hideakitai/MPU9250)
* Custom ROS2 drivers where also created for the [BlueRobotics pressure sensor](https://bluerobotics.com/store/sensors-cameras/sensors/bar-depth-pressure-sensor/), the [PWM driver](https://www.makerslab.it/pca9685-controllo-i2c-a-16-canali-pwm-per-led-e-servomotori/) and the [GPS module](https://www.amazon.it/Geekstory-navigazione-satellitare-compatibile-Microcontrollore/dp/B07PRGBLX7) connected to the Raspberry py, following their datasheets.
* Finally the control algorithm was developed as desinged in the following [Paper](https://ScudeT.github.io/publication/2026-09-01-From-fin-dynamics-to-navigation-control-A-simplified-framework-for-batoid-inspired-underwater-locomotion) and tested first in a swimmingpool in the lab and then in open waters at Lake Como

// video