# Holo-Explorer 🛰️

**🌐 Live demo:** https://siddharthkusv.github.io/holo-explorer/

A browser-based hand-tracking hologram console inspired by sci-fi interfaces (think Iron Man's JARVIS). Point your webcam at your hand and control glowing holograms with natural gestures — no installs, no backend, everything runs on-device in your browser.

## ✨ Features

- **Real-time AI hand tracking** — 21 hand landmarks detected live via MediaPipe
- **Arc reactor** — blooms in your open palm, scales with your hand
- **Energy orb** — pinch to grab it, release to throw it with physics + motion trail
- **Fist explosion** — clench your fist to trigger a particle blast
- **Energy beam** — open both palms to fire a beam between them
- **Touch / mouse mode** — full experience without a camera (drag = palm, hold = pinch, double-tap = blast)
- **Sci-fi HUD** — scanlines, corner brackets, FPS meter, live status readouts
- **Synth sound effects** — generated live with WebAudio, mutable

## 🎮 Gestures

| Gesture | Effect |
|---|---|
| 🖐️ Open palm | Arc reactor appears in palm |
| 🤏 Pinch (thumb + index) | Grab the energy orb, release to throw |
| ✊ Fist | Particle explosion |
| 🖐️🖐️ Two open palms | Energy beam between hands |
| ☝️ Point | Focus ring |

## 🚀 How to use

### Camera mode (recommended)
1. Open the live link in **Chrome** (desktop or Android)
2. Click **ENABLE CAMERA** → **Allow** when asked
3. Show your palm to the camera and try the gestures above

> ⚠️ Camera needs a secure (HTTPS) page. The hosted link above works. Opening the raw HTML file from a file manager / WhatsApp viewer (`content://`) blocks the camera — always use the hosted link.

### Touch / mouse mode (no camera needed)
Click **USE TOUCH DEMO** (or **USE MOUSE DEMO** on desktop):
- **Drag** → move palm
- **Press & hold** → pinch / grab orb
- **Double-tap** (or right-click / Space on desktop) → explosion

## 🛠️ How it works

1. **Webcam** captures live video
2. **MediaPipe HandLandmarker** (Google's ML model, loaded from CDN) detects 21 hand landmarks per frame — on-device
3. **Gesture engine** classifies each hand from landmark geometry (open palm / fist / pinch / point)
4. **Canvas renderer** draws glow holograms anchored to the landmarks every frame
5. **WebAudio** synthesizes matching sound effects in real time

No video ever leaves your device — tracking runs 100% locally in the browser.

## 🧱 Tech stack

- Single self-contained `index.html` (zero build step)
- [MediaPipe Tasks Vision](https://ai.google.dev/edge/mediapipe/) (`@0.10.14`) — hand tracking
- HTML5 Canvas — hologram rendering
- WebAudio API — synthesized SFX
- Hosted on GitHub Pages

## 📄 License

MIT — feel free to fork and build on it.
