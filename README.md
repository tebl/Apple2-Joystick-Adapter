# Apple ][ Joystick Adapter
I have an Apple ][ somewhere in my storage room, I don't play on the thing much. Part of the reason might be the lack of a joystick, so I've been attempting to remedy that by soldering something together - the hard, and quite possibly the only real classic way, by reading about them in an old book and attempt to actually build the thing (Computer Controller Cookbook).

![Installation done](https://github.com/tebl/Apple2-Joystick-Adapter/raw/main/gallery/2021-01-31%2020.42.28.jpg)

The adapter allows you to connect up to two Atari-style joysticks up to the Apple ][, if you like that sort of thing. I'm told most Apple fans prefer their joysticks to be analog because that was all the rage was all about at the end of the 70s, but as already mentioned I don't have one - I on the other hand have a ton of Atari-style joysticks so those are the ones I'd like to use. Keep reading for all the necessary details, click links below if you want to skip to a specific section.

- [1> Building the adapter](#1-building-the-adapter)
  - [1.2> IDC-cables](#12-idc-cables)
- [2> BOM](#2-bom)
  - [2.1> Miscellaneous components](#21-miscellaneous-components)

# 1> Building the adapter
Building the adapter, as with most things that deals with electronic projects, starts with going through the [BOM](#2-bom) and ordering whatever you don't already have. Compare with the gallery pictures if you're wondering what something looks like, unfortunately ebay is not a good place to shop for well-described components - I usually just order one of each if they're cheap (it'll get used sometime, if only to irritate someone attempting to build more than one of my projects).

Next up is soldering the resistors, these are have the lowest profile of the components and move up in size from that point forward. Please use sockets though, mainly because everything that looks like ICs from ebay can and should be considered highly suspicious until verified working - you will likely want the ability to quickly change one of them out (often they are B-grade or forcibly pulled from other hardware; they may or may not working depending on your luck).

![Front of PCB](https://github.com/tebl/Apple2-Joystick-Adapter/raw/main/gallery/2021-01-21%2022.52.42.jpg)

The last component to get soldered into place are the machined pin headers that go into the area labelled A1, these go into the Game I/O socket on the Apple ][ motherboard - the regular kind will probably break your socket, so don't use those (even if they are cheap). They are soldered on the reverse side compared to the other components, to ensure that they are soldered into place at a reasonable angle, I recommend using a 16 pin machined pin socket as a template below the pins.

![Back of PCB](https://github.com/tebl/Apple2-Joystick-Adapter/raw/main/gallery/2021-01-21%2022.52.50.jpg)

The last step I usually do with my boards, is installing an M3 nylon standoff (10mm length) into the hole between the IDC connectors - this is there so that there is some strain relief for the pins that go into the socket. It just pushes against the motherboard, so don't use the brass one as that might accidentally short something.

Onto the next step, because everyone loves making cables.

## 1.2> IDC-cables
While I would have liked to just use something that could be ordered straight from AliExpress without going so far as creating a custom cable, all of the ones I've found were mostly IDC to RS232 adapters - those have a rather randomized pin layout so I chose not to use them as a basis. The method I used instead was order said cables, cut off the DB9 part and then just add a new male DB9 IDC connector that lines up pin 1 with pin 1.

You can create the whole cable by yourself, should you choose to do so. Soldering connectors do kind of suck, so I've listed IDC connectors in the miscellaneous section - these are assembled by aligning pin 1 of the flat cable with pin 1 of the connector, then just push really hard down on it with something hard (if you don't have a vise) like the handle of a screwdriver. Note that the 2x5pin IDC side will have a spot for a tenth wire, this is left empty as the DB9 side only requires the 9 wires.

# 2> BOM
This is the list of parts that you'd need in order to construct Apple ][ Joystick Adapter, most could quite possibly be sourced from your friendly neighbourhood electronics store - if you should happen to have one available (using a passport on the way doesn't count). I don't, so I order most of the components on ebay and similar sources - parts may be cheap, but at least you'll need extras in order to assure at least one of them works.

| Reference            | Item                                              | Count |
| -------------------- | ------------------------------------------------- | ----- |
| Adapter (PCB)        | Fabricate using Gerber files ([order]())          |     1 |
| A1 *                 | 8 pin machined pin header                         |     2 |    
| C1,C2                | 100nF ceramic capacitor (5mm)                     |     2 |
| C3                   | 4.7uF electrolytic capacitor (2mm)                |     1 |
| IC1                  | 74HCT04 (DIP-14)                                  |     1 |
| IC2                  | CD4066 (DIP-14)                                   |     1 |
| J1,J2                | 2x5 pin straight IDC socket                       |     2 |
| R1-R6                | 1k Ohm resistor                                   |     6 |
| R7-R10               | 68k Ohm resistor                                  |     4 |
| R11-R14              | 100k Ohm resistor                                 |     4 |

*) These are soldered on the reverse side compared to the other components, these pins go into the Game I/O socket on the Apple ][ motherboard. These are usually sold as 40 pin breakable strips, it is recommended to use the machined pin headers as they won't destroy the motherboard socket like the regular pin header eventually would.

## 2.1> Miscellaneous components
This is a suggested list of components used to screw together each of the PCBs, most of these you can find as part of a set on ebay (just search for "*M3 nylon assorted standoff kit*"). Cable components are also listed here.

| Reference | Item                                      | Count |
| --------- | ----------------------------------------- | ----- |
|           | M3x6mm nylon screw                        |     1 |
|           | M3x10mm Nylon Hex standoff                |     1 |
|           | IDC Flat Ribbon DB9 Male Connector        |     2 |
|           | 2x5 Flat Riboon IDC Connector             |     2 |
|           | 9 core flat ribbon cable                  |     2 |