# Swarm-Formation-Control
(Will be completed soon!)
This repository contains Simulink implementation of "A Decentralized Cooperative Control Scheme With Obstacle Avoidance for a Team of Mobile Robots" by Hamed Rezaee and Farzaneh Abdollahi. You can find the article using this links: [IEEE](https://ieeexplore.ieee.org/document/6451251)

## Algorithm
This algorithm applies a potential field method to our control strategy to arrange a polygon formation. 


**The dynamical equation of the Agents**, which is a double integrator, is considered as follow:
![1](https://user-images.githubusercontent.com/93844522/155850189-b5af05eb-c695-44d4-9da6-2679389a52eb.png)

```math
M*x" + B*x' = f_x - k*x' 
M*y" + B*y' = f_y - k*y'
```
```M: the mass, B: the damper coefficient, f: the control force, k: a coefficient considered to control the transient response of the robot```
