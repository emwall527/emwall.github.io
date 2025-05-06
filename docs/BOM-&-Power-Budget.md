# Bill of Materials & Power Budget

## Bill of Materials (__Last Edited__: 5/5/2025)

### Description
The bill of materials lists all components across documents, including their quantity, model number, and manufacturer. It will be updated as final part selections are made. For certain components, such as resistors, bulk ordering will be used to simplify procurement and reduce the need for individual orders. To ensure seamless integration, all resistors will be kept at a consistent size regardless of the final selection.

![Bill of Materials](https://raw.githubusercontent.com/emwall527/emwall.github.io/refs/heads/main/Pictures/Wind%20Speed%20Subsystem%20V2%20BOM.jpg)

## Power Budget (__Last Edited__: 2/25/2025)

### Description
To ensure sufficient power delivery for all required hardware, I have generated this power budget to illustrate the power allocation necessary to operate key components. The primary power draw comes from the Vybronics DC motor when in motion, while the PIC18F27/47Q10 and SunLED contribute minor consumption.

![Power Budget](https://raw.githubusercontent.com/emwall527/emwall.github.io/refs/heads/main/Pictures/Power%20Budget%20for%20Subsystem.jpg)

### How the Power Budget was used
The Power Budget table helps estimate the system’s power needs by detailing the minimum and maximum power consumption for each component. The PIC18F47Q10 microcontroller draws 10mA in active mode, serving as the central control unit. The Vybronics DC Motor draws 0mA when inactive and up to 60mA when running, making it the largest power consumer. The SunLED XDCBD14A display uses 0mA when off and 20mA when on. The total minimum power draw is 10mA, and the maximum draw is 90mA, which occurs when the motor is at full speed and the display is on. These values confirm that the system requires a 3.3V supply capable of delivering at least 100mA, with sufficient headroom for safe operation. The system is power-efficient, with the motor being the primary power consumer, and careful management can further reduce power use.



__Made__: 2/25/2025

[Back to Home](index.md)