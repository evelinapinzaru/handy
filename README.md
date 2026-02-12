# Handy - Computer Vision-Based Gesture Control for Presentations

## Overview
Handy is a mobile application that enables hands-free control of desktop presentations using computer vision and hand gesture recognition.\
\
**Why mobile?** Presentation laptops often face away from the presenter, making reliable camera-based gesture tracking difficult. A phone can be positioned conveniently to solve this issue.

## Features
- ✋ Swipe right/left to navigate slides
- 📱 Works with any Android phone
- 💻 Compatible with major presentation software (PowerPoint, Keynote, PDF viewers, Google Slides)
- 🔄 Low latency via real-time WebSocket communication

## Tech Stack (demo version)

### Core Technologies
- **Computer Vision**: MediaPipe, OpenCV
- **Mobile Framework**: Kivy (cross-platform)
- **Communication**: WebSockets
- **Desktop Control**: PyAutoGUI

### Supporting Libraries
- **NumPy**: Mathematical operations & array processing
- **Buildozer**: Android APK packaging (dev tool)

## Project Structure
```
handy/
├── src/
│   ├── \_\_init\_\_.py
│   ├── detector.py       # Gesture detection logic
│   ├── server.py         # Laptop WebSocket server
│   └── client.py         # Phone app
├── tests/
│   ├── \_\_init\_\_.py
│   └── test\_camera.py   # Test hand tracking
├── config/
│   └── settings.py       # Configuration (IP, thresholds, ports)
├── requirements.txt      # Python dependencies
├── buildozer.spec        # Android build configuration
└── README.md
```

## How It Works
```
┌─────────────┐         ┌──────────────┐         ┌─────────────┐
│   Phone     │         │   Laptop     │         │ Presentation│
│             │         │              │         │  Software   │
│  MediaPipe  │ ─────▶  │  WebSocket   │ ─────▶  │  (PowerPoint│
│   Camera    │ Gesture │   Server     │ Keyboard│   /PDF)     │
│             │  JSON   │              │  Events │             │
└─────────────┘         └──────────────┘         └─────────────┘
```

1. **Phone**: Captures video, detects hand landmarks, recognizes gestures
2. **Communication**: Sends gesture commands via WebSocket
3. **Laptop**: Receives commands, simulates keyboard presses
4. **Result**: Presentation advances/reverses

## Roadmap

### ⏳  Tier 1 - MVP (In progress)
- Hand detection with MediaPipe
- Swipe left/right gestures
- WebSocket communication
- Basic gesture smoothing

### 🚧 Tier 2 - Demo-Ready (Planned)
- Laser pointer (finger tracking)
- Point gesture recognition
- Visual feedback on phone
- Connection status indicator

### 📋 Tier 3 - Production Features (Planned)
- Multi-gesture support (5-7 gestures)
- Kalman filtering for smoother tracking
- Customizable sensitivity settings
- Distance-based speed control