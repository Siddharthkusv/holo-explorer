# Holo-Explorer 🛰️

**🌐 Live demo:** https://siddharthkusv.github.io/holo-explorer/

A browser-based hand-tracking hologram console inspired by sci-fi interfaces (think Iron Man's JARVIS). Point your webcam at your hand and control glowing holograms with natural gestures — no installs, no backend, everything runs on-device in your browser.

## ✨ Modes

### HOLO FX — gesture effects
- **Real-time AI hand tracking** — 21 hand landmarks detected live via MediaPipe
- **Arc reactor** — blooms in your open palm, scales with your hand
- **Energy orb** — pinch to grab it, release to throw it with physics + motion trail
- **Fist explosion** — clench your fist to trigger a particle blast
- **Energy beam** — open both palms to fire a beam between them
- **Touch / mouse mode** — full experience without a camera (drag = palm, hold = pinch, double-tap = blast)
- **Sci-fi HUD** — scanlines, corner brackets, FPS meter, live status readouts
- **Synth sound effects** — generated live with WebAudio, mutable

### 🔧 WORKSHOP — Iron-Man builder
Assemble a working arc reactor part-by-part, Tony Stark style. Press **WORKSHOP** (top-right) to enter the lab:
- **6 holographic components** scattered around: **CORE**, **COIL · L**, **COIL · R**, **INNER RING**, **OUTER RING**, **CAP**
- **Pinch (or press & hold)** a component to grab it, **drag** it to the glowing assembly pedestal, **release** to lock it — ghost outlines show where each part belongs
- Wrong drops are rejected — the part simply stays where you left it
- Live progress readout: `ASSEMBLY 3 / 6`
- Lock all 6 → **ARC REACTOR ONLINE** — full assembly sequence with flash burst, particles and fanfare
- **RESET** scatters the parts so you can build again

## 🎮 Gestures

| Gesture | HOLO FX | WORKSHOP |
|---|---|---|
| 🖐️ Open palm | Arc reactor in palm | — |
| 🤏 Pinch (thumb + index) | Grab energy orb, release to throw | Grab component |
| ✊ Fist | Particle explosion | — |
| 🖐️🖐️ Two open palms | Energy beam | — |
| ☝️ Point | Focus ring | — |
| 🖱️ Drag / hold / double-tap | Mouse-touch equivalents | Grab / move / — |

## 🚀 How to use

### Camera mode (recommended)
1. Open the live link in **Chrome** (desktop or Android)
2. Click **ENABLE CAMERA** → **Allow** when asked
3. Show your palm to the camera and try the gestures above
4. Press **WORKSHOP** (top-right) for the arc-reactor builder

> ⚠️ Camera needs a secure (HTTPS) page. The hosted link above works. Opening the raw HTML file from a file manager / WhatsApp viewer (`content://`) blocks the camera — always use the hosted link.

### Touch / mouse mode (no camera needed)
Click **USE TOUCH DEMO** (or **USE MOUSE DEMO** on desktop):
- **Drag** → move palm / pointer
- **Press & hold** → pinch / grab component
- **Double-tap** (or right-click / Space on desktop) → explosion

## 🛠️ How it works

1. **Webcam** captures live video
2. **MediaPipe HandLandmarker** (Google's ML model, loaded from CDN) detects 21 hand landmarks per frame — on-device
3. **Gesture engine** classifies each hand from landmark geometry (open palm / fist / pinch / point)
4. **Canvas renderer** draws glow holograms anchored to the landmarks every frame
5. **Workshop physics** — grab uses distance checks + eased dragging; snap uses per-part slot targets with a snap radius; wrong drops are rejected
6. **WebAudio** synthesizes matching sound effects in real time

No video ever leaves your device — tracking runs 100% locally in the browser.

## 🧱 Tech stack

- Single self-contained `index.html` (zero build step)
- [MediaPipe Tasks Vision](https://ai.google.dev/edge/mediapipe/) (`@0.10.14`) — hand tracking
- HTML5 Canvas — hologram rendering
- WebAudio API — synthesized SFX
- Hosted on GitHub Pages

## 📄 License

MIT — feel free to fork and build on it.
