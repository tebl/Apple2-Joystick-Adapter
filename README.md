# Apple ][ Joystick Adapter
I have an Apple //e somewhere in my storage room, I don't play on the thing much. Part of the reason might be the lack of a joystick, so I've been attempting to remedy that by soldering something together - the hard, and quite possibly the only real classic way, by reading about them in an old book and attempt to actually build the thing (Computer Controller Cookbook).

![Installation done](https://github.com/tebl/Apple2-Joystick-Adapter/raw/main/gallery/2021-01-31%2020.42.28.jpg)

The adapter allows you to connect up to two Atari-style joysticks up to the Apple //e, if you like that sort of thing. I'm told most Apple fans prefer their joysticks to be analog because that was all the rage was all about at the end of the 70s, but as already mentioned I don't have one - I on the other hand have a ton of Atari-style joysticks so those are the ones I'd like to use. Keep reading for all the necessary details, click links below if you want to skip to a specific section.

- [1> Building the adapter](#1-building-the-adapter)
  - [1.2> IDC-cables](#12-idc-cables)
  - [1.3> Testing it out](#13-testing-it-out)
- [2> BOM](#2-bom)
  - [2.1> Miscellaneous components](#21-miscellaneous-components)

**NB!** I don't have any of the other variants of the Apple ][ computer than the //e, so I've not been able to test the design on any other variant. I can't tell you wether they work or even fit into them.

# 1> Building the adapter
Building the adapter, as with most things that deals with electronic projects, starts with going through the [BOM](#2-bom) and ordering whatever you don't already have. Compare with the gallery pictures if you're wondering what something looks like, unfortunately ebay is not a good place to shop for well-described components - I usually just order one of each if they're cheap (it'll get used sometime, if only to irritate someone attempting to build more than one of my projects).

Next up is soldering the resistors, these are have the lowest profile of the components and move up in size from that point forward. Please use sockets though, mainly because everything that looks like ICs from ebay can and should be considered highly suspicious until verified working - you will likely want the ability to quickly change one of them out (often they are B-grade or forcibly pulled from other hardware; they may or may not working depending on your luck).

![Front of PCB](https://github.com/tebl/Apple2-Joystick-Adapter/raw/main/gallery/2021-01-21%2022.52.42.jpg)

The last component to get soldered into place are the machined pin headers that go into the area labelled A1, these go into the Game I/O socket on the Apple ][ motherboard - the regular kind will probably break your socket, so don't use those (even if they are cheap). They are soldered on the reverse side compared to the other components, to ensure that they are soldered into place at a reasonable angle, I recommend using a 16 pin machined pin socket as a template below the pins.

![Back of PCB](https://github.com/tebl/Apple2-Joystick-Adapter/raw/main/gallery/2021-01-21%2022.52.50.jpg)

The last step I usually do with my boards, is installing an M3 nylon standoff (10mm length) into the hole between the IDC connectors - this is there so that there is some strain relief for the pins that go into the socket. It just pushes against the motherboard, so don't use the brass one as that might accidentally short something.

Onto the next step, because everyone loves making cables.

## 1.2> IDC-cables
While I would have liked to just use something that could be ordered straight from AliExpress without going so far as creating a custom cable, all of the ones I've found were mostly IDC to RS232 adapters - those have a rather randomized pin layout so I chose not to use them in the design. The method I used instead was order said cables, cut off the DB9 part already on there and then just add a new male DB9 IDC connector so that pin 1 with pin 1 on both sides (red stripe).

![Cable parts](https://github.com/tebl/Apple2-Joystick-Adapter/raw/main/gallery/cable_001.jpg)
![Cable parts](https://github.com/tebl/Apple2-Joystick-Adapter/raw/main/gallery/cable_002.jpg)

The flat ribbon DB9 connector is easy to use, just push the ribbon through and align - then push down on it with something hard like the handle of a screwdriver (if you don't have a vise). Wrap the cable over, clip the strain relief over the top. The result you should end up with looks like the following, note the position of the tab in relation to the red wire on both sides.

![Cable parts](https://github.com/tebl/Apple2-Joystick-Adapter/raw/main/gallery/cable_003.jpg)

If also adding the 2x5pin straight pin IDC to the other side, then it will have a spot for the tenth wire, this is left empty as we only use nine for the DB9. The process for fixing it into place is the same as before, but there is probably no strain relief this time - so align it according to picture above

Screw the IDC-connector into the case using M3-screws, I mainly use those that come with the cables if you got them (M3x6mm hex standoff, brass or otherwise as long as the cable is firmly in place).

# 1.3> Testing it out
Testing it out is easy, just make sure that it is installed properly - align the back pins with the holes on the socket then push it gently into place. As long as it is aligned properly, you shouldn't need to use more than a little bit of force - anything more and you'll just snap off or bend the header pins. Plug your joystick into what is marked port 1, the one closest to the side of the case, via the cable you just made and mounted on the case.

At this point you can just try to load up a game and see if that works, but personally I like to test it out using some basic code first - if only to see that all the directions work as expected. There is an [article](https://devonhubner.org/check_if_the_appleii_joystick_is_working_using_applesoft_basic/) on Devon Hubners page that does this very nicely and goes into more detail, so just type in the simple version for now and run it (I've posted a copy of it below in case that page disappears).
```
10 PRINT PDL(0), PDL(1)
20 GOTO 10
```
The little piece of code should print the X-value followed by the Y-value on the first port, it should be a number between 0 and 255. When not pushing anything it should center about the mid-point of this, mine was around 140 in values and worked nicely in the games I've tested (mostly Donkey Kong). If you get something significantly different, ensure that the correct value resistors went into the correct place (a swapped 68k and 100k would give 200, as I accidentally found out).


# 2> BOM
This is the list of parts that you'd need in order to construct Apple ][ Joystick Adapter, most could quite possibly be sourced from your friendly neighbourhood electronics store - if you should happen to have one available (using a passport on the way doesn't count). I don't, so I order most of the components on ebay and similar sources - parts may be cheap, but at least you'll need extras in order to assure at least one of them works.

| Reference            | Item                                              | Count |
| -------------------- | ------------------------------------------------- | ----- |
| Adapter (PCB)        | Fabricate using Gerber files ([order](https://www.pcbway.com/project/shareproject/Apple___e_Joystick_Adapter.html))          |     1 |
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