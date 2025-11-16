# taketwo_multi_sim
Multi-vehicle platoon simulation framework for evaluating the taketwo car-following controller in both ROS/Simulink and Python-based Jupyter environments.

This repository contains all launch files, controller models, and anlaysis notebooks used to run scalable multi-vehicle platoon simulations for the assignment. It supports both (1) real-time ROS/Simulink platooning and (2) lightweight Python-based platoon simulations, enabling comparisons of controller performance, safety, string stability, and road capacity behavior across multiple controller versions.

## Repository Structure:

```
launch/                     # Multi-vehicle ROS launch files
controllers/                # Simulink controller versions (v1, v2)
notebooks/                  # Jupyter notebooks (analysis + Python platoon sim)
```

## How to run the multi-vehicle ROS simulation::
1. Build and source the Docker ROS container as usual
2. Run the full platoon simulation: `roslaunch taketwo taketwoDocker_multi.launch`

#### This launch file:
* Plays the HWIL bag file into ROS.
* Spawns a lead car and four followers (egocar, car2, car3, car4).
* Wires each vehicle’s dynamics, controller, and relative-distance/velocity nodes.
* Records all topics into a single output bag for post-processing.

## Jupyter Notebooks:
`taketwo_Large_Scale_Analysis.ipynb`:
Processes the output bag file from the ROS simulation and generates:
1. Inter-vehicle spacing (safety + stability)
2. Mode classification over time
3. Relative-velocity propagation
These figures evaluate how the controller behaved in the Docker multi-vehicle run.

`taketake_Large_Scale_Sim.ipynb`:
Recreates the controller logic in Python and simulates a 5-car platoon:
- Same ModeSelector logic, LUT values, and control law as MATLAB design
- Simpler point-mass vehicle model (no actuator dynamics, no ROS noise)
- Allows rapid testing and changing of α, τ, and mode thresholds
- Produces string-stability figures and capacity metrics


## Controllers:
`controllers/taketwo_v1.slx`: version used in real-road test
`controllers/taketwo_v2.slx`: adjusted α, τ, and mode-transition buffer
Both controllers use ROS and are compatible with the multi-vehicle launch file.


##Purpose:
This project aims to:
- Test scalability of the taketwo controller across platoons
- Look at both ROS/Simulink performance and simplified notebook simulation
- Analyze safety, stability, and throughput based on leader behavior
