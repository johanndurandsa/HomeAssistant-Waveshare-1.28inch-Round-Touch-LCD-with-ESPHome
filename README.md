# HomeAssistant-Waveshare-1.28inch-Round-Touch-LCD-with-ESPHome
# HomeAssistant-Round-Touch-LCD

A sophisticated, touch-driven ESPHome interface for the Waveshare 1.28" Round LCD (ESP32-S3). This project transforms a compact display into a functional Home Assistant "Satellite" controller with multiple UI modes and an animated screensaver.

## ✨ Features
* **Analog Watch Face:** Dynamic background that changes from day (blue) to night (navy).
* **Digital Dashboard:** Real-time metrics with a bold 4px circular progress ring.
* **4-Way Control Grid:** Toggle four different devices (Lights, Fans, Kitchen) from a single screen.
* **Single-Target Mode:** Large, touch-friendly button for primary lighting control.
* **Animated Screensaver:** "Living Eyes" animation triggers after 60s of inactivity to prevent screen burn-in.

## 🛠 Hardware
* **Device:** [Waveshare ESP32-S3-Touch-LCD-1.28](https://www.waveshare.com/wiki/ESP32-S3-Touch-LCD-1.28)
* **Display Driver:** GC9A01A (240x240 Round IPS)
* **Touch Controller:** CST816S
* **MCU:** ESP32-S3

## 📂 File Structure
To compile successfully, organize your ESPHome folder as follows:
```text
/esphome/
├── fonts/
│   ├── OCRAEXT.ttf
│   ├── GoogleSansMedium.ttf
│   └── materialdesignicons-webfont.ttf
├── images/
│   └── ha-logo.png
└── esp32-s3-touch.yaml

