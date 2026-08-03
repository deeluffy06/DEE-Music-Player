# Circuit Design

**Project:** DEE Music Player

**Version:** 1.0

---

# Overview

This document describes the electrical connections between all hardware components used in the DEE Music Player.

The design is based around the ESP32-S3 and uses dedicated communication buses for each peripheral:

- SPI → TFT Display & microSD Card
- I²S → PCM5102A DAC
- I²C → MAX17048 Fuel Gauge
- GPIO → Buttons & Rotary Encoder

---

# System Connections

## ESP32-S3 ↔ TFT Display

| TFT Pin | ESP32 GPIO |
|----------|------------|
| VCC | 3.3V |
| GND | GND |
| SCK | GPIO14 |
| MOSI | GPIO12 |
| MISO | GPIO13 |
| CS | GPIO15 |
| DC | GPIO16 |
| RESET | GPIO17 |
| BL | 3.3V |

---

## ESP32-S3 ↔ microSD Card

| SD Pin | ESP32 GPIO |
|---------|------------|
| VCC | 3.3V |
| GND | GND |
| MOSI | GPIO12 |
| MISO | GPIO13 |
| SCK | GPIO14 |
| CS | GPIO18 |

---

## ESP32-S3 ↔ PCM5102A DAC

| DAC Pin | ESP32 GPIO |
|----------|------------|
| VIN | 3.3V |
| GND | GND |
| BCK | GPIO4 |
| LCK | GPIO5 |
| DIN | GPIO6 |
| SCK | GND |
| FMT | GND |
| FLT | GND |
| DMP | GND |
| XSMT | 3.3V |

---

## PCM5102A ↔ Speaker Amplifier

| DAC | Amplifier |
|-----|-----------|
| LOUT | LIN |
| ROUT | RIN |
| GND | GND |

---

## Speaker Amplifier ↔ Speaker

| Amplifier | Speaker |
|-----------|---------|
| OUT+ | Speaker + |
| OUT− | Speaker − |

---

## PCM5102A ↔ Headphone Jack

| DAC | Headphone Jack |
|-----|----------------|
| LOUT | Left |
| ROUT | Right |
| GND | Sleeve |

### Headphone Detection

| Headphone Jack | ESP32 |
|----------------|-------|
| Detect Switch | GPIO7 |

---

## ESP32-S3 ↔ MAX17048 Fuel Gauge

| MAX17048 | ESP32 |
|-----------|-------|
| VIN | Battery + |
| GND | GND |
| SDA | GPIO2 |
| SCL | GPIO3 |
| ALRT | GPIO41 |

---

## ESP32-S3 ↔ Rotary Encoder

| Encoder Pin | ESP32 GPIO |
|-------------|------------|
| CLK | GPIO8 |
| DT | GPIO9 |
| SW | GPIO10 |
| VCC | 3.3V |
| GND | GND |

---

## ESP32-S3 ↔ Buttons

| Button | GPIO |
|--------|------|
| Play / Pause | GPIO21 |
| Previous | GPIO38 |
| Next | GPIO39 |
| Home | GPIO40 |

All buttons are connected between GPIO and GND using the ESP32-S3's internal pull-up resistors.

---

# Power System

### Battery

- 3000 mAh Li-ion Battery

### Charging

- USB-C TP4056 Charging Module

### Fuel Gauge

- MAX17048

### Power Flow

```text
USB-C
   │
TP4056 Charger
   │
Battery
   │
Power Switch
   │
Buck Converter
   │
3.3V Rail
   ├── ESP32-S3
   ├── TFT Display
   ├── microSD Card
   ├── PCM5102A DAC
   ├── MAX17048
   └── Rotary Encoder

Battery / Amplifier Supply
   └── Class-D Speaker Amplifier
        └── Speaker
```

---

# Communication Interfaces

| Interface | Devices |
|------------|---------|
| SPI | TFT Display, microSD Card |
| I²C | MAX17048 Fuel Gauge |
| I²S | PCM5102A DAC |
| GPIO | Buttons, Rotary Encoder, Headphone Detect |

---

# Design Notes

- TFT Display and microSD Card share the SPI bus with separate Chip Select lines.
- PCM5102A provides high-quality line-level analog audio.
- The Class-D amplifier drives the internal speaker.
- The 3.5 mm headphone jack is connected directly to the DAC outputs.
- The MAX17048 fuel gauge provides accurate battery percentage over I²C.
- Headphone insertion is detected using the jack's detect switch.
- A common ground is shared by all modules.

# Circuit Diagram

![Circuit schematic showing ESP32-S3 connections to TFT display, microSD card, PCM5102A DAC, MAX17048 fuel gauge, rotary encoder, buttons, amplifier, speaker, headphone jack, battery and power system. Includes labeled power flow and communication interface tables.](../images/schematics/schematic_v1.pdf)