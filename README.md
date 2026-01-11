# ESP32-S3 Touch LCD Dashboard for Home Assistant


<img src="https://github.com/user-attachments/assets/2d476706-6556-40df-926a-cb86238b541b" width="400">


A **fully-featured round touchscreen dashboard** built with **ESPHome + Home Assistant**, designed specifically for the
**Waveshare ESP32-S3 Touch LCD 1.28" (GC9A01)**.

This project turns the display into:

* 🕒 Analog & digital clocks
* 🌡 Indoor / outdoor temperature dashboard
* 💡 Interactive light & fan control
* 🟢 4-way touch control grid
* 😴 Animated screensaver with automatic dimming

Everything runs **locally**, no cloud required.

---

## ✨ Features

* ✅ Native **ESPHome** integration with Home Assistant
* 🖥 240×240 **round GC9A01 IPS display**
* 👆 Capacitive **CST816 touch support**
* ⏱ Home Assistant **time synchronization**
* 💡 Touch-controlled Home Assistant switches & lights
* 🌈 Smooth UI animations & custom fonts
* 😴 Smart **screensaver with brightness dimming**
* 🔄 OTA updates enabled

---

## 🧰 Hardware Used

![Image](https://www.waveshare.com/img/devkit/ESP32-S3-Touch-LCD-1.28-B/ESP32-S3-Touch-LCD-1.28-B-details-inter.jpg)

| Component      | Description                       |
| -------------- | --------------------------------- |
| **Board**      | Waveshare ESP32-S3 Touch LCD 1.28 |
| **MCU**        | ESP32-S3 (Dual-core, PSRAM)       |
| **Display**    | 1.28" Round IPS LCD               |
| **Driver**     | GC9A01A (SPI)                     |
| **Touch**      | CST816 (I²C)                      |
| **IMU**        | QMI8658 (optional)                |
| **Resolution** | 240 × 240                         |

### 🔗 Official Links

* Product Page:
  [https://www.waveshare.com/esp32-s3-touch-lcd-1.28.htm](https://www.waveshare.com/esp32-s3-touch-lcd-1.28.htm)
* Datasheet / Wiki:
  [https://www.waveshare.com/wiki/ESP32-S3-Touch-LCD-1.28](https://www.waveshare.com/wiki/ESP32-S3-Touch-LCD-1.28)

---

## 🏗 Software Stack

* **ESPHome**
* **Home Assistant**
* **Arduino Framework** (ESP32-S3)
* **SPI DMA display driver**
* **I²C touch controller**

> ℹ️ ESP-IDF also works, but Arduino is used here for compatibility and simplicity.

---

## 📦 Folder Structure

```text
.
├── esp32-s3-touch.yaml
├── images/
│   └── ha-logo.png
├── fonts/
│   ├── OCRAEXT.ttf
│   └── GoogleSansMedium.ttf
└── secrets.yaml
```

---

## 🔌 Pin Configuration (Waveshare Default)

### SPI (Display – GC9A01)

| Function  | GPIO   |
| --------- | ------ |
| SCLK      | GPIO10 |
| MOSI      | GPIO11 |
| MISO      | GPIO12 |
| CS        | GPIO9  |
| DC        | GPIO8  |
| RESET     | GPIO14 |
| Backlight | GPIO2  |

### I²C (Touch + IMU)

| Function    | GPIO   |
| ----------- | ------ |
| SDA         | GPIO6  |
| SCL         | GPIO7  |
| Touch INT   | GPIO5  |
| Touch RESET | GPIO13 |

---

## 🎨 UI Display Modes

### **Mode 0 – Analog Watch Face**

* Day/night color themes
* Ticking second hand
* Drop shadows
* Date complication
* Home Assistant logo overlay

---

### **Mode 1 – Digital Dashboard**

* Large digital clock
* Animated progress ring (seconds)
* Indoor & outdoor temperatures
* Material Design icons

---

### **Mode 2 – Single Light Control**

* Large touch-friendly circular button
* Live Home Assistant switch state
* Color-coded ON/OFF background

---

### **Mode 3 – Animated Screensaver**

* Automatic after 60 seconds of inactivity
* Wandering animated eyes 👀
* Blink animation
* Backlight dimmed to 20%
* Prevents OLED/IPS burn-in

---

### **Mode 4 – 4-Way Control Grid**

| Quadrant     | Entity      |
| ------------ | ----------- |
| Top-Left     | Corner Lamp |
| Top-Right    | Fan         |
| Bottom-Left  | Main Light  |
| Bottom-Right | Kitchen     |

---

## 👆 Touch Logic Overview

* Tap anywhere → cycles display modes
* Touch center button → toggles lamp
* Touch grid quadrant → toggles entity
* First touch exits screensaver
* Touch resets idle timer

Touch detection uses:

* **Circular hit testing** (Pythagorean distance)
* **Quadrant mapping**
* **State-aware UI refresh**

---

## 🧠 Screensaver Logic

```text
• Checks inactivity every 1 second
• After 60 seconds:
  → Saves current screen
  → Switches to Mode 3
  → Dims backlight
• On touch:
  → Restores brightness
  → Returns to previous mode
```

---

## 🔗 Home Assistant Integration

Entities are linked directly via the ESPHome API:

### Sensors

* Indoor temperature
* Outdoor temperature
* Power consumption

### Switches / Lights

* Corner lamp
* Fan
* Main light
* Kitchen switch

Everything updates **live** on the display.

---

## 🚀 Installation Steps

1. Flash ESPHome to the board
2. Copy `esp32-s3-touch.yaml`
3. Add Wi-Fi credentials to `secrets.yaml`
4. Upload fonts & images
5. Compile & upload
6. Add device to Home Assistant
7. Enjoy 😎

---

## ⚠️ Notes & Tips

* Resize images to **≤200×200** to save RAM
* Use PSRAM (enabled by default)
* GC9A01 **requires color inversion**
* OTA enabled – no USB needed after first flash

---

## 🧩 Customization Ideas

* Add weather forecast
* Add music player controls
* Add brightness auto-adjust (LDR)
* Add swipe gestures
* Add vibration motor feedback

---

## ❤️ Credits & Inspiration

* Waveshare hardware & documentation
* ESPHome community
* Home Assistant project

---

## 📜 License

MIT License – free to use, modify, and share.



