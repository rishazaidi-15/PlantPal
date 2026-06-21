# 🌱 PlantPal

### An Emotion-Aware IoT Companion for Human–Plant Interaction

Transforming environmental sensor data into expressive emotional feedback to make plant care intuitive, engaging, and human-centered.

![ESP32](https://img.shields.io/badge/ESP32-IoT-success?style=for-the-badge)
![HCI](https://img.shields.io/badge/HCI-Human--Computer--Interaction-blue?style=for-the-badge)
![Data Science](https://img.shields.io/badge/Data%20Science-Research-orange?style=for-the-badge)
![Figma](https://img.shields.io/badge/Figma-UI%2FUX-purple?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active%20Development-brightgreen?style=for-the-badge)

**MSc Data Science Dissertation Project**  
IoT • Affective Computing • Human–Plant Interaction • UX Research

---

## 🌿 Why PlantPal?

Traditional plant monitoring systems display raw values such as:

- Soil Moisture: 34%
- Light Intensity: 620 lux
- Humidity: 41%

These metrics require interpretation and often fail to communicate urgency effectively.

PlantPal introduces an alternative approach:

Instead of numbers, plants communicate through emotions.

😊 Happy  
😴 Sleepy  
🥺 Thirsty  
😟 Worried  
😭 Distressed

### Research Question

Can emotion-based feedback improve plant-care understanding, empathy, and engagement compared to traditional numerical dashboards?

---

## ✨ Key Features

- Multi-Sensor Monitoring
- Emotion Engine
- On-Device TFT Display
- Companion Dashboard
- Research Instrumentation
- Low-Cost Hardware
- Emotion-First UX

---

## 🏗 System Architecture

```text
Soil Moisture Sensor
          │
Light Sensor
          │
Humidity Sensor
          ▼

        ESP32
          │
          ▼

   Emotion Engine
          │
     ┌────┴────┐
     │         │
     ▼         ▼

 TFT Display   Mobile Dashboard
     │
     ▼

 Human–Plant Interaction
```

---

## 🔧 Hardware

- ESP32 DevKit v1
- Capacitive Soil Moisture Sensor
- BH1750 Light Sensor
- DHT22 / BME280
- 2.4" ILI9341 TFT Display

---

## 📱 Planned Interfaces

### TFT Device
- Happy State
- Sleepy State
- Thirsty State
- Distressed State

### Mobile App
- Dashboard
- Analytics
- Plant Journal
- Emotion Timeline

### Research Dashboard
- Sensor Trends
- Emotion Trends
- User Study Results

---

## 📊 Research Contribution

PlantPal combines:

- IoT Sensing
- Human–Computer Interaction
- Affective Computing
- Data Science Evaluation

The contribution is the design and evaluation of an emotion-based interface for plant care.

---

## 🚀 Roadmap

- [x] Project Concept
- [x] Design System
- [ ] Hardware Assembly
- [ ] Firmware Development
- [ ] Emotion Engine Implementation
- [ ] User Study
- [ ] Dissertation Evaluation

---

## 📄 License

MIT License

---

Built as part of an MSc Data Science Dissertation.
