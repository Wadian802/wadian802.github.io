---
Application Programming Interface or API  Messaging
---
The software between the motor, hall effect sensor, wifi and OLED screen all need to communicate to perform a function and communicate that function to a user. 
The interfacing between these components means that each part can speak to another part. 

Provided is a sample of messages the stepper motor will send or receive between other sensors. 

Message Structure:  

| Message Type <br /> byte 1-2 <br /> (char)         | Description |
| --------------------------------------------- | ----------- |
|1                                              | Set motor X direction |
|2                                              | Print sensor X value Y |
|3                                              | Subsystem X id|
|4                                              | Motor Status, X |
|5                                              | Set motor speed |


Team ID:

| Name   | Alex | Frank | Luis | Tyler | Broadcasting|
|--------|------|-------|------|-------|------------|
| Letter | a    | b     | d    | c     | X|


Structure of the Message

|Bytes	|Byte 1	|  Byte 2	|  Byte 3	| Byte 4	|Byte 5| 	Byte 6 |	Byte 7 |	Byte 8|
|-----|-----|-----|-----|-----|-----|-----|-----|-----|
|Contents|	'A'	|'Z'|	Sender Letter |Receiver Letter|	Message Letter |Message contents	|'Y'	|'B'| 


Message Type 1:  

|-----------    | Byte 5      | Byte 6       |   Byte 7 |
|------------   | --------------| ------------- | ------------- |
| Variable Name | message_type  | motor_id      | motor_direction |
|Variable Type  | char          | char          | int8_t |
| Min Value     | 1             | 1             | 0 |
| Max Value     | 1             |  3            | 2 |
| Example       | 1             | 2             | 2 |


Message Type 2:  

|-----------    | Byte 5    | Byte 6       | Byte 7   |
|------------   | -------------| ------------- | ------------- |
| Variable Name | message_type | sensor_id     | sensor_value |
| Variable Type | char         | char          | char |
| Min Value     | 1            | 1             | 0 |
| Max Value     | 2            | 2             |  100 |
| Example       | 2            | 2            | 25 |


Message Type 3:  

|------------| Byte 5  | Byte 6 |
|------------| --------------| ------------- |
| Variable Name | message_type | subsystem_id |
|Variable Type | char | char |
| Min Value | 5 | a |
| Max Value| 5 | d |
| Example | 5 | c |


Message Type 4:  

|----------  | Byte 5  | Byte 6 |
|------------| --------------| ------------- |
| Variable Name | message_type | motor_status |
|Variable Type | char | uint8_t |
| Min Value | 6 | 0 |
| Max Value| 6 | 1 |
| Example | 6 | 1 |


Message Type 5:  

|------------| Byte 5 | Byte  6|
|------------| --------------| ------------- |
| Variable Name | message_type | motor_speed |
|Variable Type | char | uint8_t |
| Min Value | 1 | -100 |
| Max Value| 7 | 100 |
| Example | 2 | 56|


Message Broadcast :

|----|Byte 5|	Byte 6 - Byte 55|
|-----|-------|-------|
|Variable Name | 	message_type	| broadcast_message|
|Variable Type	|int8_t	|string|
|Min Value|	8	|Minimum value is 1 character|
|Max Value	|8	|Max value is 48 characters|
|Example	|8	|This is broadcast |

