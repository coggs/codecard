## Code Card Arduino
![](images/arduino.png)

The Code Card runs on an [ESP8266](https://en.wikipedia.org/wiki/ESP8266) Wi-fi microcontroller.  

The ESP8266 is a low-cost Wi-Fi microchip with full TCP/IP stack and microcontroller capability, produced by manufacturer Espressif Systems.  
The processor is an L106 32-bit RISC microprocessor core running at 80 MHz, with 4 MiB external QSPI flash. The ESP8266 supports IEEE 802.11 b/g/n Wi-Fi, WEP or WPA/WPA2 authentication, and also supports open networks.  

### Software
In order to customise the Code Card firmware, you need to download the [Arduino IDE](https://www.arduino.cc/en/Main/Software) and configure it to use the Arduino core for ESP8266 WiFi chip.  
The Arduino core for ESP8266 is a C++ based firmware. With this core, the ESP8266 CPU and its Wi-Fi components can be programmed like any other Arduino device using the Arduino IDE.  

## Instructions
The following instruction describes the setup and configuration of the Arduino IDE, and the process to upload firmware to your Code Card using the Arduino IDE:

*Note:*
- *Versions per component are detailled below, if you chose to deviate from the recommended - your mileage may vary!*
- *Ensure your Code Card can connect to Wi-Fi before completing step #12*

1. Install the Arduino IDE version (Latest): https://www.arduino.cc/en/Main/Software
2. Install the serial driver for the ESP-12F Wi-Fi chip: https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers
3. In the Arduino IDE, go to Preferences and set the “Additional Board Managers URLs to http://arduino.esp8266.com/stable/package_esp8266com_index.json
4. Install esp8266 support: Tools | Board | Board Manager
   - esp8266 by ESP8266 Community 2.4.2
5. Install the required modules: Sketch | Include Libraries | Manage Libraries
   - ArduinoJson by Benoit Blanchon version 6.19.4
   - GxEPD2 by Jean-Marc Zingg version 1.4.9
   - Adafruit GFX Library by Adafruit 1.11.3
6. Under Tools set the following settings:
   - Board: “Generic ESP8266 Module”
   - Upload Speed “115200”
   - CPU Frequency: “80 MHz”
   - Crystal Frequency: “26 MHz”
   - Flash Size: “4M (3M SPIFFS)”
   - Flash Mode: “DIO”
   - Flash Frequency: “40MHz”
   - Reset Method: “nodemcu”
   - Debug port: “Disabled”
   - Debug Level: “None”
   - IwIP Variant: “v2 Lower Memory”
   - VTables: “Flash”
   - Builtin Led: “2”
   - Erase Flash: “Only Sketch”
   - Port: This is the port that shows up once you turn on the CodeCard and press a button
   - Programmer: “ArduinoISP”
7. Connect the CodeCard via USB to your computer
8. Choose Serial Port and Board (ESP-12E)
9. Establish serial connection via Arduino IDE:
   - Tools | Serial Monitor
10. Turn on the Code Card
11. Press and hold button `A` until 5 seconds after the following output is displayed:
```
Shuting down...
Shuting down...
```
