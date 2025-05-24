# Smart Lock – Full Stack IoT Access System

A complete **IoT-based smart lock system** using an **ESP32-CAM**, facial recognition, and keypad input. This monorepo contains the full stack:

-  **Frontend:** React Native app (Expo)
-  **Backend:** Node.js + Express + PostgreSQL
-  **Microservice:** Python Flask face recognition API
-  **Hardware Integration:** ESP32-CAM, Relay, Buzzer

---

##  Repositories / Modules

| Folder                             | Description                             |
|------------------------------------|-----------------------------------------|
| [`Smart-Lock-Client`](./Smart-Lock-Client)         | React Native app (mobile interface)     |
| [`Smart-Lock-Server`](./Smart-Lock-Server)         | Node.js API server & database backend   |
| [`face-recognition-microservice`](./face-recognition-microservice) | Flask microservice for face verification |

---

## Quick Start

### 1. Clone the Monorepo with Submodules

```bash
git clone --recurse-submodules https://github.com/ziadteama/Smart-Lock.git
cd Smart-Lock

# Initialize & pull submodules
git submodule update --init --recursive
git pull --recurse-submodules
git submodule update --remote --merge
```

### 2. Backend Setup (Node.js + Express)

```bash
cd Smart-Lock-Server
cp .env.example .env
npm install
npm run dev
```

### 3. Face Recognition Microservice (Python + Flask)

```bash
cd ../face-recognition-microservice
pip install -r requirements.txt
python app.py
```

### 4. Frontend Setup (React Native Expo)

```bash
cd ../Smart-Lock-Client
npm install
npx expo start
```

---

## 🔧 ESP32-CAM Integration

- Sends base64 image via HTTP POST to microservice
- Keypad input triggers camera + validation
- Relay unlocks door if face/PIN match
- LED, buzzer, LCD show system state
- PIR sensor triggers alerts on intrusion

---

## Backend Overview (`Smart-Lock-Server`)

- Auth: login, register (with photo)
-  Routes: `/api/unlock`, `/api/lock`
-  Logs access events (with images)
-  Sends photo to face service for verification
-  MQTT or HTTP control with ESP

---

##  Face Recognition Microservice

- Python + Flask
- `POST /verify` – match base64 face
- `POST /register` – enroll user with photo

---

## 📱 Frontend App Features

- Login / Register (with optional face)
- Lock/unlock buttons + lock status
- Take photo for unlock verification
- View access logs with images

---

## 🧑‍💻 Contributors

- Mohamed ElTabakh – 221017595  
- Ziad Teama – 221007636  
- Omar Khalifa – 221017776  
- Youssef Medhat – 221017569  
- Ahmed Osama – 221011400  





