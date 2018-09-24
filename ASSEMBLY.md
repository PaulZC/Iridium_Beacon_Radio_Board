# Iridium 9603N Beacon Radio Board

## Circuit Board Assembly and Configuration

![Assembly_6.JPG](https://github.com/PaulZC/Iridium_Beacon_Radio_Board/blob/master/img/Assembly_6.JPG)

A radio board for the [Iridium 9603N Beacon](https://github.com/PaulZC/Iridium_9603_Beacon). Equipped with an
[LPRS eRIC4 or eRIC9 integrated radio module](http://www.lprs.co.uk/products/easyradio-ism-modules/eric-soc-rf-modules.html),
this board allows remote control of radio-enabled devices near the Iridium Beacon. E.g. a
[radio-enabled cut-down device](https://github.com/PaulZC/Pyrotechnic_Balloon_Cut-Down).

See [Iridium_Beacon_Radio_Board_V1.pdf](https://github.com/PaulZC/Iridium_Beacon_Radio_Board/blob/master/Iridium_Beacon_Radio_Board_V1.pdf) for the schematic,
layout and Bill Of Materials.

The [Eagle](https://github.com/PaulZC/Iridium_Beacon_Radio_Board/tree/master/Eagle) directory contains the schematic and pcb design files.

Here are the assembly instructions for V1 of the PCB:

### eRIC

The radio board uses the eRIC4 or eRIC9 [easyRadio Integrated Controller](http://www.lprs.co.uk/products/easyradio-ism-modules/eric-soc-rf-modules.html).

Either an eRIC4 or an eRIC9 can be installed. The eRIC4 operates at 402-470 MHz for Europe, APAC and China. The eRIC9 operates at 804-940 MHz for Europe,
North & South America, India and China. Solder the _FREQ_ split pad to select the eRIC9 915 MHz band.

The eRIC will come pre-programmed with easyRadio V1.5.5 and is ready to use.

You can find the datasheet for the eRIC on the LPRS website:
- http://www.lprs.co.uk/products/easyradio-ism-modules/eric-soc-rf-modules.html
- http://www.lprs.co.uk/assets/files/eRIC4_9_Datasheet_1.34.pdf

### Blank PCB

Start by having the blank PCBs manufactured. If you are based in the UK or Europe, I can recommend
[Multi-CB](https://www.multi-circuit-boards.eu/en/index.html) who can manufacture PCBs in 1-8 working days and
can process the Eagle .brd file direct - there's no need to generate Gerber files.

My recommended options are:
- Layers: 2 layers
- Format: single pieces
- Surface finish: chemical gold (ENIG)
- Material: FR4, 1.55mm
- Cu layers: 35um
- Solder stop: both sides, green
- Marking print: top side, white

![Assembly_1.JPG](https://github.com/PaulZC/Iridium_Beacon_Radio_Board/blob/master/img/Assembly_1.JPG)

### Add the surface mount components

Solder the surface mount components onto the board by hand. There are many good surface mount soldering guides available on the web, including
[this one](https://www.youtube.com/watch?v=QzoPxvIM2qE).

Use a cotton swab dipped in Isopropyl Alcohol (IPA / Propanol / rubbing alcohol) to remove any flux residue.

All being well, your PCB should look like this:

![Assembly_3.JPG](https://github.com/PaulZC/Iridium_Beacon_Radio_Board/blob/master/img/Assembly_3.JPG)

### Add the non-surface mount components

The non-surface mount components (SMA connector and header pins) can now be soldered into place.

![Assembly_4.JPG](https://github.com/PaulZC/Iridium_Beacon_Radio_Board/blob/master/img/Assembly_4.JPG)

![Assembly_7.JPG](https://github.com/PaulZC/Iridium_Beacon_Radio_Board/blob/master/img/Assembly_7.JPG)

### Lacquer the PCB

I do recommend giving the PCB a coat of lacquer, especially if you are intending to use it on a balloon flight.
Cover all of the surface mount components with [Acrylic Protective Lacquer (conformal coating)](https://uk.rs-online.com/web/p/conformal-coatings/3217324/).

### LED

LED1 will flash once per second when the eRIC is powered up and not in power-save mode.

### I/O pins

The eRIC TxD, RxD, CTS and RTS pins are connected to 0.1" pads on the edge of the circuit board. The order of these pads matches the order of the pins of an FTDI
TTL-232R-3V3 USB to TTL serial cable. The eRIC can be reprogrammed via the FTDI cable if required.

Two extra pads are connected to the eRIC bootloader pins (Pin11 and Pin12). The eRIC will enter bootloader mode if these pads are shorted together on reset
or power-up. LED1 will be lit continuously when the eRIC is in bootloader mode.

### Antennas

Recommended antenna for the eRIC4 is:
- LPRS ANT-SR433 (Farnell part 2096221)

Recommended antenna for the eRIC9 is:
- LPRS ANT-SR900 (Farnell part 2096219)

http://www.lprs.co.uk/products/antennas-cables-connectors/stubby-antennas.html

The horizontal antenna orientation is important if the Iridium Beacon is located below the cut-down device on the balloon cord.

### Iridium Beacon Connections

The radio board is designed to sit on top of the Iridium 9603N module and connect to the IO pads on the Iridium Beacon board. You will need to solder three sockets
onto the Iridium Beacon board for the radio board to plug into:

![Assembly_5.JPG](https://github.com/PaulZC/Iridium_Beacon_Radio_Board/blob/master/img/Assembly_5.JPG)

- The 3+3 Way sockets are Harwin M20-7830346 (Farnell part 7991983)
- The 2+2 Way socket is Harwin M20-7830246 (Farnell part 7991975)

![Assembly_8.JPG](https://github.com/PaulZC/Iridium_Beacon_Radio_Board/blob/master/img/Assembly_8.JPG)

### The Small Print

This project is distributed under a Creative Commons Attribution + Share-alike (BY-SA) licence.
Please refer to section 5 of the licence for the "Disclaimer of Warranties and Limitation of Liability".

Enjoy!

**_Paul_**