# Component Selection

This page documents my component selection process, including the options considered for each major subsystem and the reasoning behind my choices for supporting hardware. Due to project requirements, only surface-mount components will be considered.

## Subsystem Functionality
My role in our team's simulated wind tunnel project is to manage the airspeed display. The system includes a small airplane on a pivot with streamers to visualize airflow, along with a 7-segment display that indicates wind speed. The wind speed values are controlled by an operator using dials. To ensure seamless communication between subsystems, our team has chosen to use UART, forwarding messages with headers to identify their sources. Since response time is not critical, this approach should work as long as each microcontroller has enough data storage to queue and transmit the necessary information.

### Microcontroller Selection
Solution    | Pros   | Cons
------------|--------|-------
PIC18F47Q10 TQFP/44 | *Benfit 1 <br> *Benefit 2 <br> *Benefit 3 | *Drawback <br> *Drawback <br> *Drawback
Component 2 | filler | filler
Component 3 | filler | filler

### Pitot Tube Sensor
Solution    | Pros   | Cons
------------|--------|-------
Component 1 | filler | filler
Component 2 | filler | filler
Component 3 | filler | filler

### OLED
Solution    | Pros   | Cons
------------|--------|-------
Component 1 | filler | filler
Component 2 | filler | filler
Component 3 | filler | filler

[Back to Home](index.md)