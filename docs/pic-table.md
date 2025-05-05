---
title: PIC Table
---

| ESP Info                                      | Answer |
| --------------------------------------------- | ------ |
| Model                                         | PIC18F47Q10 |
| Product Page URL                              | [link](https://www.microchip.com/en-us/product/pic18f47q10) |
| Datasheet URL(s)                              | [link](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27_47Q10-data-sheet-40002043C.pdf) |
| Application Notes URL(s)                      | [link](https://ww1.microchip.com/downloads/en/Appnotes/AN3174-Getting-Started-with-PIC18-Q10-00003174A.pdf) |
| Vendor link                                   | [link](https://www.digikey.com/en/products/detail/microchip-technology/PIC18F47Q10-I-PT/10187786) |
| Code Examples                                 | [link](https://github.com/microchip-pic-avr-examples/pic18f47q10-cnano-eusart-hello-world-fs) |
| External Resources URL(s)                     | [link](https://www.youtube.com/watch?v=J-nBlnyPI14) |
| Unit cost                                     | $1.64 |
| Absolute Maximum Current for entire IC        | 185 mA |
| Supply Voltage Range                          | 1.8V / 3.3V / 5.5V / 5.5V |
| Absolute Maximum current (for entire IC)      | 185 mA |
| Maximum GPIO current (per pin)                | 25 mA |
| Supports External Interrupts?                 | Yes |
| Required Programming Hardware, Cost, URL      | Curiosity Nano Board, $15, [link](https://www.microchipdirect.com/dev-tools/DM182029) |
| Works with MPLabX?                            | Yes |
| Works with Microchip Code Configurator?       | Yes |



| Module | # Available | Needed | Associated Pins (or * for any) |
|--------|-------------|--------|--------------------------------|
| GPIO   | 36          | ~10    | *                              |
| ADC    | 35 channels | 1–2    | ANx pins (e.g., RA0, RA1, etc.)|
| UART   | 2 (EUSART)  | 1      | TX1/RX1 (RC6/RC7), TX2/RX2 (RB6/RB7) |
| SPI    | 1 (MSSP)    | 1      | SDO/SCK/SDI (e.g., RC3, RC4, RC5) |
| I2C    | 1 (MSSP)    | 1      | SDA/SCL (e.g., RC3, RC4)       |
| PWM    | 6 (CCP/CLC) | 1–2    | CCPx (e.g., RC2, RC1, RB3, etc.) |
| ICSP   | 1           | 1      | PGD/PGC (RA0/RA1 or RB6/RB7 depending on setup) |

__Made__: 5/5/2025

[Back to Home](index.md)