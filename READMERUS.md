# ThermalCamera
## [README.md on english](./README.md)
## Что это?

Это форк репозитория с кодом для совместной работы ESP32-Cam и MLX90640. Он создаёт Wi-Fi сеть "ThermalCamera" с паролем "zernovtech".

Форк упрощает прошивку микроконтроллера с помощью [flash_download_tool](./flash_download_tool_3.9.6.exe) и скомпилированных .bin файлов.

## Как?

Для прошивки необходимо:

1. Подключить ESP32-Cam к USB-TTL программатору и ввести его в режим прошивки (IO0 замкнуть на GND)
2. Установить на компьютер [драйвер CH340](./CH340.EXE)
3. Запустить [flash_download_tool](./flash_download_tool_3.9.6.exe) выбрать ESP32 и Develop, нажать "ОК"
4. В первой строке указать [Esp32ThermalCam.bootloader.bin](./Esp32ThermalCam.bootloader.bin), адрес 0x1000
5. Во второй строке указать [Esp32ThermalCam.partitions.bin](./Esp32ThermalCam.partitions.bin), адрес 0x8000
6. Во второй строке указать [Esp32ThermalCam.bin](./Esp32ThermalCam.bin), адрес 0x10000
7. Выберать COM порт программатора
8. Нажать "START"

После прошивки контроллера можно подключать MLX90640:

1. Соединить SDA MLX с IO12 ESP32
2. SCL MLX с IO13 ESP32
3. VCC MLX с 3v3 ESP32
4. G MLX с GND ESP32

Подать питание на ESP32 и подключиться к Wi-Fi сети "ThermalCamera" с паролем "zernovtech". Веб-сервер тепловизора находится по адресу 192.168.4.1.

## Congratulations!
