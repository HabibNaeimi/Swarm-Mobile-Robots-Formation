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
    <li>
      <a href="#algorithm">Algorithm</a>
      <ul>
        <li><a href="#%D9%90agents-model-defenition">Agents Model Defenition</a></li>
        <li><a href="#path-planning">Path Planning</a></li>
      </ul>
    </li>
    <li><a href="#fixed-formation">Fixed Formation</a></li>
    <li><a href="#Dynamic-formation">Dynamic Formation</a></li> 
    <li><a href="#failing-scenario">Failing Scenario</a></li>    
    <li><a href="#References">References</a></li>

  </ol>
</details>


## About The Project
This repository contains the Simulink implementation of "A Decentralized Cooperative Control Scheme With Obstacle Avoidance for a Team of Mobile Robots" by Hamed Rezaee and Farzaneh Abdollahi. You can find the article in the [References](https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation/edit/main/README.md#references) section or use this link:: [IEEE](https://ieeexplore.ieee.org/document/6451251)

This project has been done at the request of *Zobdeh Modiran Rahneshan Soraya Company* in the 2nd *Rahneshan Competition*.

![image7](https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation/blob/958b4278b6e43488f689c7d65c41bcb2a988f8a3/Results/Dynamic%20Formation.jpg)


<p align="right">(<a href="#top">back to top</a>)</p>

### Built With

Major softwares/libraries used to this project:

* [MATLAB 2014a](https://www.mathworks.com/products/matlab.html)
* [Simulink v8.3](https://www.mathworks.com/products/simulink.html)
* [Python v3.7](https://www.python.org/downloads/release/python-370/)
  * [Pandas](https://pandas.pydata.org/)
  * [Numpy v1.18](https://numpy.org/devdocs/release/1.18.0-notes.html)
  * [Bokeh v1.4](https://docs.bokeh.org/en/1.4.0/docs/user_guide.html)
* [Jupyter Notebook v6.4](https://jupyter.org/try) 

<p align="right">(<a href="#top">back to top</a>)</p>


## Algorithm
This algorithm applies a potential field method to our control strategy to arrange a polygon formation. In this algorithm, the robots consider electric charges, and the method is based on the repulsive forces between electric charges. These forces make agents form on a circle with a defined center and radius. Additionally, these forces make themselves form in a polygon formation on that circle. We can move the formated agents by dragging the center. The center of this circle can be considered as a virtual leader.

In this project, we have four agents to form in a regular quadrilateral or square.

### ِAgents Model Defenition
**The dynamical equation of the Agents**, which is a *double integrator*, is considered as follow:
![2](https://user-images.githubusercontent.com/93844522/155851605-b696a159-71d3-4b20-a313-b33c083d83da.png)

```M: the mass, B: the damper coefficient, f_k: the control force, k_d: a coefficient considered to control the transient response of the robot```

where

![3](https://user-images.githubusercontent.com/93844522/155852219-a73ad849-ddb3-4cc1-98a9-931eccaa1b91.png)

```alpha: the radius, (xc,yc): the center (also considers as virtual leader)```

and the force that exerts on the kth charge from N − 1 charges is as below:

![4](https://user-images.githubusercontent.com/93844522/155852371-a0df20a7-be74-4a8f-9186-afb8ae5f8af2.png)

Finally, each agent is simulated as below:

![9](https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation/blob/958b4278b6e43488f689c7d65c41bcb2a988f8a3/Simulations/Agent%203.jpg)

<p align="right">(<a href="#top">back to top</a>)</p>

### Path Planning
We chose a discrete sinuosity trajectory for this project and developed a block to address all agents independently—the initial point used for Fixed Formation in (0,1). Our agents will form around this point, and by changing this point, we move the virtual leader and following agents.

The following diagram is the Path Planning block:

![8](https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation/blob/958b4278b6e43488f689c7d65c41bcb2a988f8a3/Simulations/Trajectory.jpg)

<p align="right">(<a href="#top">back to top</a>)</p>


## Fixed Formation
Initial coordination of the agents are (-1,2) for Agent 1, (3,6) for Agent 2, (3,-1) for Agent 3, and (-4,-4) for Agent 4. These agents are targeted to arrange a formation around the point (0,1), our virtual leader.

Following figure shows the path of each agent from the initial point to its point in regular quadrilateral formation.

![10](https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation/blob/958b4278b6e43488f689c7d65c41bcb2a988f8a3/Results/Fixed%20Formation.jpg)

<p align="right">(<a href="#top">back to top</a>)</p>

## Dynamic Formation
After achieving formation, we transfer the virtual leader so the robots can move following that. The discrete trajectory allows us to maintain the formation along the path.

Block diagram of the dynamic formation simulation: 

![11](https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation/blob/958b4278b6e43488f689c7d65c41bcb2a988f8a3/Simulations/Dynamic%20Formation%20Diagram.jpg)

Results of simulation:

![image7](https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation/blob/958b4278b6e43488f689c7d65c41bcb2a988f8a3/Results/Dynamic%20Formation.jpg)

<p align="right">(<a href="#top">back to top</a>)</p>

## Failing Scenario
The scenario of losing an agent.

To prove that this algorithm is robust in changing the number of agents suddenly, we proposed a special case study that one of the agents will fail in the middle of our path and see what's happening to the other agents. The results were magnificent. We have four agents to form in a regular quadrilateral or square in the usual dynamic formation. But when the failure happens, the number of our agents decreases to three, and the agents start reforming their formation. They change their position on the hypothetical circle until arranging a polygonal formation which is a regular triangle in this case.

![12](https://github.com/HabibNaeimi/Swarm-Mobile-Robots-Formation/blob/958b4278b6e43488f689c7d65c41bcb2a988f8a3/Results/Losing%20Agent.jpg)

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- References -->
## References
[1] *[H. Rezaee, and F. Abdollahi, “A Decentralized Cooperative Control Scheme with Obstacle Avoidance for a Team of Mobile Robots,” IEEE Transactions on Industrial Electronics, vol. 61, pp. 347-354, January 2014.](https://ieeexplore.ieee.org/document/6451251)*

[2] *[V. Bajaj, and S. Rao, “Autonomous Shape Formation and Morphing in a Dynamic Environment by a Swarm of Robots,” Proceedings of The 19th International Conference On Autonomous Agents and Multiagent Systems, pp. 1765-1767, May 2020.](http://ifaamas.org/Proceedings/aamas2020/pdfs/p1765.pdf)*
<p align="right">(<a href="#top">back to top</a>)</p>
