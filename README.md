# EEE3088F-Group31-Micro-mouse-project

![R](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/01f54a60-e836-4ba0-82be-355d683afa89)
### What is a micro-mouse? 
A micromouse is an autonomous robot designed to navigate and solve a maize as quickly as possible. More abstractly, a micromouse is a maze-solving robot or an autonomous maze navigator. To gain context of what a micromouse is, watch [this](https://www.youtube.com/watch?v=ZMQbHMgK2rw) video.

### Project Overview
This project is all about designing some subassemblies for a (simplified) micro-mouse. The (simplified) micromouse has four modules, namely: the processor, motherboard, sensing and power. This project is solely focused on making PCB designs of the power and sensing subsystems that will collaborate with the rest of the micro-mouse's other subsystems (that have already been designed). 

## Exposition of each module

- **The motherboard**: The given motherboard is responsible for connecting all the 
                       subsystems/PCBs together. It is the base board that all other modules will slot onto.

- **The processor**: The processor board has a STM32L476. It is a 100-
pin package and has 78 output pins that are available to use, the subsystems will interface with the microcontroler through these pins. Most of 
these have already been dictated by the required interconnections 
between supplementary modules.

- **The power**: This module is responsible for powering the entire system. For this project, this is the subsystem that is being designed. This subsystem should be designed such that it meets the given requirements. A high-level description of the requirements is as follows:
-It needs to run the motors and charge a battery.
-It will need to fit onto the pin headers on the motherboard.
-It will need to be an appropriate size for the robot.
- **The sensor**:
