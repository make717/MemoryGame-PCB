# Assembly Instructions

The following instructions is for building the badges, but leaving the buzzer and battery unattached. These two components will be soldered on by students as part of their lesson.

Parts list:
 * one SAMD21G18A 48 pin micro-controller (pre-programmed)
 * four DotStar SK9822 LEDs
 * three 10u capacitors (0805 size)
 * three 0.1u capacitors (0805 size)
 * one microUSB port
 * one MIC5504 3.3 volt regulator

Here's a rendering of the final populated badge
![Make717badge](https://github.com/make717gh/MemoryGame-PCB/blob/master/front_badge.png)

Note: We will NOT be populating U6, C2, C3, or SP1 in these instructions

# Hand Soldering instructions

Start with micro-controller (U1). If you're at Make717, use one that has already been flashed with a bootloader. This will make things easier to test and won't require soldering on an additional 4 pins.
 * Make sure to align the chip's dot with the "U1" marking on the board!

Attach the USB port (J1) to the edge of the board. Solder on the large pads on the side, then the 5 leads on the back.
  * Make sure this sits flat on the board before soldering the leads.

Solder on all 6 pads for the 4 DotStar LEDs. 
 * The tiny triangle cut out needs to point towards the "Ux" marking on the board (U3, U4, U5, and U7)

Solder on the 5 legs of the voltage regulator (U2)

There are two different sets of capacitors for the board ("10u" and "0.1u"), make sure to use the correct values which are labeled on the board. Also there are additional pads on the board that will NOT get populated. These are for expansions that can be added later.These capacitors are not polarized, so can face either direction. 

 * Start with the "10u" values which go in 3 places on the board (C1, C6, C8). Check your micro-controller pins after C8 since these are near by.

 * Then solder the "0.1u" capacitors in the 3 places on the board (C4, C5, C7)

Finally add the switch (SW1) near the USB port. This can face either direction.

# QA Testing

Now it's time to test the board. Plug in the USB port power up the system. You should see all 4 leds light up and change color.

If only a few LEDs light up.
 * Check the orenitation of the LEDs. Are the triangle cutout facing the labels on the silk-screen (U3, U4, U5, and U7)
 * Is there enough solder on each of the 6 pads from the LED?
 * Is there too much solder on any pad causeing them to bridge?
 * If this was done in the reflow oven, they may have been over baked

If there are no lights at all, here's a few things to try.
 * Press fit a buzzer to SP1, and press any triangle button a few times. Do you hear any beeping? If so, the code is running and it is most likely an issue with the LEDs.
 * Plug in the USB port to a computer. Does any new drive show up? If so, then the USB port, regulator, and micro-controller are probably fine.
 * Use a multimeter and check the "GND1" and "5V0" pins while plugged into USB power. This should read close to 5 volts. If not, check the USB port.
 * Use a multimeter and check the "GND1" and "3V3" pins while plugged into USB power. It should read close to 3.3 volts. If not, check the regulator, and capacitors (C1, C6, C7).

