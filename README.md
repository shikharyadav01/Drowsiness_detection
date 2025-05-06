This project implements a real-time drowsiness detection system that monitors the driver's eyes using a webcam and alerts them if signs of drowsiness are detected. It uses computer vision, eye aspect ratio (EAR), and optionally a CNN-based eye state classifier to identify prolonged eye closure — a strong sign of sleepiness.

# 💤 Drowsiness Detection System

A real-time driver drowsiness detection system using computer vision techniques, built with Python, OpenCV, and Dlib.

![Demo](https://user-images.githubusercontent.com/your-gif-or-screenshot.gif)

---

## 🚗 Overview

Driver fatigue is a major cause of road accidents. This project aims to prevent such incidents by detecting signs of drowsiness through eye behavior and alerting the user in real-time with an alarm.

---

## 🛠️ Technologies Used

- Python
- OpenCV
- Dlib
- imutils
- playsound

---

## ⚙️ How It Works

1. Captures video through the webcam.
2. Detects face and eye landmarks using Dlib’s 68-point facial landmark detector.
3. Calculates the **Eye Aspect Ratio (EAR)**.
4. If the EAR falls below a threshold for a few seconds, it triggers an audible alarm.

---

## 🔁 Eye Aspect Ratio (EAR)

The EAR is calculated using the vertical and horizontal distances between eye landmarks.  
If the EAR < 0.25 for 48 consecutive frames, drowsiness is detected.

```python
EAR = (||p2 - p6|| + ||p3 - p5||) / (2 * ||p1 - p4||)


