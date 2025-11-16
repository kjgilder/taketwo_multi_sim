# taketwo_multi_sim
Multi-vehicle platoon simulation framework for evaluating the taketwo car-following controller in both ROS/Simulink and Python-based Jupyter environments.

This repository contains all launch files, controller models, and anlaysis notebooks used to run scalable multi-vehicle platoon simulations for the assignment. It supports both (1) real-time ROS/Simulink platooning and (2) lightweight Python-based platoon simulations, enabling comparisons of controller performance, safety, string stability, and road capacity behavior across multiple controller versions.

Repository Structure:

**launch/taketwoDocker_multi.launch** : ROS multi-vehicle platoon launch file


**controllers/**
    **taketwo_v1.slx** : Controller used in real-road test and Verison 1 of the large scale simulation doc
    **taketwo_v2.slx** : Updated controlelr with revised tau/alpha + buffer and Version 2 of the large scale simulation doc


**notebooks/**
    **taketwo_Large_Scale_Analysis.ipynb** : Analysis of bag-file output for Version 1 and 2
    **taketwo_Large_Scale_Sim.ipynb** : Python recreation of the controller and platoon sim (Version 3)
