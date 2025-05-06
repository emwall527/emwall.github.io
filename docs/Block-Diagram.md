# Block Diagram

## Description
Below is the block diagram for my individual subsystem,this subsytem recieves the signal for changing the wind speed and indicating what the wind speed is at.

## Diagram (__Last Edited__: 2/25/2025)
![Block Diagram](https://raw.githubusercontent.com/emwall527/emwall.github.io/refs/heads/main/Pictures/New%20Block%20Diagram.png)

### How it Meets Product Requirement (__Made__: 5/5/2025)
The block diagram was designed to meet the product requirements of reading and displaying fan speed, updating the display in real-time, and reporting the data to the input device board. The system is powered by a 12V power supply, which is regulated to 3.3V for the microcontroller and other components. The PIC18F47Q10 microcontroller receives fan speed data from the anemometer, decodes it, and sends it to the LED Driver via I2C. The LED Driver then controls the 7-segment display to show the fan speed.

Real-time data is processed by the microcontroller, which communicates with the LED Driver to update the display immediately. The 3.3V switching regulator ensures proper voltage levels for all components. This design efficiently handles the reading, decoding, and displaying of fan speed while maintaining simple communication between the microcontroller, anemometer, and display system. The MPLAB SNAP interface is included for easy programming and debugging.

__Made__: 1/31/2025

[Back to Home](index.md)