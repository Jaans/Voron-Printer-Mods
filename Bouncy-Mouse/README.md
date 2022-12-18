# Bouncy Mouse PCB for Voron skirt buttons
An evolution of the physical skirt button, by adding PCB to simplify wiring, soldering and physical mounting. 

![2x Bouncy Mouse PCB installed](Images/Installed_350mm_Skirt.jpg)  

## Credits and Attribution
This idea is not original or even novel, with most ideas taken from Voron user `meteyou`'s [gcode_buttons](https://github.com/VoronDesign/VoronUsers/blob/master/legacy_printers/printer_mods/README.md) and adapted to fit my needs after trial and error experiences.

Thanks to `meteyou` and everyone else who had some incarnation of skirt buttons for the Voron. Thanks to `MakerBogans` Australia 3D printer community for being friendly and supportive human beings.

<br/>

# What are skirt buttons / G-Code buttons?
The idea is about having the convenience of direct interaction with physical buttons that perform a desired action upon pressing / releasing them. For example, pressing button `X` should instruct the print to turn on/off the internal LED light. (Insert your imagination here - mine sucks.)

The idea is not novel in any way and `Bouncy Mouse` is intended to help you build your own "custom" keyboard that can be installed in your Voron skirt, and then to connect that to your Raspberry PI / other GPIO interface and have it execute G-Code or macros.

Some users even replace / remove their display in favour of this.

Here's the `Bouncy Mouse` PCB (v1 is pictured):
![Bouncy Mouse PCB v1](Images/BouncyMousePCBv1.jpg)

Holds up to three CherryMX key switches (LED optional)

## Some known uses for G-Code buttons
- Pause / Resume an active print.
- Turn on/off/push-to-peek chamber LED lights.
- Turn on/off fans.
- Multi-material control (like ejecting filament in ERCF) 
- Start your Pre-heat / Warm-up routine
- Graceful shutdown of Printer Software (e.g. Klipper / Raspberry PI Operating System)
- Take a photo from printer CAM
- Home your printer

<br/>

## Do I need Bouncy Mouse
No, you don't. You can use `meteyou`'s MOD and wire things directly - nothing wrong with it.

I created this because I found the soldering of wires to the switches and LEDs hard and fragile (I solder poorly - it's a hobby for me). Found the PCB held it all together much more firmly and regidly.

<br/>


## Bill of Materials (BOM)
Work in progress with regard to skirts that are not 350mm.

### PCB Options
* `3`-Key PCB - Suitable for 350mm skirt / possibly even for 300mm skirt with PCB extending beyond behind the skirt)
* `2`-Key PCB - Suitable for 300mm skirt
* `1`-Key PCB - Suitable for 250mm skirt / small or custom usages

<br/>

### For each PCB, where `N` is the number of keys:
* `N`x CherryMX switches

* `N`x Printed part set
    * 1x Hexagon Key Cap

    * 1x Hexagon Key Shell

    * 1x Hexagon Shell Retention Clip

* `N`+1 PIN JST XH through the hole / PCB mount receptacle

* `N`+1 PIN JST XH crimp connector housing

* `N`+1 PIN JST XH crimp connector female pin

* AWG 28 wiring long enough to reach connection points (suggest making this to size at point of installation)

<br/>

### Optional LEDs
The LED key backlight is optional and mine with 3 LEDs per PCB, uses 12v from Octopus. A different resistor size is needed with 24v.
5v will be too low for 3 LEDs.

* 2 PIN JST XH through the hole / PCB mount receptacle

* 2 PIN JST XH crimp connector housing

* 2 PIN JST XH crimp connector female pin

* R1 - Resistor (based on 12v supply)

    * For PCB with 3 LEDs populated, each with forward voltage of 1.6v - 1.8v, use 430-470 Ohm resistor (lower for brigther but shorter life)

    * For PCB with 2 LEDs : (TBA)

    * For PCB with 1 LED : (TBA)

<br/>


## How to build
I see it as 4 main stages. 
Refer to each of the following pages for more detailed information:
1. [Print parts](./Stage1.md)

    Button shell, hexagon holder, key cap with icon.
    
    Click [here](./Stage1.md) to view page about this section.

    <br/>

2. [Physical build](./Stage2.md)
    
    Assemble PCB, Button, LED, Wires, Crimps, Solder, etc.
    
    Click [here](./Stage1.md) to view page about this section.

    <br/>

3. [GPIO PIN setup](./Stage3.md)

    I use a Raspberry PI 4B and configure pins as input with pull-up resistor enabled.

    Click [here](./Stage1.md) to view page about this section.

    <br/>

4. [Klipper setup](./Stage4.md)

    What to do when GPIO pin has been triggered.

    Click [here](./Stage1.md) to view page about this section.


<br/>


## Disclaimer
The advice and suggestions here are in good faith, and offer no warranty accepts no liability by any actions taken by you, in part or in full, from content in this repository.

If you wire or solder incorrectly, use the wrong polarity or voltage, or different resistor sizes then you can damage not only these components but also the connected devices like your MCU controller or GPIO device like Raspberry PI. Don't take on this project if you are not comfortable with holding yourself responsible. 

*Plain English: You acknowledge you are responsible for your actions and don't hold me liable for anything whatsoever.*