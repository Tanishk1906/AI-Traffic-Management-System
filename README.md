# 🚦 AI-Powered Smart Traffic Management System

An intelligent traffic optimization system that combines **Machine Learning**, **Computer Vision**, and **Real-Time Decision Making** to dynamically control traffic signals based on live vehicle density.

The system utilizes **YOLOv8 Object Detection** to analyze traffic feeds in real time, estimates congestion levels across multiple lanes, and applies a custom **Fairness-Based Scheduling Algorithm** to optimize traffic flow while preventing lane starvation.

The platform also provides a real-time monitoring dashboard accessible through **http://localhost:3000**, enabling operators to observe traffic conditions, AI-generated insights, vehicle counts, and signal states in real time.

---

# 🌟 Problem Statement

Traditional traffic lights operate on fixed timers regardless of actual road conditions, leading to:

* Increased congestion
* Longer waiting times
* Fuel wastage
* Reduced traffic efficiency

This project introduces an AI-driven solution capable of:

* Understanding traffic density automatically
* Making real-time decisions
* Dynamically allocating signal durations
* Ensuring fairness across all traffic lanes

---

# 🧠 Machine Learning & Computer Vision

## Vehicle Detection using YOLOv8

The system employs **YOLOv8 Nano**, a state-of-the-art real-time object detection model, to detect and count vehicles from multiple traffic feeds.

### Detected Vehicle Classes

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
* Lightweight architecture
* Suitable for edge deployments
* Industry-standard object detection framework

---

# ⚙️ Intelligent Traffic Scheduling

Unlike conventional fixed-time traffic signals, this system dynamically computes signal duration based on current traffic conditions.

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

This allows heavily congested lanes to receive longer green durations automatically.

---

# ⚖️ Fairness-Based Scheduling Algorithm

A purely density-based system can lead to lane starvation.

To solve this problem, the system implements a custom Anti-Starvation Algorithm:

* Tracks waiting cycles for each lane
* Increases priority as wait time grows
* Guarantees service for low-density lanes
* Balances efficiency and fairness

This approach improves practicality for real-world deployments.

---

# 📡 Real-Time Streaming Architecture

The platform supports ultra-low latency monitoring using WebRTC.

### Features

* H.264 video encoding
* Browser-based streaming
* On-demand feed activation
* Reduced network bandwidth consumption
* Real-time visual monitoring

---

# 🚀 Key Features

### ✅ Real-Time Vehicle Detection

YOLOv8-powered vehicle counting from multiple traffic feeds.

### ✅ Dynamic Signal Allocation

Adaptive signal timing based on live vehicle density.

### ✅ Fairness Optimization

Prevents lane starvation and ensures balanced traffic flow.

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

Ultra-low latency live traffic feed visualization.

### ✅ WebSocket Synchronization

Instant communication between AI worker, backend controller, and dashboard.

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
Socket.io Communication
       │
       ▼
React Dashboard
```

---

# 🛠️ Technology Stack

## Machine Learning & Computer Vision

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

## Streaming & Communication

* WebRTC
* aiortc
* aiohttp
* WebSockets

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

## Clone Repository

```bash
git clone https://github.com/Tanishk1906/AI-Traffic-Management-System.git

cd AI-Traffic-Management-System
```

## Backend Setup

```bash
cd backend
npm install
```

## Frontend Setup

```bash
cd ../frontend
npm install
```

## Python Environment Setup

```bash
cd ../cv_worker

python -m venv .venv

# Windows
.venv\Scripts\activate

pip install -r requirements.txt
```

---

# ▶️ Running the Application

After starting all services, the application will be available locally.

| Service            | URL                   |
| ------------------ | --------------------- |
| React Dashboard    | http://localhost:3000 |
| Backend Server     | http://localhost:4000 |
| AI & WebRTC Worker | http://localhost:5000 |

### Terminal 1 — Backend

```bash
cd backend
npm start
```

### Terminal 2 — Frontend

```bash
cd frontend
npm start
```

### Terminal 3 — AI Worker

```bash
cd cv_worker
python webrtc_tracker.py
```

### Open Dashboard

```text
http://localhost:3000
```

The dashboard provides:

* Real-time vehicle counts
* Dynamic signal allocation
* Live traffic monitoring
* Wait-cycle analytics
* AI-powered decision making
* WebRTC-based camera streams

---

# 📈 Future Enhancements

* Reinforcement Learning-based traffic optimization
* Traffic congestion forecasting
* Emergency vehicle prioritization
* Multi-junction coordination
* Edge AI deployment using NVIDIA Jetson
* Historical traffic analytics
* Cloud deployment and monitoring
* Smart city infrastructure integration

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
* WebRTC Streaming
* Full-Stack Development
* Real-Time Data Processing

---

# 📄 License

This project is intended for educational, research, and demonstration purposes.
