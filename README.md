# Swiftia — Web Sim

Swiftia is a **web-based simulation** of a iOS-style jailbreak experience called "SwiftSword". It is pure entertainment — it does **not** modify, exploit, or jailbreak any real device, and it installs no real configuration profiles. Everything lives inside the browser page:

- "Install Swiftia" shows visual install steps (profile card + Add to Home Screen instructions). Nothing is installed silently — you tap through each step yourself.
- Tapping the home screen shortcut opens the app as a full-screen web clip (Add to Home Screen in Safari).
- "Jailbreak" streams console-style log lines with a fading animation, then shows a respring overlay, then switches the button to "Jailbroken" with an unlocked lock icon.
- **Sileo** sheet: add the bundled sources, browse/search packages, queue multiple items — queued packages are applied the next time you reopen the page.
  - `themes.repo/` — 10 gradient themes (installable, apply from the main page, default is Monochrome black/white)
  - `procurus.net/` — 2 tweaks:
    - **Gravitation** — asks for motion access; shake the device twice up-and-down to let the UI fall into gravity based on your rotation, shake twice again to release.
    - **Editor** — hold the top-right corner for ~1 s to activate; a notification appears and every element on the main page becomes draggable; hold the corner again to release. Positions are remembered.
- "Jailbroken" state, themes, tweaks and element positions are saved in `localStorage`, so reopening the bookmark restores everything.
- "Remove Jailbreak" resets everything back to stock.
- Remove Jailbreak and Sileo buttons are hidden until the jailbreak has been completed.

> Reminder: this is a simulation for fun — no system-level changes are ever made.

## Deploy to Render (via GitHub)

1. Push this folder to a GitHub repository:
   ```bash
   cd SwiftiaWebsite
   git init
   git add .
   git commit -m "Swiftia site"
   git remote add origin https://github.com/YOUR_NAME/swiftia.git
   git push -u origin main
   ```
2. Go to [render.com](https://render.com) → **New +** → **Static Site**.
3. Connect your GitHub repo.
4. If the settings screen appears, use:
   - **Root directory:** leave empty (or `SwiftiaWebsite` if you pushed the repo with this folder inside another project)
   - **Build command:** *none*
   - **Publish directory:** `.` (or leave blank — `render.yaml` in this folder also configures it automatically)
5. Click **Create Static Site**. Render gives you a URL like `https://swiftia-xxxx.onrender.com`.
6. On your iPhone, open that URL in Safari → Share → **Add to Home Screen** → name it **Swiftia**.

## Files

- `index.html` — the entire app (no external dependencies, works offline after first load)
- `render.yaml` — Render static site config
- `assets/icon.png` — white triangle on black background (app/home screen icon)
