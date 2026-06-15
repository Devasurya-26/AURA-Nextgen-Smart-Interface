# 🌌 AURA — Nextgen Smart Interface

> *An atmospheric intelligence UI for smart home control — where biometrics meet environment.*

![AURA Banner](https://img.shields.io/badge/AURA-Nextgen%20Smart%20Interface-7C3AED?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQTEwIDEwIDAgMCAwIDIgMTJhMTAgMTAgMCAwIDAgMTAgMTAgMTAgMTAgMCAwIDAgMTAtMTBBMTAgMTAgMCAwIDAgMTIgMnoiLz48L3N2Zz4=)
![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

---

## 🧠 What is AURA?

AURA is a **smart home ambient intelligence interface** — a futuristic UI prototype that merges biometric health data with real-time environment control. The system reads your body (heart rate, stress, sleep quality) and predictively adjusts your room's temperature, lighting, and scent — before you even feel the need.

Think of it as **Jarvis for your living space.**

The interface is built around a **Glassmorphism + Deep Space** design language — floating glass panels over fluid animated metaballs that shift color based on your home's current "aura."

---

## ✨ Screens

| Screen | Description |
|--------|-------------|
| 🏠 **Aura Dashboard** | Main home hub — room status, mood, active atmosphere at a glance |
| 💓 **Biometric Insights** | Real-time HRV, stress score, sleep quality from wearable data |
| 🌡️ **Atmosphere Customizer** | Manual control — light, temperature, scent sliders + mood presets |
| 📅 **Predictive Schedule** | AI-driven daily timeline — room pre-conditions 15 min before each event |

---

## 🎨 Design System

### Visual Language
- **Style:** Glassmorphism over fluid animated metaballs
- **Theme:** Deep Space Dark (`#0B1326` base)
- **Depth:** `backdrop-filter: blur(30px)` + 1px rim-light border
- **Motion:** Organic floating blobs with staggered CSS keyframe animations

### Typography
```
Sora          → Display headings, atmospheric readings
Geist         → Body text, data values (Vercel's precision font)
Space Grotesk → Labels, metadata, technical caps
```

### Color Tokens
```css
--primary:   #d2bbff   /* Soft violet — calm state */
--secondary: #ffafd3   /* Blush pink  — energized state */
--tertiary:  #7bd0ff   /* Ice blue    — cool state */
--surface:   #0b1326   /* Deep navy   — base layer */
```

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────┐
│           AURA Navigator (HTML)          │
│                                         │
│  ┌──────────┐    ┌───────────────────┐  │
│  │ Sidebar  │───▶│     iframe        │  │
│  │ Nav      │    │  (base64 screen)  │  │
│  └──────────┘    └───────────────────┘  │
│                                         │
│  JS dictionary lookup → O(1) switching  │
└─────────────────────────────────────────┘
```

### Smart Home Data Flow (Production Architecture)
```
[Smartwatch / Phone]
        ↓ Bluetooth
[Edge Hub — Raspberry Pi]
        ↓ Python ML (LSTM model)
[Prediction Engine]
        ↓ WebSocket / MQTT
[AURA UI — This Repo]
        ↓ REST API
[Smart Devices — AC / Lights / Diffuser]
```

---

## 🔬 Core Logic

### Temperature Prediction
```python
# Weighted moving average on historical room data
def predict_next_temp(history):
    weights = [0.1, 0.15, 0.2, 0.25, 0.3]
    return sum(h * w for h, w in zip(history, weights))
```

### Stress Detection from Biometrics
```python
def detect_stress(hrv, skin_conductance, breath_rate):
    score = (1/hrv)*0.5 + skin_conductance*0.3 + (breath_rate-15)*0.2
    return "HIGH" if score > 0.7 else "MEDIUM" if score > 0.4 else "LOW"
```

### Predictive Pre-conditioning
```python
# Trigger atmosphere 15 mins before scheduled event
trigger_time = event_time - timedelta(minutes=15)
if current_time == trigger_time:
    set_atmosphere(event["activity"])
```

---

## 🚀 Getting Started

### Option 1 — Single File
```bash
# Download aura_navigator.html
# Open directly in any browser — no server needed
open aura_navigator.html
```

### Option 2 — Individual Screens
```bash
git clone https://github.com/yourusername/aura-nextgen-interface
cd aura-nextgen-interface

# Open any screen directly
open aura_dashboard/code.html
open biometric_insights/code.html
open atmosphere_customizer/code.html
open predictive_schedule/code.html
```
## 🔌 Tech Stack

| Layer | Technology |
|-------|-----------|
| Markup | HTML5 |
| Styling | Tailwind CSS (CDN) + Custom CSS |
| Scripting | Vanilla JavaScript |
| Icons | Google Material Symbols |
| Fonts | Google Fonts (Sora, Geist, Space Grotesk) |
| Animation | CSS Keyframes + `backdrop-filter` |
| Packaging | Python base64 embedding |

**No build step. No framework. No dependencies. Runs anywhere.**

---

## 🗺️ Roadmap

- [ ] WebSocket integration for live sensor data
- [ ] Google Calendar API hookup for schedule prediction
- [ ] React Native port for iOS / Android
- [ ] MQTT bridge for actual smart home device control
- [ ] LSTM model training pipeline for personalized predictions
- [ ] Voice command layer (Web Speech API)

---

## 🧩 Design Decisions

**Why no React/Vue?**
This is a UI prototype focused on design validation. Keeping it pure HTML means zero setup friction — designers, PMs, and clients can open it instantly. Production implementation would use React Native or Flutter.

**Why base64 embedding?**
Multi-screen prototypes usually require a file server. Base64 encoding each screen as a data URI lets the entire experience live in one portable HTML file — shareable over email, WhatsApp, Google Drive, anywhere.

**Why Glassmorphism?**
The visual metaphor of glass reflects the product's core idea — AURA is an invisible layer between you and your environment. You see through it, but it's always working.

---

## Developer

Devasurya Senthilkumar❤️
---

<div align="center">

**Built with 🌌 obsessive attention to atmosphere**

*AURA — Feel the intelligence.*

</div>
