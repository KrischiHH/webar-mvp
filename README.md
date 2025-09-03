# WebAR MVP (Cost-neutral, Image-Tracking)

This is a tiny starter you can host for free (e.g. GitHub Pages). It uses **MindAR (A‑Frame build)** for **image tracking** and a **fallback** 3D viewer if AR is not available.

## Files
- `index.html` — AR page (image tracking with MindAR/A‑Frame).
- `fallback.html` — Non‑AR 3D viewer using `<model-viewer>`.
- `share.html` — Generates a QR code for your AR link.
- `assets/model.glb` — Put your GLB here (replace the placeholder path in `index.html`).
- `targets/targets.mind` — Put your MindAR target file here (generated from your marker image).
- `targets/target.png` — (optional) The original marker image for preview in the scene.

## Quick start (no coding)
1) **Test immediately** using built‑in demo assets:
   - Open `index.html` (served via a web server — see below) on your phone.
   - Point the camera at the sample image shown here:  
     https://cdn.jsdelivr.net/gh/hiukim/mind-ar-js@1.2.5/examples/image-tracking/assets/card-example/card.png
   - You should see a plane and a small animated model appear on top.

2) **Create your own marker** (`targets/targets.mind`):
   - Use the online **MindAR Image Targets Compiler** (upload your image → download `.mind`):  
     https://hiukim.github.io/mind-ar-js-doc/tools/compile/
   - (Tip) Prefer images with strong features/contrast. See guidelines: https://www.mindar.org/how-to-choose-a-good-target-image-for-tracking-in-ar-part-1/

3) **Swap to your own assets**:
   - Put your `.mind` file in `targets/targets.mind` and your original image as `targets/target.png` (optional).
   - Put your GLB model in `assets/model.glb`.
   - In `index.html`, change the paths in the `<a-scene>` and asset tags (they’re commented clearly).

4) **Fallback 3D viewer**:
   - If AR doesn’t run on a device, open `fallback.html` to show the model in a standard 3D viewer.

5) **Host for free**:
   - Push this folder to a GitHub repo and enable **GitHub Pages** (Project/Docs site).  
     Docs: https://pages.github.com/
   - Your AR will be available at `https://<username>.github.io/<repo>/index.html` (use this in `share.html` for the QR).

## Notes on device support
- **Image tracking** via MindAR works on **iOS Safari** and **Android Chrome** (camera permission required).
- **Surface (world) placement** using **WebXR Hit‑Test** is supported on **Chrome for Android** but **not** on iOS Safari as of now. For iOS users, prefer **image targets**. (See: https://caniuse.com/webxr)

Enjoy! :)
