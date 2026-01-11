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
Project Description: ESPHome Touch Satellite
This project transforms the Waveshare 1.28" Round LCD (ESP32-S3) into a high-performance, touch-driven "Satellite" node for Home Assistant. Unlike a simple sensor, this device acts as a localized control hub, featuring a custom-coded UI with smooth animations, dynamic states, and power-management features.

## 🧩 Core Functionality
The firmware is built on ESPHome using the arduino framework, optimized for the ESP32-S3's memory architecture. It features five distinct operating modes:

Dynamic Analog Face: A classic watch face that transitions its background color based on the time of day (Bright Blue for day, Deep Navy for night).

Smart Dashboard: Provides a digital clock with a 60-second "Progress Ring" and live temperature data pulled directly from your Home Assistant sensors.

Single-Target Controller: A large, high-contrast button designed for "no-look" toggling of a primary device (e.g., a Corner Lamp).

4-Way Control Grid: A segmented interface that splits the round screen into four touch-sensitive quadrants to toggle lights, fans, and kitchen appliances.

Reactive Screensaver: To prevent image retention and save power, the device enters an "Animated Eyes" mode after 60 seconds of inactivity, dimming the backlight and using procedural math to simulate "blinking" and "looking" behaviors.

## 🛠 Technical Highlights
Display Driver: High-speed SPI implementation for the GC9A01A 240x240 IPS panel.

Touch Integration: I2C communication with the CST816 controller, using custom C++ Lambdas for coordinate-based button detection.

Asset Management: Integrated custom typography (Google Sans & OCR-A) and Material Design Icons (MDI) stored in the ESP32's flash memory.

Efficiency: Uses ledc PWM for smooth backlight dimming and specialized ili9xxx rotation settings for the circular form factor.
