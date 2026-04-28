# 🚗 Real-Time Driver Monitoring System

A production-grade computer vision pipeline that detects driver 
fatigue and distraction in real-time using facial landmark analysis 
and machine learning.

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0.10-orange)
![Accuracy](https://img.shields.io/badge/Accuracy-94.47%25-brightgreen)

---

## 🎯 Problem Statement

Driver fatigue and distraction are leading causes of road accidents 
globally. Traditional alert systems rely on expensive hardware or 
cloud APIs. This system provides a **lightweight, real-time, 
on-device AI solution** that runs on standard webcam hardware — 
no internet required.

---

## ⚙️ How It Works

Webcam Feed → MediaPipe Face Mesh → Landmark Extraction
→ Feature Engineering → ML Classifier → Alert System

1. **Face Detection** — MediaPipe Face Mesh extracts 468 facial 
   landmarks per frame
2. **Feature Extraction** — Eye Aspect Ratio (EAR), Mouth Aspect 
   Ratio (MAR), and head pose angles computed per frame
3. **Classification** — Scikit-learn classifier trained on extracted 
   features detects drowsiness / distraction states
4. **Alert** — Real-time on-screen warning triggered below threshold

---

## 📊 Performance

| Metric | Value |
|--------|-------|
| Accuracy | **94.47%** |
| Frames Processed | **6,500+** |
| Latency | **< 1 second** |
| Hardware Required | Standard webcam |

---

## 🛠️ Tech Stack

- **Python 3.8+**
- **OpenCV** — real-time video capture and frame processing
- **MediaPipe** — facial landmark detection (Face Mesh)
- **Scikit-learn** — ML classification model
- **NumPy / Pandas** — feature computation and data handling

---

## 🚀 Setup & Run

```bash
# Clone the repo
git clone https://github.com/Utkarsh300503/Real-Time-Driver-Monitoring-System.git
cd Real-Time-Driver-Monitoring-System

# Install dependencies
pip install -r requirements.txt

# Run the system
python main.py
```

---

## 📁 Project Structure

├── main.py                  # Entry point — real-time detection loop
├── detector.py              # Landmark extraction & feature computation
├── model/
│   └── classifier.pkl       # Trained Scikit-learn model
├── utils/
│   └── alerts.py            # Alert trigger logic
├── requirements.txt
└── README.md

---

## 🔍 Key Engineering Decisions

- **MediaPipe over Dlib** — faster inference, no C++ build dependency
- **EAR/MAR thresholds** tuned via iterative testing on varied lighting
- **Fault-tolerant pipeline** — handles frame drops, partial occlusion, 
  and variable lighting without crashing
- **On-device inference** — no cloud API calls, sub-second latency 
  even on CPU

---

## 👤 Author

**Utkarsh Tiwari**  
[LinkedIn](https://linkedin.com/in/utkarshtiwari300503) • 
[GitHub](https://github.com/Utkarsh300503)
