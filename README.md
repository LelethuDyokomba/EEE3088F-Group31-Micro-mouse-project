# EEE3088F-Group31-Micro-mouse-project

![R](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/01f54a60-e836-4ba0-82be-355d683afa89)
### What is a micro-mouse? 
A micromouse is an autonomous robot designed to navigate and solve a maize as quickly as possible. More abstractly, a micromouse is a maze-solving robot or an autonomous maze navigator. To gain context of what a micromouse is, watch [this](https://www.youtube.com/watch?v=ZMQbHMgK2rw) video.

### Project Overview
This project is all about designing some subassemblies for a (simplified) micro-mouse. The (simplified) micromouse has four modules, namely: the processor, motherboard, sensing and power. This project is solely focused on designing and manufacturing the power and sensing subsystems that will collaborate with the rest of the micro-mouse's other subsystems (that have already been designed). 

## Exposition of each module

- **The motherboard**: The given motherboard is responsible for connecting all the 
                       subsystems/PCBs together. It is the base board that all other modules will slot onto.

- **The processor**: The processor board has a STM32L476. It is a 100-
pin package and has 78 output pins that are available to use, the subsystems will interface with the microcontroler through these pins. Most of 
these have already been dictated by the required interconnections 
between supplementary modules.

- **The power**: This module is responsible for powering the entire system. For this project, this is the subsystem that is being designed and manufactured. This subsystem should be designed such that it meets the given requirements. A high-level description of the requirements is as follows:
> - It needs to run the motors and charge a battery.
> - It will need to fit onto the pin headers on the motherboard.
> - It will need to be an appropriate size for the robot.
- **The sensor**: This module will be responsible for detecting/sensing objects. For this project, this is the subsystem that is being designed and manufactured. This subsystem should be designed such that it meets the given requirements. A high-level description of the requirements is as follows:
> - It needs to detect objects.
> - It will need to fit onto the pin headers on the motherboard.
> - It will need to be an appropriate size for the robot.

## Requirements and specifications of the subsystems




![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/7afe9fe0-3bef-4b60-aea8-3b8a2bd8c481)<br>
The image below features a pin view of the Motherboard PCB. This is the exact layout and shape of 
the motherboard. The sensor and power PCBs will be designed to fit onto the sensor and power 
connections.<br>
![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/c8e6e336-e12f-4789-9774-9814666661b1)

- ![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/46b3d521-76cb-4023-8c0c-0a425f7fddc4)

This processor board has a STM32L476 microcontroller on 
it. The images below depict the 3D PCB render and the schematic of the processor board.



![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/d1a7982e-c805-49c5-833b-fe3de31666cf)



![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/52f1492b-0533-4ee8-ab60-ed8f3f5ea6c3)



The following table highlights the pinouts of the processor board:


![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/81c4b08b-91aa-4e75-834b-3b6eeaf94b0b)

![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/7cae4ada-2729-455e-9e60-5ac30e41fabb)

The module needs:



> - To operate 2 motors with the pins available (listed in Table 3). Needs to 
control 2x motors which could each draw 200mA at the highest voltage of a 1S1P battery 
(the battery is further specified in the battery section). 
> - Needs to provide an analog connection that provides information on the battery's voltage 
for the processor to sense battery state of charge (SoC). 
> - Needs to charge the battery from the 5V input pin (listed in Table 3).
> - Needs an ON/OFF switch. OFF state: battery draw <500uA. ON state: ther robot peak 
current.

Additionally, the following connectors need to be included:
1. A JST PH 2mm pin pitch connector for the battery. The battery will either be tucked away 
between the motherboard PCB and the processor PCB or secured to the bottom of the 
motherboard.
2. A 2x8 (2.54mm pin pitch) pin header as shown in the image below:

![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/b59e1451-9cf9-4044-9dbc-8c0000b0202e)

1. The Connector does NEED to be proud of the resulting board (i.e. needs to have 
a tab) as the motors and connections would collide otherwise. The height of the 
tab can be 18mm or greater, the width can be no greater than 35mm and the 
connector should be centered in this tab.
2. Additionally, you want to minimize the maximum distance of your robot from 
the center of rotation (indicated on the MM motherboard PCB). Essentially this 
means that you want to make your PCB as small as possible.

![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/4b030318-a4d9-4f70-927f-ef3557e2c637)

![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/1355dcf3-603c-411b-8b57-a68655348e9b)

![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/3c34bb09-300b-4bd7-9213-661b24ba54c8)


The sensor PCB is effectively the “eyes” of your robot. This subsystem will provide information to 
the processor to determine whether there is an obstruction in the way of the MM. This submodule 
needs to:
> - Detect whether there is an obstacle in front of the robot (probably on the sides too).
> - Have switching means to save power when not in operation.
Additionally, you need to:
> - Design for reliability such that you can prove your system works.
> - Consider how much power and current your sensing board is using/drawing so that you do 
not drain the battery before the maze is solved.
> - Write some code to interface your sensor with the rest of the system and prove it senses the 
wall. The processor board has 3 LEDs (so you do not need to add LEDs for this purpose on 
your sensing board). Use 1 to indicate a wall is sensed on the right, 1 to indicate that there is 
a wall on the left and 1 to indicate a wall in front of the robot. If no wall is sensed, then no 
LEDs will be on.
<br>
The following image is a template of the board shape, but the arc and design are not necessarily an 
optimal solution

![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/b6e12ab6-651d-4dde-8450-9d7a1347aec1)

It will need to fit onto the 2x14 connection standard and be an appropriate size for the robot.

![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/3e719db9-1f50-4191-b04f-699a5e8c34bf)

To be successful, you will need to understand how your component fits into the greater picture and 
what you would need to do on your module to meet the requirements.

![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/b3fcf4b7-49c3-4bfd-bec4-13e8574b2da1)

The battery will be: [Battery LiPo 800mAh 3.7V - Micro Robotics](https://www.robotics.org.za/802540)

Typically, the max discharge should be kept at 0.5C (Capacity) for this type of battery. This implies 400mA 
max draw and from full to fully discharged in 2 hours. 


![image](https://github.com/LelethuDyokomba/EEE3088F-Group31-Micro-mouse-project/assets/163681208/8fa658cb-e68d-4cca-a349-9c62b386a282)

The cost of the components should  not be more $8.25 per board, per subsystem. 






