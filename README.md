# RIVA CLAV Interactive Web Application

An interactive web application for **RIVA CLAV** (Amoxicillin & Clavulanic Acid), reverse-engineered from the Android APK (`RivaClav-v1.0.apk`) using **REA (Reverse Engineer Anything)** and enhanced for modern web browsers.

---

## 🔬 Reverse Engineering Findings

1. **Architecture Discovery**:
   - The original APK (`com.rivaclav.app`) was a hybrid application packaging a full HTML5 / CSS3 / Canvas interactive experience inside an Android WebView.
   - The core visual assets and logic were contained in `assets/www/`.
   - Android-native bridging (`Android.sharePoster()`) was connected to Android's `FileProvider` to share `poster-full.jpg`.

2. **Core Components**:
   - **Interactive Canvas (`#interactiveCanvas`)**: 11 bacteria sprites with dynamic physics bouncing off viewport bounds and deflecting around the central protective shield.
   - **Magnifying Lens (`lens_2.png`)**: Draggable 1.85x magnification viewer with realistic radial glass lighting reflection.
   - **Product Packaging**: 4 suspension dosages with interactive modal viewers:
     - `457 mg / 5 ml` (70 ml)
     - `312.5 mg / 5 ml` (100 ml)
     - `228.5 mg / 5 ml` (70 ml)
     - `156 mg / 5 ml` (100 ml)

3. **Web Enhancements**:
   - **Modern Typography**: Integrated Google Fonts (`Cairo` for Arabic text and `Outfit` for English dosages/subtitles).
   - **Cross-Platform Sharing**: Web Share API support with graceful fallback to an interactive Full Poster modal with direct download and copy-link buttons.
   - **Modal Carousel**: Added Prev / Next navigation buttons, touch swipe gestures, and keyboard arrow controls.
   - **Web Audio API**: Synthesized soft audio feedback (toggleable) on interactions.
   - **PWA Ready**: `manifest.json`, favicons, and meta tags for "Add to Home Screen" support.

---

## 🚀 Deployment to Vercel

### Option 1: Vercel CLI (Instant)
```bash
# In the project directory
npx vercel
```

### Option 2: GitHub / GitLab / Bitbucket
1. Push this directory to your GitHub repository.
2. Go to [vercel.com/new](https://vercel.com/new).
3. Import the repository — Vercel will automatically detect the static configuration from `vercel.json` and deploy it instantly with zero configuration!

---

## 🛠 Local Development
```bash
# Using npm
npm start

# Or using Python
python -m http.server 3000
```
Open `http://localhost:3000` in any web browser.
