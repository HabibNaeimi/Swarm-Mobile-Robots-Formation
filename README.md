# Swarm-Formation-Control
(Will be completed soon!)
This repository contains Simulink implementation of "A Decentralized Cooperative Control Scheme With Obstacle Avoidance for a Team of Mobile Robots" by Hamed Rezaee and Farzaneh Abdollahi. You can find the article using this links: [IEEE](https://ieeexplore.ieee.org/document/6451251)

## Algorithm
This algorithm applies a potential field method to our control strategy to arrange a polygon formation. 


**The dynamical equation of the Agents**, which is a double integrator, is considered as follow:
```math
Mx" + Bx' = f_x - k_dx' 
My" + By' = f_y - k_dy'
```
```M: the mass, B: the damper coefficient, f: the control force, k_d: a coefficient considered to control
the transient response of the robot```
