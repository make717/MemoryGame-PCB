# MemoryGame-PCB
KiCad PCB files for custom [Make717 memory game](https://github.com/make717gh/MemoryGame) soldering badge. This badge was designed and built by members of [Make717](https://www.make717.org) for a soldering event at the [Lancaster Science Factory](https://www.lancastersciencefactory.org/) on April 27, 2019.

This badge is using the [SAMD21G](https://cdn-shop.adafruit.com/product-files/2772/atmel-42181-sam-d21_datasheet.pdf) 32-bit microcontroller running [CircuitPython](https://github.com/make717gh/circuitpython). Thank you to [Adafruit](https://www.adafruit.com). 

![Make717badge](https://github.com/make717gh/MemoryGame-PCB/blob/master/front_badge.png)

# Power
The badge is powered by either USB or two AAA batteries (*SW1* "Power Switch" can be either in *USB* or *BATT*). If using batteries, ensure they are 1.5 volts and fully charged. The badge might not power up with recharable batteries which are often rated at 1.2 volts. The USB connection goes through a voltage regulator to supply 3.3 volts to the microcontroller and other components on the board.

# Ready to Build
If you are joining us at Make717, or have all the component to build a badge, you can follow the [assembling instructions](https://github.com/make717gh/MemoryGame-PCB/blob/master/ASSEMBLING.md) which include tips on what to check if the badge is not working.

# Flashing and Firmware
You can update the firmware on the badge over USB by droping an updated UF2 image when in bootloader mode. To enter this mode, double tap the *RST1* to *GND1* while powered over USB. The drive should reappear as *FEATHER_BOOT* when it has entered this mode. 

It is also possible to directly program the SAMD21G18A using Serial Wire Debug (SWD). We recommend a [J-LINK](https://www.adafruit.com/product/3571) programmer or similar, connecting to *SWDIO1* (data), *SWCLK1* (clock), *GND1* (ground), and *3V3* (power). You will also need to power the board with 3.3 volts which can be done via the USB connection while programming or the *5V* pin near the USB port.
