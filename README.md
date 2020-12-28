# Sony KSS laser pickup driver

This board is used to drive the KSS-family pickups (KSS-16x, KSS-220 etc.) with a circuit very similar to one used by various kinds of mobile and home players, which all used the CXA1081 IC. Personally, I've used this circuit to measure/adjust the laser diode current and to measure the light emission (using a Leader LPM-8000 meter). A separate circuit like this one makes it much easier to handle the pickup compared to working within cramped Discman or car audio players.

The circuit is pretty much a copy of the Alpine 7909 design, but very closely resembles Discmans (such as D-33) from that era. The only difference I've noticed is the resistor for the `VR` line - it's 0-ohm in 7909, but 91-ohm in some of the Discman implementations.

The circuit is tested and worked fine on several Sony pickups without burning any of them :) Still, you use it at your own risk.

![3D render](/pictures/IMG_1101_thumb.JPG)

## Potentially compatible devices/pickups

### Sony Discmans
- KSS-220A (D-11, D-22, D-33, D-99, D-800K, D-802K)
- KSS-162A (D-4, D-12, D-20, D-T20, D-30, D-34, D-40, D-55T, D-90, D-100)

### Car audio
- Alpine 7909 (KSS-163A)
- Sony CDX-5080 CDX-7580 CDX-R77 CDX-R79 (KSS-168A)
- Blaupunkt CD42 family
- Blaupunkt New York SCD08 (KSS-164A), BMW Bavaria ELECTRONIC CD (II)

## Connections

### Power supply
Connect to `J1` a stable power source within the range acceptable by `78L05` on the board.

### Laser pickup
You can use either of the 3 connections:
- 1mm pitch FFC connector,
- 1.25mm pitch FFC conector,
- solder pads (`PD` - monitor diode, `LD` - laser diode, `GND` - ground); please mind the ESD measures.

The `LD_SHORT` jumper shorts out the laser diode. Remove the jumper once your pickup is fully connected.

### Switching on the laser diode

Use the `SW1` switch to turn on the diode. After turning it on, do not look directly into it lens.

### Measuring laser diode current

You can measure the laser current on the `J2`/`J3` banana jacks as a voltage across a 10-ohm resistor.

## CXA1081 symbol/footprint

You can find it in [my library](https://github.com/dymczykm/marcin_kicad_library).

## Component list

I've sourced CXA1081 SDIP from ebay (I took a used one to be sure it's not a counterfeit).

Most other components are listed in the [CSV file](digikey_bom.csv). Please note that it does not contain components I had already at hand, so double check it against the schematic.
