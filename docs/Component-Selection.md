# Component Selection

This page documents my component selection process, including the options considered for each major subsystem and the reasoning behind my choices for supporting hardware. Due to project requirements, only surface-mount components will be considered.

## Subsystem Functionality
My role in our team's simulated wind tunnel project is to manage the airspeed display. The system includes a small airplane on a pivot with streamers to visualize airflow, along with a 7-segment display that indicates wind speed. The wind speed values are controlled by an operator using dials. To ensure seamless communication between subsystems, our team has chosen to use UART, forwarding messages with headers to identify their sources. Since response time is not critical, this approach should work as long as each microcontroller has enough data storage to queue and transmit the necessary information.

### Microcontroller Selection
Solution    | Image | Pros   | Cons  | Datasheet
------------|-------|--------|-------|----------
PIC18F47Q10 TQFP/44 | [Image] |- Benefit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 2
Component 2 | [Image] | - Benfit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 3
Component 3 | [Image] | - Benfit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 3

### Pitot Tube Sensor
Solution    | Image | Pros   | Cons  | Datasheet
------------|-------|--------|-------|----------
Component 1 | [Image] | - Benfit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 3 | [Datasheet]
Component 2 | [Image] | - Benfit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 3 | [Datasheet]
Component 3 | [Image] | - Benfit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 3 | [Datasheet]

### OLED
Solution    | Image | Pros   | Cons  | Datasheet
------------|-------|--------|-------|----------
Component 1 | [Image] | - Benfit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 3 | [Datasheet]
Component 2 | [Image] | - Benfit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 3 | [Datasheet]
Component 3 | [Image] | - Benfit 1 <br> - Benefit 2 <br> - Benefit 3 | - Drawback 1 <br> - Drawback 2 <br> - Drawback 3 | [Datasheet]

[Back to Home](index.md)