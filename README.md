<div align="center">

<img src="docs/assets/banner.png" alt="PlantPal banner" width="100%" />

# 🌱 PlantPal

**An emotion-aware IoT companion for human–plant interaction**

*MSc Data Science Dissertation — IoT · HCI · Affective Computing*

[![ESP32](https://img.shields.io/badge/hardware-ESP32-3B6D11?style=flat-square)](#hardware)
[![Arduino](https://img.shields.io/badge/firmware-Arduino_C%2B%2B-185FA5?style=flat-square)](#firmware)
[![Status](https://img.shields.io/badge/status-active_development-EF9F27?style=flat-square)](#roadmap)
[![License](https://img.shields.io/badge/license-MIT-444441?style=flat-square)](LICENSE)
[![Figma](https://img.shields.io/badge/design-Figma-993556?style=flat-square)](#design-system)

[Demo video](#demo) · [Read the dissertation](#research) · [Design files](#design-system) · [Get started](#getting-started)

</div>

---

## What is PlantPal?

Most plant monitoring systems show you numbers — 34% moisture, 620 lux — and leave you to interpret them. PlantPal takes a different approach: it reads your plant's environment and translates it into an emotional state, shown through a small animated character living next to your plant.

The idea isn't novel for being "another IoT sensor project" — it's novel for treating the *interface* as the research question. Does affective feedback change how people relate to and care for a houseplant, compared to a numeric dashboard? That's what this project measures.

<div align="center">
<img src="docs/assets/hero-screenshot.png" alt="PlantPal device and app showing happy state" width="640" />
</div>

## Features

| | |
|---|---|
| 🌡️ **Multi-sensor monitoring** | Soil moisture, light intensity, ambient humidity via ESP32 |
| 😊 **Emotion engine** | Rule-based model maps sensor scores to 6 expressive states |
| 🖥️ **On-device display** | Animated character on a 2.4" TFT — no app required to read |
| 📱 **Companion app** | Mobile dashboard with trends, history, and care insights |
| 📊 **Research instrumentation** | Built-in data logging for the user study comparing emotional vs numeric feedback |
| 🔌 **Low-cost hardware** | Full BOM under £30, no actuators — feedback only, by design |

## How it works

```
Soil sensor ─┐
Light sensor ─┼──→ ESP32 ──→ Emotion engine ──→ TFT display (on-device)
Humidity sensor ┘                │
                                  └──→ MQTT / WiFi ──→ Companion app
```

Each sensor reading is normalised to a 0–100 score, combined into a weighted composite (moisture weighted highest — it's the most survival-critical factor), then routed through a small state machine into one of six emotions: **happy, neutral, thirsty, sleepy, sad, critical**. Full model details are in [`docs/emotion-engine.md`](docs/emotion-engine.md).

## Hardware

| Component | Purpose | Cost |
|---|---|---|
| ESP32 DevKit v1 | Microcontroller, WiFi | ~£5 |
| Capacitive soil moisture sensor | Soil moisture (analog) | ~£2 |
| BH1750 | Ambient light (I²C, lux) | ~£2 |
| DHT22 / BME280 | Humidity + temperature | ~£3 |
| 2.4" ILI9341 TFT (240×320) | On-device emotion display | ~£6 |

Full wiring diagram and pin map: [`docs/hardware.md`](docs/hardware.md).

## Repository structure

```
PlantPal/
├── firmware/              ESP32 Arduino sketch (sensors, emotion engine, display)
├── app/                   React Native companion app
├── design/                Figma exports, design tokens, component specs
├── docs/
│   ├── hardware.md        Wiring, pin map, calibration
│   ├── emotion-engine.md  Scoring formulas, thresholds, state machine
│   ├── research/          Study design, survey instruments, results
│   └── assets/            Screenshots, diagrams, banner
└── data/                  Sensor logs from user study (anonymised)
```

## Getting started

```bash
git clone https://github.com/yourusername/plantpal.git
cd plantpal/firmware
# Open PlantPal.ino in Arduino IDE, select ESP32 Dev Module, flash
```

See [`docs/hardware.md`](docs/hardware.md) for wiring and [`docs/setup.md`](docs/setup.md) for the full build walkthrough.

## Design system

The character, app, and device UI follow one visual language — sage green and clay palette, a "breathing" glow that mirrors plant health, and an emotion-first layout. Figma file: *[link]*. Token reference: [`design/tokens.md`](design/tokens.md).

<div align="center">
<img src="docs/assets/screens-grid.png" alt="App screens grid" width="640" />
</div>

## Research

This project's contribution is the emotion-mapping model and the empirical comparison of affective vs numeric feedback for plant care. Study design, hypotheses, and instruments live in [`docs/research/`](docs/research). Results and analysis are added as the user study completes.

| | |
|---|---|
| **RQ** | Does emotional feedback increase care behaviour and empathy vs a numeric dashboard? |
| **Design** | Within-subjects, counterbalanced, n=12, 7-day conditions |
| **Status** | 🟡 Data collection in progress |

## Roadmap

- [ ] Computer-vision leaf health detection (ESP32-CAM)
- [ ] Predictive health model (time-series forecast)
- [ ] Multi-plant mesh network
- [ ] Voice feedback

## License

MIT — see [LICENSE](LICENSE).

---

<div align="center">
<sub>Built as part of an MSc Data Science dissertation, 2026.</sub>
</div>
