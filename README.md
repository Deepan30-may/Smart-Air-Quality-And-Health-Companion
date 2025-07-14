# 🌬️ Smart Air Quality & Health Companion (AI + IoT)

A low-cost, AI-powered, portable health companion that monitors air quality, temperature, and humidity in real-time and warns users before their environment becomes hazardous—especially useful for individuals with asthma, respiratory, or heart conditions.

---

## 📘 What Is This Project About?

This is **more than just an IoT project**. It's a smart system that:
- 🧠 Monitors environmental conditions using sensors (MQ-135, DHT11/22)
- 🔔 Predicts health risks using an AI model
- 📱 Alerts users in real-time via LED, buzzer, or mobile notifications
- 📊 Gives personalized health advice based on air quality
- 📡 Works offline and syncs to cloud later

Think of it as a **“smart guard for your lungs.”**

---

## 🎯 Why Are We Building This?

- 🌫️ **Air Pollution** kills 7 million people every year (WHO).
- 👶👵 Vulnerable groups like kids, elderly, and asthma patients need early warning.
- 💸 Existing solutions are expensive, generic, and often online-only.
- 🔍 We aim to create a **smart, affordable, offline-capable alternative**.

---

## 🌍 Real-World Impact

| ✅ Benefit | 💡 Description |
|-----------|----------------|
| Personal Protection | Real-time alerts on bad air |
| Public Health Data | Anonymized sharing to detect city hotspots |
| Education | Encourages awareness and behavior change |
| Custom Health Advice | Tailored tips like "avoid jogging" or "open windows" |

---

## 💡 Who Can Benefit?

| 👤 Target Group | 🩺 Value |
|----------------|---------|
| Asthma Patients | Avoid attacks by early alerts |
| Parents | Safer air for children |
| Elderly | Prevents heart/breathing issues |
| Students | Learn about tech and pollution |
| Urban Dwellers | Understand local air trends |

---

## 🧠 What Makes It Smart?

| Traditional IoT | Smart Companion (Ours) |
|-----------------|------------------------|
| Static sensor readings | AI-powered predictions |
| No personalization | Learns user health profile |
| Online-only | Offline support + sync |
| No feedback | Alerts + tips via app |

---

## 🔧 Hardware Components

| Component | Purpose |
|----------|---------|
| ESP32 | Wi-Fi + BLE microcontroller |
| MQ-135 | Detects CO2, NH3, Benzene, smoke |
| DHT11 / DHT22 | Measures temperature + humidity |
| OLED Display (optional) | Displays sensor values |
| Red/Green LED | Visual air status |
| Li-ion Battery | Portable power |
| Buzzer (optional) | Audible warning for bad air |

---

## 🧠 AI Model (Health Risk Prediction)

**Goal:** Predict whether current environmental conditions are hazardous.

**Option 1: TinyML (on-device)**  
- Use TensorFlow Lite Micro  
- Train on historical labeled sensor data  
- Deploy `.tflite` model on ESP32

**Option 2: Backend ML Model**  
- ESP32 sends data to Firebase or Node.js server  
- Python ML model (e.g., Random Forest) returns risk prediction + advice

---

## 📱 Software Stack

| Layer | Technology |
|-------|------------|
| Firmware | Arduino IDE (C++) |
| AI Model | Python (Pandas, Scikit-learn, TensorFlow) |
| Mobile App | Flutter / React Native / MIT App Inventor |
| Backend | Firebase / Node.js |
| Database | Firebase / Firestore / SQLite |
| IoT Protocol | MQTT (preferred) or HTTP |

---

## 📡 System Architecture

```plaintext
Sensors (MQ-135 + DHT11)
        ↓
      ESP32
        ↓
  ┌────────────┐
  │ AI Model   │ ← (TinyML or backend)
  └────────────┘
        ↓
If air quality is poor:
  → Turn on RED LED
  → Trigger buzzer
  → Send push alert to mobile app
  → Save data locally (offline)
        ↓
Sync to cloud (when connected)
