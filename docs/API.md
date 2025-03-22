## Message Type

We use different types of messages that need to be sent using this standard. Thanks to the header and footer setup, the messages can be different sizes. Below is a list of the message types and their lengths. All messages are also picked up by the Wi-Fi system so the operator can see them live on the web interface. The web interface can also send fake messages to replace commands from the user.

Each subsystem address is laid out below (__Last Edited__: 3/22/2025)

| Member           | Subsystem              | Address |
|------------------|------------------------|---------|
| Dominick Trusko  | Pitch-Control and Wifi | 0x06    |
| Cory Lewis       | Fan Speed Controller   | 0x07    |
| Adam Quan        | Human Interface        | 0x08    |
| Emerson Wall     | Windspeed Display      | 0x09    |
| All              | All Subsystems         | 0x10    |


## Example Key: (__Last Edited__: 3/22/2025)

<span style="color:blue"><strong>BLUE</strong></span>: All common message components (i.e., Headers/Footers)  
<span style="color:red"><strong>RED</strong></span>: The local address for my subsystem  
<span style="color:green"><strong>GREEN</strong></span>: The address for all devices  

Including headers and footers isn’t required for the assignment, but they’ll help me and my team during production by giving us better reference information. So, they will stay in this document.
The messages don’t need data type declarations. Since the data values don’t overlap, the receiver can figure out what the message means by checking who sent it and who it's meant for (either a specific device or all devices).

| TX/RX | Message Name     | Data Type | Range     | Size                   | Description                                         | Example                                                                 |
|-------|------------------|-----------|-----------|------------------------|-----------------------------------------------------|-------------------------------------------------------------------------|
| TX    | Ready to Receive | uint_8    | [253]     | 8 Bits [56 Bits Total] | Notifies subsystems that ready commands can be received | <span style="color:blue">[0x41][0x5a]</span> <br> <span style="color:red">[0x6]</span> <span style="color:green">[0x10]</span> [0xF3] <br> <span style="color:blue">[0x59][0x42]</span> |
| TX    | Initialize Clock | uint_8    | [255]     | 8 Bits [56 Bits Total] | Tells all devices to start their send clock        | <span style="color:blue">[0x41][0x5a]</span> <br> <span style="color:red">[0x6]</span> <span style="color:green">[0x10]</span> [0xF5] <br> <span style="color:blue">[0x59][0x42]</span> |
| TX    | Emergency Stop   | uint_8    | [244]     | 8 Bits [56 Bits Total] | Commands all devices to cease operation            | <span style="color:blue">[0x41][0x5a]</span> <br> <span style="color:red">[0x6]</span> <span style="color:green">[0x10]</span> [0xF4] <br> <span style="color:blue">[0x59][0x42]</span> |
| RX    | No Report        | uint_8    | [0]       | 8 Bits [56 Bits Total] | Indicates to master device that no new information is available | <span style="color:blue">[0x41][0x5a]</span> <br> [0x09] <span style="color:red">[0x6]</span> [0x43] <br> <span style="color:blue">[0x59][0x42]</span> |
| RX    | True Airspeed    | uint_8    | [0–255]   | 8 Bits [56 Bits Total] | Airspeed reporting from Windspeed subsystem        | <span style="color:blue">[0x41][0x5a]</span> <br> [0x09] <span style="color:green">[0x10]</span> [0x43] <br> <span style="color:blue">[0x59][0x42]</span> |
| RX    | Airspeed Target  | uint_8    | [0–100]   | 8 Bits [56 Bits Total] | Airspeed dial target (Reported to web interface)   | <span style="color:blue">[0x41][0x5a]</span> <br> [0x08] <span style="color:green">[0x10]</span> [0x44] <br> <span style="color:blue">[0x59][0x42]</span> |
| RX    | Pitch Target     | uint_8    | [101–201] | 8 Bits [56 Bits Total] | Pitch dial target                                  | <span style="color:blue">[0x41][0x5a]</span> <br> [0x08] <span style="color:green">[0x10]</span> [0x67] <br> <span style="color:blue">[0x59][0x42]</span> |
| RX    | Current Fan Speed| uint_8    | [0–100]   | 8 Bits [56 Bits Total] | Current Fan Speed (Reported to web interface)      | <span style="color:blue">[0x41][0x5a]</span> <br> [0x09] <span style="color:green">[0x10]</span> [0x2B] <br> <span style="color:blue">[0x59][0x42]</span> |

__Made__: 3/22/2025

[Back to Home](index.md)