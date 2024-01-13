# CNC Shield V3

 The Wemos D1 R32 board controls the CNC Shield V3.0. This works fine,
 if A4988 drivers are use on the shield.

 Once the A4988 drivers are exchanged with TMC2209 boards I observed The
 following error:

rst:0x10 (RTCWDT_RTC_RESET),boot:0x33 (SPI_FAST_FLASH_BOOT)<CR> invalid header: 0xffffffff<CR> invalid header: 0xffffffff<CR> invalid header: 0xffffffff<CR> invalid header: 0xffffffff<CR> invalid header: 0xffffffff<CR> invalid header: 0xffffffff<CR> invalid header: 0xffffffff<CR> ets Jul 29 2019 12:21:46<CR>

 If I connect gnd to gpio12 then it will boot into the flashed program. 

 GPIO_NUM_12 and GPIO_NUM_13 can be tricky to use on a ESP32 
 with those lines being used for boot and program load. I 
 recommend against using GPIO_NUM_12.

Power via USB: 75-87 mA 4.96V

Regular boot sequence
---------------------
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
ESP32 bluetooth address: 08:b6:1f:35:54:66<CR>
ROBGC - FTobler Roboter Arm GCODE Control V1.0<CR>

Boot crash
----------
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

Hardware Fix:
-------------
Disconnect GPIO12 and the connect ENABLE to GPIO00 (not yet used).



