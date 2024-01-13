# CNC Shield V3

 The Wemos D1 R32 board controls the CNC Shield V3.0. This works fine,
 if A4988 drivers are used on the shield.

<pre>
rst:0x1 (POWERON_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)<CR>
configsip: 0, SPIWP:0xee<CR>
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00<CR>
mode:DIO, clock div:1<CR>
load:0x3fff0018,len:4<CR>
load:0x3fff001c,len:1216<CR>
ho 0 tail 12 room 4<CR>
load:0x40078000,len:10944<CR>
load:0x40080400,len:6388<CR>
entry 0x400806b4<CR>
</pre>

 Once the A4988 drivers are exchanged with TMC2209 boards I observed The
 following error:

<pre>
rst:0x10 (RTCWDT_RTC_RESET),boot:0x33 (SPI_FAST_FLASH_BOOT)<CR>
invalid header: 0xffffffff<CR>
invalid header: 0xffffffff<CR>
invalid header: 0xffffffff<CR>
invalid header: 0xffffffff<CR>
invalid header: 0xffffffff<CR>
invalid header: 0xffffffff<CR>
invalid header: 0xffffffff<CR>
ets Jul 29 2019 12:21:46<CR>
<CR>
</pre>

 This seems to be caused by a higher load that the TMC2209 drivers put on the 
 GPIO12 port, which status is critcal during the ESP32 boot.
 
 The TMC2209 drivers keep cool during operation and run the steppers in a very
 silent mode. Therefore I decided to implement a hardware fix:
 
 *Disconnect GPIO12 and the connect ENABLE to the GPIO00 pin that is not used.*
 
 Please also note that the R1 resistor has to be removed from the board, because
 it connected to +5V level that is too high for the ESP32 which allows a maximum
 of 3V3 for its ports.
 
![Hardware Modifications](/CNC%20Shield%20V3/CNC%20Shield%20Modifications.png)

The pin above "ENABLE" has to be removed
![Hardware Modifications](/CNC%20Shield%20V3/enable%20a.jpg)
View, after the pin was removed
![Hardware Modifications](/CNC%20Shield%20V3/enable%20b.jpg)
![Hardware Modifications](/CNC%20Shield%20V3/enable%20c.jpg)
Solder the removed pin to a cable and the solder dot on the pcb board
![Hardware Modifications](/CNC%20Shield%20V3/enable%20d.jpg)
![Hardware Modifications](/CNC%20Shield%20V3/enable%20e.jpg)
![Hardware Modifications](/CNC%20Shield%20V3/enable%20f.jpg)
Connect the pin to "IO00" on the Wemos D1 R32 board
![Hardware Modifications](/CNC%20Shield%20V3/enable%20g.jpg)

Locate resistor R1 on the CNC shield
![Hardware Modifications](/CNC%20Shield%20V3/remove%20R1%20a.jpg)
Removed resistor R1
![Hardware Modifications](/CNC%20Shield%20V3/remove%20R1%20b.jpg)
Add a new 10k resistor on the other side of the pcb between the shown solder dots
![Hardware Modifications](/CNC%20Shield%20V3/remove%20R1%20c.jpg)



