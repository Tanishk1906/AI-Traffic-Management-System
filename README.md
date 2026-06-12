# 🚦 AI-Powered Smart Traffic Management System

An intelligent traffic optimization system that combines **Machine Learning**, **Computer Vision**, and **Real-Time Decision Making** to dynamically control traffic signals based on live vehicle density.

The system utilizes **YOLOv8 Object Detection** to analyze traffic feeds in real time, estimates congestion levels across multiple lanes, and applies a custom **Fairness-Based Scheduling Algorithm** to optimize traffic flow while preventing lane starvation.

This project demonstrates the practical application of AI in smart city infrastructure and intelligent transportation systems.

---

# 🌟 Problem Statement

Traditional traffic lights operate on fixed timers regardless of actual road conditions, leading to:

* Increased congestion
* Longer waiting times
* Fuel wastage
* Reduced traffic efficiency

The objective of this project is to develop an AI-driven traffic control system capable of:

* Understanding traffic density automatically
* Making real-time decisions
* Dynamically allocating signal durations
* Ensuring fairness across all traffic lanes

---

# 🧠 Machine Learning & AI Components

## Vehicle Detection using YOLOv8

The system employs **YOLOv8 Nano**, a state-of-the-art real-time object detection model, to detect and count vehicles from live camera feeds.

### Detected Classes

* Car
* Bus
* Truck
* Motorcycle

### ML Pipeline

```text
Video Feed
     ↓
Frame Extraction
     ↓
YOLOv8 Inference
     ↓
Vehicle Detection
     ↓
Vehicle Counting
     ↓
Traffic Density Estimation
     ↓
Decision Engine
     ↓
Traffic Signal Allocation
```

### Why YOLOv8?

* Real-time inference capability
* High detection accuracy
* Low computational overhead
* Suitable for edge deployments

---

# ⚙️ Intelligent Traffic Scheduling

Instead of fixed timers, signal duration is computed dynamically.

### Dynamic Green Time Formula

```text
Green Time = Base Time + (Vehicle Count × Weight Factor)
```

Example:

```text
Base Time = 5 seconds
Vehicle Count = 10
Weight Factor = 1.5

Green Time = 20 seconds
```

This allows highly congested lanes to receive longer green durations automatically.

---

# ⚖️ Fairness-Based Scheduling Algorithm

One limitation of density-based systems is lane starvation.

To address this, the system implements an Anti-Starvation mechanism:

* Each lane tracks wait cycles.
* Priority increases with waiting time.
* Low-density lanes receive scheduling boosts.
* Every lane is guaranteed service within a bounded number of cycles.

This combines optimization with fairness, making the system more practical for real-world deployment.

---

# 📡 Real-Time Streaming Architecture

The platform provides ultra-low latency monitoring using WebRTC.

### Features

* H.264 video encoding
* Browser-based streaming
* On-demand feed activation
* Reduced network bandwidth consumption

---

# 🚀 Key Features

### ✅ Real-Time Vehicle Detection

YOLOv8-based vehicle counting from multiple traffic feeds.

### ✅ Dynamic Signal Allocation

Adaptive green light duration based on vehicle density.

### ✅ Fairness Optimization

Prevents starvation of low-density lanes.

### ✅ Telemetry Mode

AI processing runs continuously while video streaming remains optional.

### ✅ Real-Time Dashboard

Live monitoring of:

* Vehicle count
* Signal state
* Wait cycles
* Active lane
* Stream status

### ✅ WebRTC Streaming

Low-latency traffic feed visualization.

---

# 🏗️ System Architecture

```text
Traffic Cameras
       │
       ▼
Computer Vision Layer
(OpenCV + YOLOv8)
       │
       ▼
Vehicle Detection
       │
       ▼
Density Estimation
       │
       ▼
Traffic Decision Engine
(Fairness Algorithm)
       │
       ▼
Node.js Controller
       │
       ▼
WebSocket Communication
       │
       ▼
React Dashboard
```

---

# 🛠️ Technology Stack

## Machine Learning

* YOLOv8
* Ultralytics
* OpenCV
* NumPy

## Backend

* Node.js
* Express.js
* Socket.io

## Frontend

* React.js
* CSS3

## Streaming

* WebRTC
* aiortc
* aiohttp

---

# 📂 Project Structure

```text
traffic-light-system/
│
├── backend/
│   ├── package.json
│   └── server.js
│
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
│
├── cv_worker/
│   ├── requirements.txt
│   ├── webrtc_tracker.py
│   ├── north.mp4
│   ├── south.mp4
│   ├── east.mp4
│   └── west.mp4
│
├── package.json
└── README.md
```

---

# ⚙️ Installation

### Clone Repository

```bash
git clone https://github.com/Tanishk1906/AI-Traffic-Management-System.git
cd AI-Traffic-Management-System
```

### Backend

```bash
cd backend
npm install
npm start
```

### Frontend

```bash
cd frontend
npm install
npm start
```

### Computer Vision Worker

```bash
cd cv_worker

python -m venv .venv

# Windows
.venv\Scripts\activate

pip install -r requirements.txt

python webrtc_tracker.py
```

---

# 📈 Future Improvements

* Reinforcement Learning-based signal optimization
* Traffic congestion prediction using time-series forecasting
* Emergency vehicle prioritization
* Multi-junction coordination
* Edge AI deployment using NVIDIA Jetson
* Cloud-based traffic analytics
* Historical traffic pattern analysis

---

# 👥 Project Team

* **Tanishka Meena**
* **Karthik**
* **Divyansh**
* **Tushar**
* **Sumay**

---

# 🎯 Learning Outcomes

This project demonstrates practical experience in:

* Machine Learning Deployment
* Computer Vision
* Object Detection
* Real-Time Inference Systems
* Applied AI for Smart Cities
* Distributed System Design
* Full-Stack Development
* WebRTC Streaming

---

# 📄 License

This project is intended for educational, research, and demonstration purposes.
