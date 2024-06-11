# rst-esp32
## ESP32-S3 (Generic) Reset + Reflash Instructions

If your ESP32-S3 is spitting out garbage like so:

```
I (37388) example: log -> UART
example: print -> stdout
example: print -> stderr
```

### This MAY help. 

Hold down the BOOT button.
Connect to the USB port (not the COM port). 
Visit => https://adafruit.github.io/Adafruit_WebSerial_ESPTool/

**Do not disconnect the board during any step of this proccess.**

Set Baud to 115200, then click connect (connect to the COM port of the ESP32, ensure it is the **correct** one before going further.)
![image](https://github.com/Gamer23car/rst-esp32/assets/93737164/00145e77-0442-452f-bd68-d1ff35269b70)

The console will ask you to **hard reset** the device, which can be accomplished by 

Holding BOOT while you short pins GND & RST with a jumper cable **OR** 

Proceed while holding BOOT to then press and release the RST button (release BOOT after quickpressing RST). 

![image (69)](https://github.com/Gamer23car/rst-esp32/assets/93737164/2554d5e4-6806-4ba7-9484-d3afa37c6bc6)


From there, you will have to re-connect the device, which will now show up as a Debug device, this is normal.

![image](https://github.com/Gamer23car/rst-esp32/assets/93737164/fcfac53a-0cd1-4a34-806d-11e4d70daee3)


### There will now be an interface that should pop-up with additional information as to Erasing and Re-Programming the flash. 
#### You can use any .bin designed for your exact ESP32-S3 board (keeping in mind the flash of the device) to Re-Program it. 

![image (70)](https://github.com/Gamer23car/rst-esp32/assets/93737164/993c4aca-604b-43c1-88b4-ce18cbb6172a)

**Example Bin(s):**

MicroPython ESP-32 S3 => https://micropython.org/download/ESP32_GENERIC_S3/

CircuitPython ESP-32 S3 => https://circuitpython.org/downloads?q=esp32+s3

### After it succeeds, you may RST the device once more and use PuTTY OR your designated IDE to verify the integrity of the newly flashed .bin

**You may disconnect the board after this point**

Congrats, your ESP32-S3 should be re-flashed. 

I made this as an instructional guide, mainly for me.
