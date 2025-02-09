# Component Selection

This page documents my component selection process, including the options considered for each major subsystem and the reasoning behind my choices for supporting hardware. Due to project requirements, only surface-mount components will be considered.

## Subsystem Functionality
My role in our team's simulated wind tunnel project is to manage the airspeed display. The system includes a small airplane on a pivot with streamers to visualize airflow, along with a 7-segment display that indicates wind speed. The wind speed values are controlled by an operator using dials. To ensure seamless communication between subsystems, our team has chosen to use UART, forwarding messages with headers to identify their sources. Since response time is not critical, this approach should work as long as each microcontroller has enough data storage to queue and transmit the necessary information.

### Microcontroller Selection
Solution    | Image | Pros   | Cons  | Datasheet
------------|-------|--------|-------|----------
PIC18F47Q10 TQFP/44 | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/4564/150%7EC04-076%7EPT%7E44.JPG) |- High Memory <br> - Rich Peripherals <br> - Hardware CLC | - Higher Power Consumption <br> - More Expensive <br> - More Complex to Program | [Datasheet](https://www.digikey.com/en/products/detail/microchip-technology/PIC18F47Q10-I-PT/10187786)
MC9S08PA32AVLCR | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/6347/568%7ESOT358-3%7EAC%2CFA%2CFJ%2CLC%2CPB%7E32.jpg) | - Efficient 8-bit Performance <br> - Integrated Peripherials <br> - Lower Cost | - Limited Memory <br> - Slower Processing <br> - Limited Community Support | [Datasheet](https://www.nxp.com/docs/en/data-sheet/MC9S08PA60_Rev1.pdf)
ATTINY202-SSFR | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/4818/150%3B-8S1%3B-%3B-8.jpg) | - Ultra Low Power <br> - Compact Package <br> - Simple Programming | - Limited Memory <br> - Minimal Peripherals <br> - Lower Processing | [Datasheet](http://ww1.microchip.com/downloads/en/DeviceDoc/ATtiny202-402-AVR-MCU-with-Core-Independent-Peripherals_and-picoPower-40001969A.pdf)

__Selection:__ I chose the PIC18F47Q10 (TQFP/44) for my airspeed display because its successful integration with other systems will largely determine the projects scope. The availability of both provided and sourced information will be crucial to the final system's functionality. Additionaly, using the same microcontroller as other students provides access to broader knowledge base, and the labs leading up to the final project will help refine my skills with this specific controller.

### Pitot Tube Sensor (__NEED TO TALK WITH TEAM__)
Solution    | Image | Pros   | Cons  | Datasheet
------------|-------|--------|-------|----------
Component 1 | ![Image]() | - Benfit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 3 | [Datasheet]()
Component 2 | ![Image]() | - Benfit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 3 | [Datasheet]()
Component 3 | ![Image]() | - Benfit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 3 | [Datasheet]()

### OLED
Solution    | Image | Pros   | Cons  | Datasheet
------------|-------|--------|-------|----------
XDCBD14A | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/3750/MFG_XDCBD14A.jpg) | - Bright Illumination <br> - Standard 10-DIP <br> - Moderate Power Consumption | - Single-digit Display <br> - Common anode configuration may not be compatible with all driver circuits <br> - Limited viewing angle | [Datasheet](https://www.sunledusa.com/products/spec/XDCBD14A.pdf)
COM-13999 | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/2173/MFG_COM-13999.jpg) | - RGB capability <br> - Dual-digit design <br> - Standard 14-DIP | - Higher Power consumption <br> - More complex control circuitry <br> - Slightly larger footprint | [Datasheet](https://cdn.sparkfun.com/datasheets/Components/LED/ACD8143.pdf)
TDCR1050M | ![Image](https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/1123/TDCG1060M.JPG) | - Four-digit display <br> - Compact design <br> - Low forward voltage | - Smaller digit size <br> - Red illumination <br> - Common anode configuration | [Datasheet](https://www.vishay.com/docs/83180/tdcx10x0m.pdf)

__Selection:__ I chose the XDCBD14A for my airspeed display because its blue LED segments provide high visibility, ensuring that airspeed values are easy to read in various lighting conditions. The 0.56" digit size offers a good balance between readablitiy and compactness, making it a suitable choice for my system. Additionally, the common anode configuration allows for flexible interfacing with standard driver circuits.

[Back to Home](index.md)