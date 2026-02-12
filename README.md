# handy - mobile app for controlling presentations with hand gestures using computer vision

Tech stack for demo version:

1. **Python**
2. **Kivy** - Python mobile app framework - camera access, UI (buttons, labels)
3. **MediaPipe** - hand tracking (the core CV component) - detects hands in video, tracks 21 hand landmarks, runs in real-time
4. **OpenCV** - camera capture & image processing - captures video frames, converts image formats (MediaPipe needs RGB), draws visual feedback (circles, lines on screen)
5. **NumPy** - math operations (auto-installed with OpenCV/MediaPipe) - distance calculations, smoothing coordinates, array operations
6. **WebSockets** - communication between phone & laptop - sends gesture commands from phone to laptop, real-time, low latency
7. **Buildozer** - packages Python into Android APK - converts your Python code from development laptop into installable Android app (perfect for demo, no need for Google Play)
