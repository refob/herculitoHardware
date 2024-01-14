# Display

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

### BOM

* 1x [1.77 inch TFT LCD screen 128*160](https://www.aliexpress.com/item/32812455774.html)
* 1x [Breadboard: 20 x 25 mm](https://www.aliexpress.com/item/1005004818919331.html)
* 1x [Mini Push Button 12x12x8mm](https://www.aliexpress.com/item/1005005582412010.html)
* 1x [HT7333[(https://www.aliexpress.com/item/1005005945684499.html)

![Display Schematic](/KiCad/Display/Display.png)

Connect the cables as shown
![Display Connections](/Display/01.jpg)
Front side
![Display Connections](/Display/02.jpg)
Back side
![Display Connections](/Display/03.jpg)

