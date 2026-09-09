<div align="center">

# ⚡ Reaction Speed & Latency Test

**A modern, ultra-responsive benchmarking tool for measuring human reflexes and input latency with sub-millisecond precision.**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-testreaction.monard.online-10b981?style=for-the-badge&logo=googlechrome&logoColor=white)](https://testreaction.monard.online)
[![Zero Dependencies](https://img.shields.io/badge/Dependencies-Zero%20(Pure%20Vanilla)-blue?style=for-the-badge)](https://github.com/)
[![License](https://img.shields.io/badge/License-MIT-purple?style=for-the-badge)](LICENSE)
[![Languages](https://img.shields.io/badge/i18n-RO%20|%20EN%20|%20RU-orange?style=for-the-badge)](https://github.com/)

[**🚀 Launch Live Demo**](https://test-reaction.monard.online) • [**📖 Key Features**](#-key-features) • [**🎯 Aim Trainer Mode**](#-aim-trainer-mode-10---25) • [**🛠️ Technical Architecture**](#-technical-architecture--latency-optimizations) • [**🎮 Controls**](#-controls--usage)

---

</div>

## 📌 About The Project

**Reaction Speed Test** is an advanced, standalone web application engineered for competitive gamers, athletes, and hardware enthusiasts seeking to test their visual reaction times down to the **sub-millisecond level**.

Unlike generic web-based reaction tests that rely on naive `setTimeout` loops and standard `click` events, this engine synchronizes with the browser's display rendering pipeline (`requestAnimationFrame`), utilizes hardware-backed timing (`performance.now()`), and captures instant physical interactions via `pointerdown` to eliminate mechanical switch-release delay and browser compositing jitter.

---

## ✨ Key Features

- ⏱️ **Sub-Millisecond Accuracy**: High-resolution time measurement compliant with the W3C High Resolution Time Level 2 API.
- 🎯 **Dynamic Scaling & Aim Trainer (10% - 95%)**:
  - **10% - 25% (Micro Target)**: The arena automatically shifts into a high-precision circular target for flick and reflex drills.
  - **Random Position**: The target teleports to unpredictable coordinates across the viewport after each reset.
  - **70% - 95% (Full Arena)**: Classic large-format mode optimized for desktop monitors and immersive testing.
- 📊 **10-Round Session Analytics & Scoreboard**:
  - Round-by-round visual tracking for every attempt.
  - Real-time aggregate statistics: **Average**, **Best Time**, **Worst Time**, and performance consistency.
  - Intelligent detection for premature triggers (**False Start / Too Soon**).
- 📱 **Mobile & Touch Ergonomics**:
  - `touch-action: manipulation` eliminates the native 300ms mobile tap delay.
  - Horizontally scrollable scoreboard with sticky attempt labels for mobile viewports (≤768px).
  - Dynamic user prompts (e.g., *"Tap the screen"* on touch devices vs *"Click / Spacebar"* on desktop).
- 🌐 **Internationalization (i18n)**:
  - Built-in multi-language engine supporting **English 🇬🇧**, **Română 🇷🇴**, and **Русский 🇷🇺**.
  - Automatic browser locale detection with persistent user preferences saved to `localStorage`.
- 🎨 **Sleek Cyberpunk & Glassmorphic UI**:
  - Dark theme aesthetics inspired by UNA MD (subtle radial glows, masked gridlines, high contrast).
  - Native Fullscreen toggle with responsive geometry adaptation.
- 🔒 **Zero Dependencies & 100% Privacy**:
  - Pure Vanilla HTML5, CSS3, and ES6+ JavaScript with zero external runtime dependencies.
  - No trackers, no cookies, no analytics — all session data stays strictly on the client machine.

---

## 🎯 Aim Trainer Mode (10% - 25%)

When setting the arena size slider to **10% or 25%**:
1. The playfield transitions from a wide container into a **perfectly rounded target sphere**.
2. When **Random Position** is checked, the sphere relocates to random coordinates within the bounding surface.
3. Ideal for pre-match warmups in competitive FPS titles (*CS2, Valorant, Apex Legends, Overwatch 2, osu!*).

---

## 🛠️ Technical Architecture & Latency Optimizations

| Common Web Test Pitfall | Implemented Solution in this Engine |
| :--- | :--- |
| **Mechanical Switch Release Delay** (`click` fires upon mouse button release) | Listens directly to `pointerdown` / `touchstart` for instant trigger upon physical contact |
| **V-Sync Desynchronization** (timer starts before the green frame physically displays) | Synchronized with `requestAnimationFrame` to start timing precisely when pixels reach the frame buffer |
| **Coarse Clock Resolution** (`Date.now()` steps in ~15ms intervals on Windows) | `performance.now()` provides timestamps with microsecond granularity (down to **0.005 ms**) |
| **Mobile Double-Tap Delay** (browsers wait 300ms to detect double-tap zoom) | `touch-action: manipulation` and non-scalable viewport meta directives |

---

## 🚀 Getting Started / Local Run

No Node.js, package managers, or build steps are required.

### Method 1: Direct File Execution
Double-click `index.html` or open it in any modern browser (Google Chrome, Mozilla Firefox, Microsoft Edge, Safari, Brave).

### Method 2: Local Static Server (Optional)
If you prefer serving over HTTP:

```bash
# Using Python 3
python -m http.server 8080

# Or using Node.js
npx serve .
```
Then visit `http://localhost:8080` in your browser.

---

## 🎮 Controls & Usage

- **Mouse**: Left Click anywhere on the arena (or directly on the target circle in Aim mode).
- **Keyboard**: Press `Spacebar` to start and trigger reactions.
- **Touch Screen**: Direct single-tap anywhere on the screen.
- **F11 / Fullscreen Button**: Toggle fullscreen mode to eliminate browser chrome and maximize focus.

---

## 📂 Project Structure

```text
ReactionTest/
├── index.html            # Core standalone application (HTML5, CSS3, ES6+ JS)
├── README.md             # Project documentation and specifications
└── .gitignore            # Git ignore configuration for local artifacts
```

---

## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

<div align="center">
  <sub>Engineered for maximum responsiveness, visual clarity, and sub-millisecond precision.</sub>
</div>
