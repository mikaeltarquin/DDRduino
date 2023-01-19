# DDRduino
Custom PCB for handling DDR control panel, keypad, card reader, and LED controls.

# Acknowledgements
[PN5180-cardio Navigation LPCD](https://github.com/CrazyRedMachine/PN5180-cardio/tree/navigation-lpcd) by CrazyRedMachine 

[LED arduino code](https://github.com/Moldypie/hid-lights-with-individually-addressable-strips-and-a-keypad) by Moldypie

# BOM
## DDRduino Components

| Component ID | Component | Description |Quantity |
| --- | --- | --- | --- |
| U1 | 703W-00/54 | AC Power Entry Module | 1 |
| U101, U201 | TBD62003APG | Transistor Array | 2 |
| U301 | Arduino ProMicro | microcontroller for cab LEDs | 1 |
| <> | Arduino Leonardo | microcontroller for controls/button LEDs/card reader/keypad | 2 |
| PS1 | IRM-60-5 PSU | power supply for cab LEDs | 1 |
| PS2 | IRM-20-12 PSU | power supply for button LEDs | 1 |
| C301-C308 | 1000 uF D10.0mm | Radial electrolytic capacitors (I used 25V) | 8 |
| R1-R4, R13-R14 | 1 MOhm 0805 | SMD resistors | 6 |
| R5-R12 | 5.11 kOhm 0805 | SMD resistors | 8 |
| R101-R105, R201-R205 | 10 kOhm 0805 | SMD resistors | 10 |
| R301-R308 | 330 Ohm 0805 | SMD resistors | 8 |
| J5-J6 | USB1035-GF-P-0-B-B	| USB-A ports | 2 |
| J1-J4 | USB4085-GF-A | USB-C ports | 4 |
| J101, J201 | 

## Keymani Components

# Arduino Setup
1. Download the [Navigation LPCD branch](https://github.com/CrazyRedMachine/PN5180-cardio/tree/navigation-lpcd) of CrazyRedMachine's PN5180-cardio code.
2. Replace the `Config.h ` with the custom `Config.h.PN5180-cardio-navigation-lpcd (1P)` or `Config.h.PN5180-cardio-navigation-lpcd (2P)` versions, depending on which player control Arduino you are flashing. 
3. Upload the sketches to the Arduino Leonardos.
4. If using the LED controller, upload the `LED_promicro_version.ino` sketch to your ProMicro.

## PN5180-cardio Config Changes:
```
#define PN5180_PIN_NSS  0
#define PN5180_PIN_BUSY 2
#define PN5180_PIN_RST  1
#define PIN_ROW1 3
#define PIN_ROW2 A0
#define PIN_ROW3 A1
#define PIN_ROW4 A2
#define PIN_COL1 A3
#define PIN_COL2 A4
#define PIN_COL3 A5
#define PIN_BUT_UP    12
#define PIN_BUT_DOWN  11
#define PIN_BUT_LEFT  10
#define PIN_BUT_RIGHT 9
#define PIN_BUT_START 13  
#define PIN_LED_UP    7
#define PIN_LED_DOWN  6
#define PIN_LED_LEFT  5
#define PIN_LED_RIGHT 4
#define PIN_LED_START 8
```
In additon, player 2 changes:
```
#define CARDIO_ID 2
#define CUSTOM_VIDPID 2
```

## LED code changes:
```
#define LED_PIN_1     10
#define LED_PIN_2     16
#define LED_PIN_3     14
#define LED_PIN_4     15
#define LED_PIN_5     18
#define LED_PIN_6     19
#define LED_PIN_7     20
#define LED_PIN_8     21
#define NUM_STRIPS 8
```
