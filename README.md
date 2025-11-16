# taketwo_multi_sim
Multi-vehicle platoon simulation framework for evaluating the taketwo car-following controller in both ROS/Simulink and Python-based Jupyter environments.

This repository contains all launch files, controller models, and anlaysis notebooks used to run scalable multi-vehicle platoon simulations for the assignment. It supports both (1) real-time ROS/Simulink platooning and (2) lightweight Python-based platoon simulations, enabling comparisons of controller performance, safety, string stability, and road capacity behavior across multiple controller versions.

Repository Structure:

```
launch/                     # Multi-vehicle ROS launch files
controllers/                # Simulink controller versions (v1, v2)
notebooks/                  # Jupyter notebooks (analysis + Python platoon sim)
```
