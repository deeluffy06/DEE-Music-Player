# DEE Music Player - System Architecture

**Version:** 1.0  
**Project:** DEE Music Player  
**Author:** Deepak

---

# 1. Overview

The DEE Music Player is a battery-powered portable audio player built around the ESP32-S3 microcontroller.

The system is divided into six major subsystems:

- Processing Unit
- Audio System
- Storage System
- User Interface
- Power Management
- Connectivity

Each subsystem is designed to be modular, allowing future upgrades without redesigning the entire system.

---

# 2. High-Level Architecture

```text
                         USB-C
                           │
                           ▼
                 Charging & Protection
                           │
                           ▼
                    Li-ion Battery
                           │
                           ▼
                  Power Management
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
        ▼                  ▼                  ▼
     ESP32-S3         Display Power      Audio Power
        │
        │
 ┌──────┼─────────────────────────────────────────────────────┐
 │      │             │             │            │            │
 ▼      ▼             ▼             ▼            ▼            ▼
IPS   microSD     Bluetooth    PCM5102A DAC   Buttons    Rotary Encoder
Display             Wi-Fi            │
                                     │
                        ┌────────────┴─────────────┐
                        │                          │
                        ▼                          ▼
                Headphone Output          Speaker Amplifier
                        │                          │
                        ▼                          ▼
                  3.5 mm Jack               52 mm Speaker
```

---

# 3. System Modules

---

## 3.1 Processing Unit

### Main Controller

Component:

- ESP32-S3

Responsibilities:

- User Interface
- Audio Streaming
- SD Card Access
- Bluetooth
- Battery Monitoring
- File System
- Playback Control

---

## 3.2 Audio System

### Audio Source

- microSD Card
- Bluetooth Receiver

↓

### Audio Decoder

- ESP32 Audio Library

↓

### Digital Audio

I2S Bus

↓

### External DAC

PCM5102A

↓

### Analog Audio

↓

Speaker Amplifier

↓

5 W Speaker

OR

↓

3.5 mm Stereo Headphone Jack

---

## 3.3 Storage System

Storage Medium

- microSD Card

Contents

- Music
- Configuration
- Favorites
- Resume Information

Supported Formats

- MP3
- WAV (Future)

---

## 3.4 User Interface

Display

- 2.4" IPS TFT

Controls

- Rotary Encoder
- Play/Pause
- Previous
- Next
- Back
- Home

Displayed Information

- Song Title
- Artist
- Playback Time
- Volume
- Battery
- Bluetooth Status
- Settings

---

## 3.5 Power System

Power Source

- 3000 mAh Li-ion Battery

Charging

- USB Type-C

Battery Protection

- Overcharge
- Over-discharge
- Short Circuit

Power Distribution

- ESP32
- Display
- DAC
- Amplifier

---

## 3.6 Connectivity

Bluetooth

Supported Modes

- Receiver
- Transmitter

USB

- Charging
- Firmware Upload
- Serial Debugging

---

# 4. Data Flow

```text
Music File
      │
      ▼
microSD Card
      │
      ▼
ESP32 Audio Decoder
      │
      ▼
I2S
      │
      ▼
PCM5102A DAC
      │
      ▼
Analog Audio
      │
      ├─────────────► Headphone Jack
      │
      ▼
Speaker Amplifier
      │
      ▼
Speaker
```

---

# 5. Control Flow

```text
User Input
      │
      ▼
Buttons / Rotary Encoder
      │
      ▼
ESP32
      │
      ▼
Menu Logic
      │
      ▼
Display Update
      │
      ▼
Playback Control
```

---

# 6. Battery Flow

```text
USB-C
   │
   ▼
Charging Circuit
   │
   ▼
Li-ion Battery
   │
   ▼
Power Management
   │
   ├────► ESP32
   ├────► Display
   ├────► DAC
   └────► Speaker Amplifier
```

---

# 7. Software Layers

```text
Application Layer
│
├── Music Player
├── Settings
├── File Browser
├── Bluetooth
├── Equalizer
└── Battery Monitor

──────────────────────────

Middleware

├── Audio Library
├── FAT File System
├── Display Driver
├── Bluetooth Stack
└── Preferences Storage

──────────────────────────

Hardware Drivers

├── SPI
├── I2S
├── GPIO
├── ADC
├── PWM
└── UART

──────────────────────────

Hardware

ESP32-S3
```

---

# 8. Communication Interfaces

| Interface | Connected Device |
|------------|------------------|
| SPI | IPS Display |
| SPI | microSD Card |
| I2S | PCM5102A DAC |
| GPIO | Buttons |
| GPIO | Rotary Encoder |
| ADC | Battery Voltage Monitor |
| USB | Charging & Programming |
| Bluetooth | Wireless Audio |

---

# 9. Future Expansion

Reserved Interfaces

- Wi-Fi Streaming
- OTA Updates
- Spotify Connect
- Companion Mobile App
- Touch Display
- USB DAC Mode

---

# 10. Architecture Principles

The system is designed around the following principles:

- Modular Design
- Low Power Consumption
- High Audio Quality
- Easy Maintenance
- Scalable Firmware
- Upgrade-Friendly Hardware