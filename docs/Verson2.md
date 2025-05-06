The team found that my motor code would bog down the system. Data would come in, but my system would not know what to do with it and sent nothing out. The system was busy trying to work as programed but failed to do so causing issues with group communication. The only way it would work was to comment on the motor code. I would fix this by adding some type of sensor that identified movement and code to proceed if movement is found or exit if no movement is found. This would be looking for an action to take place and then alert if no action took place.  

Because of the problems I had with limited pins to work with, I would add more GPIO pins to the board giving me access to all pins that could be used if the pin being used had a problem. I would also add a female receiver to each of my subsystem pin so I could hard wire easier in the event it was needed. 
I did not have any lights to debug the system, just pins to measure voltage outputs. My system would be easier to read if I put in debugging lights that flashed as different processes were taking place. I would write into the program to toggle certain LEDS if different pins were sending or receiving a signal. 

Lastly, I would clean up the board by changing the design of different traces, section out where different connections could go, and remove all the switches that never got used. 

