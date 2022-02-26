 <div id="top"></div>


<!-- PROJECT SHIELDS -->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <i align="center"> In The Name Of God </i>

  <h3 align="center">Swarm Mobile Robots Firmation Control</h3>

  <p align="center">
    Modeling, Planning and Nonlinear Control Techniques For Autonomous Vehicles 🎛️🚘
    <br />
    <b> System Kinematics and Dynamics Model and Controller Design </b>
    <br />
    <a href="https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation//issues">Report Bug & Request Feature</a>
  </p>
</div>



## Swarm-Formation-Control
This repository contains Simulink implementation of "A Decentralized Cooperative Control Scheme With Obstacle Avoidance for a Team of Mobile Robots" by Hamed Rezaee and Farzaneh Abdollahi. You can find the article using this links: [IEEE](https://ieeexplore.ieee.org/document/6451251)

## Algorithm
This algorithm applies a potential field method to our control strategy to arrange a polygon formation. 


**The dynamical equation of the Agents**, which is a *double integrator*, is considered as follow:
![1](https://user-images.githubusercontent.com/93844522/155850189-b5af05eb-c695-44d4-9da6-2679389a52eb.png)

```M: the mass, B: the damper coefficient, f_k: the control force, k_d: a coefficient considered to control the transient response of the robot```
