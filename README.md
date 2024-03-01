# Speed Sensor

## Introduction
Speed Sensor with the LM393 Sensors, Arduino Nano and Seeed CAN-BUS Shield V2.0. <br>
Estimate the car's RPM at the axle. <br>
Reads the LM393 speedsensor and calculates the RPM value. <br>

## System
### Hardware 
- [LM393 speedsensor](https://cdn-reichelt.de/documents/datenblatt/A300/SEN-SPEED-DATASHEET.pdf)
- [Arduino Uno R3](https://eckstein-shop.de/HIMALAYAbasicUNOR3ATmega328PBoardATmega16U2mitUSBKabelArduinoUnoR3kompatibelEN)
- [CAN-BUS_Shield_V2.0](https://wiki.seeedstudio.com/CAN-BUS_Shield_V2.0/)

### Wiring

## CAN Frame
The calculated the RPM value is sent in byte 0 & byte 1 of the CAN Bus frame. <br>
The maximum rpm that can be measured is 1800 1/min. <br> 
Therfore we need 2 bytes in the CAN frames' payload. <br>
The can frame is structured as follows: <br>
Byte 0 - 1: RPM VALUE <br>
The rpm value in 1/min are displayed and sent in hex format. <br>
Example: <br>
```c
Set data from ID: 0x100
0	A3	
-----------------------------
Set data from ID: 0x100
0	6	
-----------------------------
```
