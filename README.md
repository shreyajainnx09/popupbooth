<div align="center">

# 📸 PopUp Booth
### A browser-based photobooth that recreates the classic mall photo-strip experience

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
[![Canvas API](https://img.shields.io/badge/Canvas%20API-2d7a4f?style=for-the-badge)](https://img.shields.io/badge/Canvas%20API-2d7a4f?style=for-the-badge)
[![Play Now](https://img.shields.io/badge/🎮%20TRY%20IT%20LIVE-6C3EB8?style=for-the-badge)](https://shreyajainnx09.github.io/popupbooth/)

</div>

---

## 📌 Description

A browser-based photobooth that recreates the classic mall photo-strip experience: pick a layout and filter, snap (or upload) 4 poses, add a short caption, and get a printable/shareable photo strip.

All capture, filtering, and compositing happens locally in your browser — no photo ever touches a server.

## 🎯 Features

- **3 strip layouts** — Portrait, Landscape, Square
- **3 filters** — Color, Black & White, Vintage — applied live to the camera preview via pixel-level Canvas manipulation
- **4-shot capture flow** with a 3-second countdown timer, live thumbnails, and a retake option per shot
- **Upload-your-own-photos mode** as an alternative to live capture
- **Custom caption** (up to 25 characters), stamped onto the final strip along with the date
- **"Collect 2 Copies"** — downloads the finished strip twice, mall-booth style
- **Built-in Privacy Policy modal** detailing exactly what data is (and isn't) collected
- **No server-side photo storage** — everything is processed and composited client-side

## 🎮 Usage

1. Choose a layout (Portrait / Landscape / Square) and a filter (Color / B&W / Vintage) from the landing screen.
2. Click **Open the Booth** to launch your camera — or switch to upload mode to use existing photos instead.
3. Capture 4 shots via the countdown timer, retaking any you don't like.
4. Add an optional short caption (25 characters max).
5. Click **Collect 2 Copies** to download your finished strip.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| 🌐 HTML5 / CSS3 | Structure and styling (custom CSS variables for theming, Google Fonts: Playfair Display + Cormorant Garamond + DM Sans) |
| 🟨 JavaScript | Booth state machine, countdown timer, strip compositing, download flow |
| 🎨 Canvas API | Live filter rendering, frame capture, and final strip compositing |
| 📷 `getUserMedia` | Live front-camera capture |

## ⚙️ Setup

No build step or dependencies — it's a single static HTML file.

```bash
git clone https://github.com/shreyajainnx09/popupbooth.git
cd popupbooth
python3 -m http.server 8000
```

Then visit `http://localhost:8000` — or just use the **[live demo](https://shreyajainnx09.github.io/popupbooth/)**.

> Camera access requires serving over `http://localhost` or `https://` rather than opening `index.html` directly via `file://`.

## 🧠 How It Works

- `openBooth()` requests the front camera via `getUserMedia`, plays the video feed into a hidden `<video>` element, and triggers the curtain-opening animation before revealing the viewfinder
- `startRenderLoop()` runs a `requestAnimationFrame` loop that mirrors the video feed and pipes every frame through `drawWithFilter()`, so the selected filter previews live, not just on the final photo
- `applyGrayscale()` and `applyVintage()` operate directly on pixel data (`getImageData`/`putImageData`) — grayscale via a standard luminance-weighted average, vintage via color-channel shifting, an S-curve contrast boost, and a radial vignette
- `runTimer()` drives a 3-second countdown before each of the 4 shots; `snapFrame()` captures the current filtered frame to a still canvas, mirrored to match what the user sees
- `downloadStrip()` composites all 4 photos plus the caption and date onto a single canvas, then triggers two sequential downloads (`popupbooth-strip-1.jpg`, `darling-strip-2.jpg`) to simulate the classic "2 copies" mall booth output

## 📁 Project Structure

```
popupbooth/
│
├── index.html        → Entire app — markup, styling, and all JS logic in one file
├── background.jpeg    → Landing screen background image
└── README.md
```

## 🌟 Ideas for Extending

- Sticker/decoration overlays on the final strip
- GIF/boomerang capture mode
- Direct social-media sharing integration

## 👩🏻‍💻 Author

**Shreya Jain**
BCA | Data Analytics | Python | SQL | Tableau
