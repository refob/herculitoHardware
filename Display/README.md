# Display

Size of the breadboard: 20x25 mm

Length of the cables: 75.0 cm

Connections:

| N | Color  | Disp | SPI   | ESP  |  TFT     | No |
|---| :---:  |------| :---: | :---:| :---:    |----|
| 1 | black  | GND  | 0v	   | GND  | GND      | -  |
| 2 | red    | VCC  | +5V   | 5V   | +5V      | -  |
| 3 | violet | SCK  | SCL   | IO22 | TFT_SCLK | 22 |
| 4 | green  | SDA  | MISO  | IO4  | TFT_MISO | 4  | 
| 5 | brown  | RES  | RESET | RES  | TFT_RST  | -1 |
| 6 | blue   | RS   | DC    | IO33 | TFT_DC   | 33 | 
| 7 | orange | CS   | CS    | IO15 | TFT_CS   | 15 | 
| 8 | -      | LEDA | 3V3   | -    | -        |    |
| - | -      | -    | -     | -    | TFT_MOSI | -1 |

![Display Schematic](/KiCad/Display.png)

Connect the cables as shown
![Display Connections](/Display/01.jpg)
Front side
![Display Connections](/Display/02.jpg)
Back side
![Display Connections](/Display/03.jpg)

