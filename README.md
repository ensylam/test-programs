# test-programs
Test Programs to verify the hardware functionality

## Upload program to stm32 boards via UART1
1. DO NOT plug the USB2TTL module to computer until the wiring is PROPERLY set up.
2. Connect your stm32 board to a USB2TTL module. Make sure to use the "3.3V" line on your USB2TTL module. This "3.3V" line shall be connecting to the "+" terminal of the UART1 port.
<img src="http://www.makerfabs.com/image/cache/makerfabs/USB-%20UART%20Convertor-%20CP2102/USB-%20UART%20Convertor-%20CP2102-1000x750.JPG" height="300" >
3. Set stm32 board to "bootloader" mode by positioning the black jumper cap as shown. (bb) black cap, (yy) yellow cap, (x) unused pin.

| bootloader mode: | xbb<br/>yyx | | normal mode: | bbx<br/>yyx |
|---|---|---|---|---|

4. Plug the USB2TTL module to computer. The power indicator on the stm32 board shall light. If not, resolder your board.
5. Check the comport number assigned to your USB2TTL with "Device Manager". Use it to upload test program.
6. Upload the test program using "stm32flash" in "command prompt". Your COM port may vary.

|stm32flash -b 115200 -w joypad.hex -v -g 0x0 COM6|
|---|

# joypad.hex
1. Data in text format are sent to PC via UART1 with baud rate 115200.
2. Data in binary format are sent to wifi module (HC06) with baud rate 115200.

# blue.hex
1. Data in text format are sent to PC via UART3 with baud rate 115200.
2. Binary data are received from wifi module (HC05) with baud rate 115200.
3. Whatever read by the path finder is displayed at the 8 pieces of red LED.
4. Hit button to change motor state:

|motor state|
|:---|
|OFF|
|FAST FORWARD for 1 second (both motor with same PWM)|
|SLOW FORWARD|
|ROTATE LEFT|
|SLOW backward|
|ROTATE RIGHT|
