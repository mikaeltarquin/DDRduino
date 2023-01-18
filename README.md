# DDRduino
Custom PCB for handling DDR control panel, keypad, card reader, and LED controls.

# Acknowledgements
[PN5180-cardio Navigation LPCD](https://github.com/CrazyRedMachine/PN5180-cardio/tree/navigation-lpcd) by CrazyRedMachine 

[LED arduino code](https://github.com/Moldypie/hid-lights-with-individually-addressable-strips-and-a-keypad) by Moldypie

# Arduino Setup
1. Download the [Navigation LPCD branch](https://github.com/CrazyRedMachine/PN5180-cardio/tree/navigation-lpcd) of CrazyRedMachine's PN5180-cardio code.
2. Replace the `Config.h ` with the custom `Config.h.PN5180-cardio-navigation-lpcd (1P)` or `Config.h.PN5180-cardio-navigation-lpcd (2P)` versions, depending on which player control Arduino you are flashing. 
3. Upload the sketches to the Arduino Leonardos.
4. If using the LED controller, upload the `LED_promicro_version.ino` sketch to your ProMicro.
