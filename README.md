# ESP32-CAM Text Recognition (Tesseract.js)

This script allows ESP32-CAM to perform text recognition using Tesseract.js. It provides custom command formats for controlling the ESP32-CAM remotely.

## Main Pages
- [API Page](http://APIP)
- [STA Page](http://STAIP)

## Custom Command Format:
- API Page: `http://APIP/control?cmd=P1;P2;P3;P4;P5;P6;P7;P8;P9`
- STA Page: `http://STAIP/control?cmd=P1;P2;P3;P4;P5;P6;P7;P8;P9`

## Default AP IP: 192.168.4.1
- IP: `http://192.168.xxx.xxx?ip`
- MAC: `http://192.168.xxx.xxx?mac`
- Restart: `http://192.168.xxx.xxx?restart`
- Digital Write: `http://192.168.xxx.xxx?digitalwrite=pin;value`
- Analog Write: `http://192.168.xxx.xxx?analogwrite=pin;value`
- Flash: `http://192.168.xxx.xxx?flash=value` (value: 0~255 for flash intensity)
- Get Still Image: `http://192.168.xxx.xxx?getstill`
- Frame Size: `http://192.168.xxx.xxx?framesize=size` (size: UXGA|SXGA|XGA|SVGA|VGA|CIF|QVGA|HQVGA|QQVGA)
- Quality: `http://192.168.xxx.xxx?quality=value` (value: 10 to 63)
- Brightness: `http://192.168.xxx.xxx?brightness=value` (value: -2 to 2)
- Contrast: `http://192.168.xxx.xxx?contrast=value` (value: -2 to 2)

## Finding Client IP:
- Search IP: `http://192.168.4.1/?ip`
- Network Reset: `http://192.168.4.1/?resetwifi=ssid;password`

## Installation
1. Set the WiFi SSID and password:
   ```cpp
   const char* ssid = "your_ssid";
   const char* password = "your_password";
   ```
2. Configure the AP SSID and password:
   ```cpp
   const char* apssid = "android";
   const char* appassword = "asepoman";
   ```

## Dependencies
- [Tesseract.js](https://github.com/naptha/tesseract.js#tesseractjs)

## Hardware Configuration
- Ensure that you are using the Wrover ESP32 module or another board with active PSRAM.

## Pin Configuration
The pin configurations for the ESP32-CAM module are as follows:

```cpp
// ESP32-CAM Module Pin Configuration
#define PWDN_GPIO_NUM   32
#define RESET_GPIO_NUM  -1
#define XCLK_GPIO_NUM   0
#define SIOD_GPIO_NUM   26
#define SIOC_GPIO_NUM   27

#define Y9_GPIO_NUM     35
#define Y8_GPIO_NUM     34
#define Y7_GPIO_NUM     39
#define Y6_GPIO_NUM     36
#define Y5_GPIO_NUM     21
#define Y4_GPIO_NUM     19
#define Y3_GPIO_NUM     18
#define Y2_GPIO_NUM     5
#define VSYNC_GPIO_NUM  25
#define HREF_GPIO_NUM   23
#define PCLK_GPIO_NUM   22
```

## Usage
- Connect to the ESP32-CAM WiFi network.
- Access the provided IP addresses in your browser to control the ESP32-CAM remotely.

## Acknowledgment
- This script is powered by Tesseract.js for text recognition.

