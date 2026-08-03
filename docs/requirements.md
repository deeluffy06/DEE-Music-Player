# DEE Music Player - System Requirements

**Version:** 1.0  
**Project:** DEE Music Player  
**Author:** Deepak  
**Last Updated:** August 2026

---

# 1. Project Objective

The DEE Music Player is a portable, battery-powered music player built around the ESP32-S3 microcontroller.

The objective of this project is to design and develop a complete embedded audio system that demonstrates skills in:

- Embedded Systems
- Audio Electronics
- PCB Design
- Firmware Development
- Power Electronics
- Product Design
- Technical Documentation

This repository documents the complete engineering process from concept to final hardware.

---

# 2. Functional Requirements

## Audio

### FR-01
The system shall play music stored on a microSD card.

### FR-02
The system shall support MP3 playback.

### FR-03
The system should support WAV playback.

### FR-04
The system shall provide high-quality audio through a dedicated external DAC.

### FR-05
The system shall output audio through an internal speaker.

### FR-06
The system shall output audio through a 3.5 mm stereo headphone jack.

### FR-07
The system shall support Bluetooth audio reception (Phone → Music Player).

### FR-08
The system shall support Bluetooth audio transmission (Music Player → Bluetooth Headphones).

### FR-09
The system shall provide software volume control.

### FR-10
The system shall provide equalizer presets.

---

# 3. User Interface Requirements

### FR-11
The system shall include a 2.4-inch IPS TFT display.

### FR-12
The user shall navigate the interface using a rotary encoder.

### FR-13
The system shall include dedicated physical buttons.

### FR-14
The interface shall display:

- Song Name
- Artist
- Album (Future)
- Playback Time
- Progress Bar
- Volume
- Battery Percentage

### FR-15
The interface shall include:

- Settings Menu
- Music Browser
- Favorites
- Theme Selection

---

# 4. Power Requirements

### FR-16
The system shall operate from a rechargeable Li-ion battery.

### FR-17
The battery capacity shall be approximately 3000 mAh.

### FR-18
The system shall charge through USB Type-C.

### FR-19
The battery percentage shall be displayed.

### FR-20
The system shall provide a low-battery warning.

### FR-21
The system shall automatically enter sleep mode after a user-defined timeout.

---

# 5. Storage Requirements

### FR-22
The system shall store music on a microSD card.

### FR-23
The system shall support folder navigation.

### FR-24
The system shall support Favorites.

### FR-25
The system shall remember the last played song.

### FR-26
The system shall remember playback position after power-off.

---

# 6. Hardware Requirements

The hardware shall include:

- ESP32-S3
- PCM5102A DAC
- Analog Class-D Speaker Amplifier
- 2.4-inch IPS TFT Display
- microSD Card Slot
- 52 mm 5 W Speaker
- 3.5 mm Stereo Headphone Jack
- 3000 mAh Li-ion Battery
- USB-C Charging Circuit
- Battery Protection Circuit
- Rotary Encoder
- Navigation Buttons

---

# 7. Software Requirements

The firmware shall provide:

- Song Browser
- Settings Menu
- Battery Monitoring
- Volume Control
- Equalizer
- Favorites
- Theme Support
- Button Lock
- Sleep Timer
- Resume Playback

---

# 8. Performance Requirements

The system should:

- Boot within 3 seconds.
- Navigate menus smoothly.
- Play music without audio stuttering.
- Detect headphone insertion automatically.
- Display accurate battery information.
- Provide stable playback over Bluetooth.

---

# 9. Non-Functional Requirements

The project shall:

- Be modular.
- Be well documented.
- Use Git for version control.
- Be maintainable.
- Be expandable for future versions.

---

# 10. Version 1 Feature Checklist

| Feature | Status |
|---------|--------|
| Offline Music Playback | ✅ |
| High-Quality DAC | ✅ |
| Dedicated Speaker Amplifier | ✅ |
| Bluetooth Receiver | ✅ |
| Bluetooth Transmitter | ✅ |
| Built-in Speaker | ✅ |
| 3.5 mm Headphone Output | ✅ |
| microSD Storage | ✅ |
| Physical Buttons | ✅ |
| Rotary Encoder | ✅ |
| 2.4" IPS TFT Display | ✅ |
| Battery Percentage | ✅ |
| USB-C Charging | ✅ |
| Equalizer Presets | ✅ |
| Favorites | ✅ |
| Sleep Timer | ✅ |
| Themes | ✅ |
| Button Lock | ✅ |
| Resume Playback | ✅ |
| Last Song Memory | ✅ |
| Folder Navigation | ✅ |

---

# 11. Future Versions

The following features are outside the scope of Version 1:

- Wi-Fi Music Streaming
- Spotify Connect
- Mobile Companion App
- OTA Firmware Updates
- Touchscreen Display
- Voice Assistant Integration
- USB DAC Mode
- Album Art Display
- Gapless Playback
- Playlist Import (.m3u)

---

# 12. Success Criteria

The project will be considered successful when:

- All Version 1 features are operational.
- Stable audio playback is achieved.
- Battery-powered operation is reliable.
- The PCB functions without hardware modifications.
- The enclosure securely houses all components.
- Complete documentation is available.