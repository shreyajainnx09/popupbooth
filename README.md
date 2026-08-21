# PopUp Booth

**Live demo:** https://shreyajainnx09.github.io/popupbooth/

## Description
A browser-based photobooth that recreates the classic mall photo-strip experience: pick a layout and filter, snap (or upload) 4 poses, add a short caption, and get a printable/shareable photo strip — all processed locally in the browser.

## Features
- Multiple strip layouts: Portrait, Landscape, Square
- Filters: Color, B&W, Vintage
- 4-shot capture flow with retake option per shot
- Upload-your-own-photos mode as an alternative to live capture
- Custom caption (up to 25 characters)
- "Collect 2 Copies" printing option
- No server-side photo storage — all processing happens client-side in the browser

## Privacy Model
- Photos are never uploaded to a server; everything is processed locally.
- No cookies used for tracking.
- Anonymous analytics only (no personally identifiable data).

## Tech Stack (typical — adjust to match your actual repo)
- HTML5 / CSS3 / JavaScript
- `getUserMedia` for live camera capture
- Canvas API for compositing the photo strip

## Getting Started
```bash
git clone https://github.com/shreyajainnx09/popupbooth.git
cd popupbooth
python3 -m http.server 8000
```
Visit `http://localhost:8000`.

## Usage
1. Choose a layout and filter.
2. Click "Open the Booth" (or "Upload Photos" to use existing images).
3. Capture 4 shots, retaking any you don't like.
4. Add an optional short message.
5. Finalize the strip and download/print/share.

## Roadmap Ideas
- Sticker/decoration overlays
- GIF/boomerang mode
- Direct social-media sharing integration

## Author
Shreya Jain
