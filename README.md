#ThermalCamera
## [README.md на русском](./READMERUS.md)
## What is this?

This is a fork of the repository with code for collaboration between ESP32-Cam and MLX90640. It creates a Wi-Fi network "ThermalCamera" with the password "zernovtech".

The fork simplifies microcontroller firmware using [flash_download_tool](./flash_download_tool_3.9.6.exe) and compiled .bin files.

## How?

For firmware you need:

1. Connect the ESP32-Cam to the USB-TTL programmer and enter it into firmware mode (IO0 shorted to GND)
2. Install [CH340 driver](./CH340.EXE) on your computer
3. Run [flash_download_tool](./flash_download_tool_3.9.6.exe) select ESP32 and Develop, click "OK"
4. In the first line indicate [Esp32ThermalCam.bootloader.bin](./Esp32ThermalCam.bootloader.bin), address 0x1000
5. In the second line indicate [Esp32ThermalCam.partitions.bin](./Esp32ThermalCam.partitions.bin), address 0x8000
6. In the second line indicate [Esp32ThermalCam.bin](./Esp32ThermalCam.bin), address 0x10000
7. Select the COM port of the programmer
8. Press "START"

After flashing the controller, you can connect the MLX90640:

1. Connect SDA MLX to IO14 ESP32
2. SCL MLX with IO15 ESP32
3. VCC MLX with 3v3 ESP32
4. G MLX with GND ESP32

Apply power to the ESP32 and connect to the "ThermalCamera" Wi-Fi network with the password "zernovtech". The thermal imager's web server is located at 192.168.4.1.

## Congratulations!
