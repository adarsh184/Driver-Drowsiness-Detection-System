# Driver Drowsiness Detection System

Driver fatigue is one of the major causes of road accidents worldwide.
This project addresses this problem by implementing a vision-based drowsiness detection system that works in real time using a webcam.

- The system analyzes facial landmarks to
* Detect prolonged eye closure
* Calculate blink rate
* Identify yawning behavior
* If the driver’s eyes remain closed for more than 10 seconds, an alarm is activated to alert the driver.

##  Description 

A real-time driver monitoring system that detects drowsiness using
eye closure duration, blink rate, and yawn detection from a live webcam feed.

This project focuses on **real-time reliability** using MediaPipe facial landmarks.
The system is designed to be lightweight, interpretable, and reliable
for real-time execution .


---

##  Features
- Eye Aspect Ratio (EAR) based eye-closure detection
- 10-second continuous eye-closure alert
- Blink rate analysis
- Yawn detection
- Adaptive EAR threshold (driver-specific calibration)
- Alarm stops automatically when eyes open
- Auto screenshot capture on alert
  

---

##  System Architecture

Pipeline:

Webcam  
→ Face Detection  
→ Landmark Extraction  
→ EAR / MAR Calculation  
→ Temporal Analysis  
→ Alert Generation

## Technologies Used

| Technology | Description                        |
| ---------- | ---------------------------------- |
| Python     | Core programming language          |
| OpenCV     | Video processing and visualization |
| MediaPipe  | Facial landmark detection          |
| NumPy      | Mathematical computations          |
| Pygame  | Audio alert generation             |


## Facial Landmark Model

This project uses MediaPipe Face Mesh, which provides 468 3D facial landmarks in real time.

Key regions used:

-  Left & Right Eyes
-  Mouth

These landmarks enable accurate measurement of eye and mouth movements.

## Methodology

The system uses **MediaPipe Face Mesh** to extract facial landmarks.
From these landmarks:

- **EAR (Eye Aspect Ratio)** is computed to determine eye openness
- **MAR (Mouth Aspect Ratio)** is used to detect yawning
- Time-based logic determines drowsiness severity
 
Eye closure is detected using the Eye Aspect Ratio (EAR) formula:

EAR = (||p2 - p6|| + ||p3 - p5||) / (2 * ||p1 - p4||)

<img width="423" height="335" alt="image" src="https://github.com/user-attachments/assets/dae2ba34-603b-4b68-ae25-439d12a1c7a0" />

<img width="414" height="322" alt="image" src="https://github.com/user-attachments/assets/df0295cc-9ac7-4f6a-824c-4575dafc7e8c" />


## Yawn Detection

Yawning is detected using Mouth Aspect Ratio (MAR):

<img width="894" height="458" alt="image" src="https://github.com/user-attachments/assets/e066b40e-947f-4523-a4cb-0f497fbb0b90" />


## Results

| Scenario             | Output                |
| -------------------- | --------------------- |
| Normal Driving       | No alert              |
| Frequent Blinks      | Blink rate displayed  |
| Yawning              | Yawn detected message |
| Eyes closed > 10 sec | Alarm triggered       |


## Applications

- Driver safety and accident prevention
- Advanced Driver Assistance Systems (ADAS)
- Real-time fatigue monitoring


##  If you like this project, don’t forget to ⭐ the repository!
