
Block Diagram
---

The motor and motor driver block diagram to give a general representaiotn of how the microcontroller will work with the driver, be programed from a Snap programmer and connect to other systems.  
![Block-Diagram](./BDiagram.png)


The requirements for this project was to have two different types of power, some means of communication with my team, 
a means to program my microcontroller and a way to engage my stepper motor. 
I used a 9V 1A power wall mount power supply through a barrel jack coupled with TEAM202 supplied power through ribbin cable. 

The PIC18F47Q10 was able to communicate with the A3909GLYTR-T motor driver through a series of pins which would send output signals to the Nema stepper motor.
