# Driver-Drowsiness-Detection-System

A real-time driver monitoring system that detects drowsiness using
eye closure duration, blink rate, and yawn detection from a live webcam feed.

This project focuses on **real-time reliability** using MediaPipe facial landmarks.
The system is designed to be lightweight, interpretable, and reliable
for real-time execution on CPU-only machines.


---

## 📌 Features
- Eye Aspect Ratio (EAR) based eye-closure detection
- 10-second continuous eye-closure alert
- Blink rate analysis
- Yawn detection
- Adaptive EAR threshold (driver-specific calibration)
- Alarm stops automatically when eyes open
- Auto screenshot capture on alert
  

---

## 🧠 Methodology

The system uses **MediaPipe Face Mesh** to extract facial landmarks.
From these landmarks:

- **EAR (Eye Aspect Ratio)** is computed to determine eye openness
- **MAR (Mouth Aspect Ratio)** is used to detect yawning
- Time-based logic determines drowsiness severity

This geometric approach is:
- Fast
- Interpretable
- Robust to lighting and pose variations

---


## 🏗️ System Architecture

![System Architecture](assets/images/system_architecture.png)

Pipeline:

Webcam  
→ Face Detection  
→ Landmark Extraction  
→ EAR / MAR Calculation  
→ Temporal Analysis  
→ Alert Generation
