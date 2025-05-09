# Component Selection

This page documents my component selection process, including the options considered for each major subsystem and the reasoning behind my choices for supporting hardware. Due to project requirements, only surface-mount components will be considered.

## Subsystem Functionality
My role in our team's simulated wind tunnel project is to manage the airspeed display. The system includes a small airplane on a pivot with streamers to visualize airflow, along with a 7-segment display that indicates wind speed. The wind speed values are controlled by an operator using dials. To ensure seamless communication between subsystems, our team has chosen to use UART, forwarding messages with headers to identify their sources. Since response time is not critical, this approach should work as long as each microcontroller has enough data storage to queue and transmit the necessary information.

### Microcontroller Selection (__Last Edited__: 5/5/2025)

Solution    | Image | Pros   | Cons  | Datasheet | Price
------------|-------|--------|-------|-----------|------
__PIC18F47Q10 TQFP/44__ | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/4564/150%7EC04-076%7EPT%7E44.JPG) |- High Memory <br> - Rich Peripherals <br> - Hardware CLC | - Higher Power Consumption <br> - More Expensive <br> - More Complex to Program | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27-47Q10-Data-Sheet-40002043E.pdf) | $1.64
MC9S08PA32AVLCR | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/6347/568%7ESOT358-3%7EAC%2CFA%2CFJ%2CLC%2CPB%7E32.jpg) | - Efficient 8-bit Performance <br> - Integrated Peripherals <br> - Lower Cost | - Limited Memory <br> - Slower Processing <br> - Limited Community Support | [Datasheet](https://www.nxp.com/docs/en/data-sheet/MC9S08PA60_Rev1.pdf) | $2.86
ATTINY202-SSFR | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/4818/150%3B-8S1%3B-%3B-8.jpg) | - Ultra Low Power <br> - Compact Package <br> - Simple Programming | - Limited Memory <br> - Minimal Peripherals <br> - Lower Processing | [Datasheet](http://ww1.microchip.com/downloads/en/DeviceDoc/ATtiny202-402-AVR-MCU-with-Core-Independent-Peripherals_and-picoPower-40001969A.pdf) | $0.50

__Selection__: I chose the PIC18F47Q10 (TQFP/44) for my airspeed display because its successful integration with other systems will largely determine the project's scope. The availability of both provided and sourced information will be crucial to the final system's functionality. Additionally, using the same microcontroller as other students provides access to a broader knowledge base, and the labs leading up to the final project will help refine my skills with this specific controller.

---

### Anemometer (__Last Edited__: 5/5/2025)

__Explanation__: Our team plans to build a custom anemometer for our project, designed to measure the speed of the fan in our wind tunnel. The component selection will include a motor which is needed for the anemometer, because we want the motor to be spinning from our provided wind speed so we can read the input and convert the motor readings to wind speed as the output.

Solution    | Image | Pros   | Cons  | Datasheet | Price
------------|-------|--------|-------|-----------|------
__VQ4TL2BQ380001__ | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/2543/MFG_Q4_MICRO-MOTOR.jpg) | - High RPM <br> - Compact size <br> - Low voltage operation | - Low torque <br> - No built-in gearing <br> - High RPM (Might require more circuitry to handle) | [Datasheet](https://www.vybronics.com/dc-micro-drive-motors/v-q4tl2bq380001) | $4.04
ROB-11696 | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/1794/MFG_ROB-11696.jpg) | - Moderate RPM <br> - Reliable performance <br> - Suitable for general applications | - May require higher wind speeds <br> - Higher voltage <br> - Slightly larger | [Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/951/ROB-11696_Web.pdf) | $2.76
FIT0564 | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/3167/FIT0564.jpg) | - Built-in gearbox increases torque <br> - Lower no-load RPM <br> - Can handle a wider range of applications | - May not see changes in wind speed <br> - Larger size compared to other motors <br> - Requires more power | [Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/778/FIT0564_Web.pdf) | $9.90

__Selection__: The Vybronics VQ4TL2BQ380001 motor was chosen because of its high RPM (24,927 RPM), which makes it highly responsive to changes in wind speed. Its compact size allows for easy integration into our anemometer design without adding unnecessary weight or bulk. Additionally, its low operating voltage (3VDC) ensures efficient power use while still generating a measurable voltage output for wind speed calculations.

---

### OLED (__Last Edited__: 5/5/2025)

Solution    | Image | Pros   | Cons  | Datasheet | Price
------------|-------|--------|-------|-----------|------
__XDCBD14A__ | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/3750/MFG_XDCBD14A.jpg) | - Bright Illumination <br> - Standard 10-DIP <br> - Moderate Power Consumption | - Single-digit Display <br> - Common anode configuration may not be compatible with all driver circuits <br> - Limited viewing angle | [Datasheet](https://www.sunledusa.com/products/spec/XDCBD14A.pdf) | $2.97
COM-13999 | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/2173/MFG_COM-13999.jpg) | - RGB capability <br> - Dual-digit design <br> - Standard 14-DIP | - Higher Power consumption <br> - More complex control circuitry <br> - Slightly larger footprint | [Datasheet](https://cdn.sparkfun.com/datasheets/Components/LED/ACD8143.pdf) | $4.68
TDCR1050M | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/1123/TDCG1060M.JPG) | - Four-digit display <br> - Compact design <br> - Low forward voltage | - Smaller digit size <br> - Red illumination <br> - Common anode configuration | [Datasheet](https://www.vishay.com/docs/83180/tdcx10x0m.pdf) | $3.34

__Selection__: I chose the XDCBD14A for my airspeed display because its blue LED segments provide high visibility, ensuring that airspeed values are easy to read in various lighting conditions. The 0.56" digit size offers a good balance between readability and compactness, making it a suitable choice for my system. Additionally, the common anode configuration allows for flexible interfacing with standard driver circuits.

---

### LED Driver (__Last Edited__: 5/5/2025)

Solution    | Image | Pros   | Cons  | Datasheet | Price
------------|-------|--------|-------|-----------|------
__AS1115-BSST__ | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/382/AS1116-BSST.jpg) | - Supports up to 8 digits <br> - Operates at 3.3V <br> - Simple I²C interface | - Limited expandability beyond 8 digits <br> - Only supports I²C, no SPI option <br> - May require external resistors for LED current control | [Datasheet](https://look.ams-osram.com/m/7ed04145f58f44e2/original/AS1115-DS000206%20Datasheet) | $4.21
MAX6958AAEE+T | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/5350/175%7E21-0055%7EEE%7E16.JPG) | - Operates at 3.3V <br> - I²C-compatible <br> - Compact 16-QSOP package | - Only supports up to 4 digits <br> - Limited segment outputs <br> - Less community support | [Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/max6958-max6959.pdf) | $13.77
MAX6955AAX+ | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/6347/175%7E21-0040%7EAX%7E36.jpg) | - Supports up to 16 digits <br> - 3.3V compatible <br> - I²C interface | - Larger 36-SSOP package <br> - More complex setup for basic needs <br> - Higher power consumption | [Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/MAX6955.pdf) | $31.18

__Selection__: I chose the AS1115-BSST for my LED driver because it supports up to 8 digits, which meets my requirement of driving 4–5 XDCBD14A 7-segment displays. It operates at 3.3V, ensuring compatibility with my PIC18F47K40 microcontroller without additional voltage level shifting. The I²C interface simplifies communication, reducing the number of required microcontroller pins while maintaining efficient data transfer. Additionally, its compact design and built-in scanning capabilities make it an ideal choice for displaying real-time airspeed values from the anemometer in my wind tunnel project.

### Major Components Summary Table (__Last Edited__: 5/5/2025)

| Component                | Description                          | Part Number                   | Price  | Datasheet                                      |
|--------------------------|--------------------------------------|-------------------------------|--------|------------------------------------------------|
| **Microcontroller**       | Central control for the system       | **PIC18F47Q10 TQFP/44**        | $1.64  | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27-47Q10-Data-Sheet-40002043E.pdf) |
| **Anemometer Motor**      | Measures fan speed                   | **VQ4TL2BQ380001**             | $4.04  | [Datasheet](https://www.vybronics.com/dc-micro-drive-motors/v-q4tl2bq380001) |
| **7-Segment Display**     | Display airspeed readings            | **XDCBD14A**                   | $2.97  | [Datasheet](https://www.sunledusa.com/products/spec/XDCBD14A.pdf) |
| **LED Driver**            | Drives the 7-segment display         | **AS1115-BSST**                | $4.21  | [Datasheet](https://look.ams-osram.com/m/7ed04145f58f44e2/original/AS1115-DS000206%20Datasheet) |


__Made__: 2/7/2025

[Back to Home](index.md)