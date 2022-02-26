 <div id="top"></div>

<!-- PROJECT LOGO -->
<br />
<div align="center">


  <h3 align="center">Swarm Mobile Robots Firmation Control</h3>

  <p align="center">
    Modeling, Trajectory Planning and Swarm Formation Control For Mobile Robots 🎛️🚘
    <br />
    <b> System Kinematics and Dynamics Model and Controller Design </b>
    <br />
    <a href="https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation//issues">Report Bug & Request Feature</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li><a href="#algorithm">Algorithm</a></li>
    <li><a href="#refereces">Refereces</a></li>

  </ol>
</details>


## About The Project
This repository contains Simulink implementation of "A Decentralized Cooperative Control Scheme With Obstacle Avoidance for a Team of Mobile Robots" by Hamed Rezaee and Farzaneh Abdollahi. You can find the article using this links: [IEEE](https://ieeexplore.ieee.org/document/6451251)

This project has been done at the request of *Zobdeh Modiran Rahneshan Soraya Company* in the 2nd *Rahneshan Competition*.

<p align="right">(<a href="#top">back to top</a>)</p>

### Built With

Major softwares/libraries used to this project:

* [MATLAB 2014a](https://www.mathworks.com/products/matlab.html)
  * Control System Toolbox
* [Simulink v10](https://www.mathworks.com/products/simulink.html)

<p align="right">(<a href="#top">back to top</a>)</p>




## Algorithm
This algorithm applies a potential field method to our control strategy to arrange a polygon formation. 

<p align="right">(<a href="#top">back to top</a>)</p>

**The dynamical equation of the Agents**, which is a *double integrator*, is considered as follow:
![1](https://user-images.githubusercontent.com/93844522/155850189-b5af05eb-c695-44d4-9da6-2679389a52eb.png)

```M: the mass, B: the damper coefficient, f_k: the control force, k_d: a coefficient considered to control the transient response of the robot```

<p align="right">(<a href="#top">back to top</a>)</p>




<!-- REFERENCES -->
## Refereces
[1] *H. Rezaee, and F. Abdollahi, “A Decentralized Cooperative Control Scheme with Obstacle Avoidance for a Team of Mobile Robots,” IEEE Transactions on Industrial Electronics, vol. 61, pp. 347-354, January 2014.*
![image](https://user-images.githubusercontent.com/93844522/155850981-8f0bc756-8e86-4918-b1a3-bcf10ba14703.png)
