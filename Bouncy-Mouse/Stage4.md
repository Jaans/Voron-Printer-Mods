# Stage 4 - Klipper setup

Last but not the least we need to tell Klipper about the GPIO pins and create G-Code buttons for them.

I chose to separate my various configuration sections out into separate `.cfg` files like `buttons.cfg` in this case. You do you - that's beyond the scope of this guide.

Here's the content of my `buttons.cfg` file. Adapt to your needs.:

```
# Push Button RPI Pins
#########################
# Configure the pins as input pins with pull up resister enabled.
# Update /boot/config.txt to configure GPIO pins at startup.
# https://www.raspberrypi.com/documentation/computers/config_txt.html#what-is-config-txt
#########################

[gcode_button Button_Z_Up]
pin: ^!rpi:gpio17
press_gcode: 
    M117 Z-UP
    _ZUP            # Custom G-Code macro
release_gcode:

[gcode_button Button_Z_Down]
pin: ^!rpi:gpio27
press_gcode: 
    M117 Z-DOWN
    _ZDOWN          # Custom G-Code macro
release_gcode:

[gcode_button Button_Pause_Resume]
pin: ^!rpi:gpio22
press_gcode: 
    M117 PAUSE-RESUME
#   TODO
release_gcode:

[gcode_button Button_Lights]
pin: ^!rpi:gpio19
press_gcode:
    M117 LIGHTS
    {% if printer['output_pin caselight'].value %}
        SET_PIN PIN=caselight VALUE=0
        status_off
    {% else %}
        SET_PIN PIN=caselight VALUE=0.4
        status_ready
    {% endif %}
release_gcode:

[gcode_button Button_Warmup]
pin: ^!rpi:gpio26
press_gcode: 
    M117 HEAT
    WARM_UP         # Custom G-Code macro
release_gcode:

[gcode_button Button_Shutdown]
pin: ^!rpi:gpio21
press_gcode: 
    M117 POWER
#   TODO
release_gcode:
```


<br/>

### Back to HOME : Click [here](./README.md)
