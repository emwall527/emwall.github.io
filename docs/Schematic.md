# Schematic and PCB

## Description

This schematic represents the individual board design based on our team's assigned block diagram. The design integrates a PIC18F46K40-I/PT microcontroller with key peripherals, enabling efficient data processing and communication.

## Schematic (__Last Updated__:5/5/2025)
![Schematic](https://raw.githubusercontent.com/emwall527/emwall.github.io/refs/heads/main/Pictures/Wind%20Speed%20Subsystem%20V2%20Schematic.jpg)

### Functionality
The schematic effectively meets the user needs and product requirements by integrating key components for real-time airspeed measurement and display. The PIC18F47Q10 microcontroller processes data from the anemometer, controlling the LED driver (AS1115-BSST) to update the 7-segment display with airspeed values. The 3.3V regulator ensures stable power for the system, converting the 12V input to the required 3.3V, which is essential for efficient operation. The MPLAB SNAP interface allows for programming and debugging, ensuring smooth development and testing.

The anemometer provides accurate data on the fan speed, which is processed by the microcontroller and displayed on the 7-segment display. The LED driver ensures the display is clear and visible, meeting the requirement for real-time monitoring of airspeed. Overall, the schematic design provides efficient power management, clear data presentation, and flexibility for future modifications, fully supporting the functionality of the wind tunnel airspeed measurement system.

## PCB (__Last Updated__:5/5/2025)
![PCB](https://raw.githubusercontent.com/emwall527/emwall.github.io/refs/heads/main/Pictures/Wind%20Speed%20Subsystem%20PCB%20(Front).jpg)


__Made__: 2/21/2025

[Back to Home](index.md)