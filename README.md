# 🎵 DEE Music Player

<p align="center">
  <b>A custom ESP32-based portable music player built from scratch.</b><br>
  An end-to-end embedded systems project covering hardware design, firmware development, PCB design, enclosure design, and product engineering.
</p>

---

## 📖 Overview

The **DEE Music Player** is a custom-built portable audio player developed using the ESP32 microcontroller.

Rather than being just another music player, this project is a complete embedded systems engineering journey. It is designed to demonstrate practical skills in electronics, firmware development, PCB design, power management, user interface design, and product development.

The repository documents every stage of development—from initial planning and breadboard prototyping to PCB manufacturing and final assembly.

---

# ✨ Features

## Current

- 🎵 MP3 Playback from Micro SD Card
- 🔊 High Quality I2S Audio Output
- 📂 File Browser
- 🎛 Rotary Encoder Navigation
- 🖥 OLED Display Interface
- 🔋 Battery Level Monitoring
- 🔌 USB-C Charging
- 🔈 Volume Control

---

## Planned

- 🌐 Wi-Fi Music Streaming
- 📶 Bluetooth Audio
- 📱 Mobile Web Control
- 🔄 OTA Firmware Updates
- ❤️ Favorites
- 🎼 Playlist Support
- 🌙 Theme Support
- ⏲ Sleep Timer
- 🔍 Search Songs

---

# 🛠 Hardware

| Component | Purpose |
|------------|----------|
| ESP32 Dev Board | Main Controller |
| MAX98357A | I2S Audio Amplifier |
| 0.96" OLED Display | User Interface |
| Rotary Encoder | Menu Navigation |
| Micro SD Card Module | Music Storage |
| Li-ion Battery | Portable Power |
| TP4056 Charging Module | Battery Charging |
| Speaker | Audio Output |
| Slide Switch | Main Power |

---

# 💻 Software

- Arduino Framework
- PlatformIO
- VS Code
- Git
- GitHub

---

# 🏗 System Architecture

```text
                +-------------------+
                |      ESP32        |
                +---------+---------+
                          |
      +-------------------+-------------------+
      |                   |                   |
      |                   |                   |
 OLED Display      Rotary Encoder      SD Card Module
      |                                       |
      +-------------------+-------------------+
                          |
                     MP3 Decoder
                          |
                    I2S Audio Output
                          |
                    MAX98357A Module
                          |
                       Speaker

Battery
    │
TP4056 Charger
    │
Power Circuit
    │
ESP32
```

---

# 📂 Repository Structure

```text
DEE-Music-Player/

├── docs/
│   ├── Architecture
│   ├── Datasheets
│   └── Design Notes
│
├── firmware/
│   └── ESP32 Firmware
│
├── hardware/
│   ├── Schematics
│   ├── PCB
│   └── BOM
│
├── enclosure/
│   ├── CAD
│   └── STL
│
├── images/
│
├── progress/
│
├── README.md
├── LICENSE
└── .gitignore
```

---

# 🚀 Development Roadmap

## Phase 1 — Planning

- [x] Repository Setup
- [x] Project Documentation
- [ ] Component Selection

---

## Phase 2 — Hardware

- [ ] Circuit Design
- [ ] Breadboard Prototype
- [ ] Power Testing

---

## Phase 3 — Firmware

- [ ] OLED Interface
- [ ] SD Card Driver
- [ ] Audio Playback
- [ ] Menu System

---

## Phase 4 — PCB

- [ ] PCB Design
- [ ] PCB Fabrication
- [ ] Assembly

---

## Phase 5 — Product

- [ ] Enclosure Design
- [ ] Testing
- [ ] Documentation
- [ ] Version 1.0 Release

---

# 📈 Project Status

| Module | Status |
|---------|--------|
| Planning | ✅ Complete |
| Component Selection | 🟨 In Progress |
| Hardware | ⬜ Pending |
| Firmware | ⬜ Pending |
| PCB Design | ⬜ Pending |
| Enclosure | ⬜ Pending |
| Testing | ⬜ Pending |

---

# 📸 Gallery

Images will be added as development progresses.

- Breadboard Prototype
- Circuit Connections
- OLED Interface
- PCB Design
- Final Product

---

# 🎓 Learning Objectives

This project is being developed to gain practical experience in:

- Embedded Systems
- ESP32 Development
- PCB Design
- Digital Audio
- Battery Management
- Product Design
- Git & GitHub
- Technical Documentation

---

# 🔮 Future Improvements

- Spotify Connect
- Bluetooth Speaker Mode
- Touch Display
- Mobile Companion App
- Voice Assistant Support
- USB DAC Mode

---

# 🤝 Contributing

Suggestions and ideas are always welcome.

If you'd like to improve the project, feel free to open an Issue or submit a Pull Request.

---

# 📄 License

Licensed under the MIT License.

---

# 👨‍💻 Author

**Deepak**

Electronics and Communication Engineering Student

GitHub: **[@deeluffy06](https://github.com/deeluffy06)**

---

<p align="center">
⭐ If you like this project, consider giving it a star.
</p>