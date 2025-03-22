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



Message Type 1:

|-----------    | Byte 5-6      | Byte 7        |   Byte 8 |
|------------   | --------------| ------------- | ------------- |
| Variable Name | message_type  | motor_id      | motor_direction |
|Variable Type  | char          | char          | int8_t |
| Min Value     | 1             | 1             | -1 |
| Max Value     | 8             | 3             | 1 |
| Example       | 1             | 2             | -1 |


Message Type 2:

|-----------    | Byte 5-6     | Byte 7        | Byte 8 |
|------------   | -------------| ------------- | ------------- |
| Variable Name | message_type | sensor_id     | sensor_value |
| Variable Type | char         | char          | char |
| Min Value     | 1            | 1             | 0 |
| Max Value     | 8            | 2             |  100 |
| Example       | 3            | 2             | 23 |


Message Type 3:

|------------| Byte 5 - Byte 6 | Byte 7 |
|------------| --------------| ------------- |
| Variable Name | message_type | subsystem_id |
|Variable Type | char | char |
| Min Value | 1 | a |
| Max Value| 7 | d |
| Example | 5 | c |


Message Type 4:

|----------  | Byte 5 - Byte 6 | Byte 7 |
|------------| --------------| ------------- |
| Variable Name | message_type | motor_status |
|Variable Type | char | uint8_t |
| Min Value | 1 | 0 |
| Max Value| 7 | 1 |
| Example | 4 | 0 |


Message Type 5:

|------------| Byte 5 - Byte 6 | Byte 7 |
|------------| --------------| ------------- |
| Variable Name | message_type | motor_speed |
|Variable Type | char | uint8_t |
| Min Value | 1 | -100 |
| Max Value| 7 | 100 |
| Example | 2 | 56|

