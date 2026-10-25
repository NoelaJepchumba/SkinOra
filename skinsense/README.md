# SkinOra AI

Mobile-style web app: sign up, scan with the camera (or upload), get regional product and clinic recommendations, a daily routine with streaks, saved products and scan history.

## Run
    npm install
    cp .env.example .env      # optional: YouCam key; empty = demo mode
    npm run dev               # http://localhost:5173

## Notes
- Camera needs HTTPS or localhost. On a phone over Wi-Fi, use Upload (it can still open the phone camera), or deploy / use a tunnel (e.g. `npx localtunnel --port 5173`).
- Auth and history are DEMO storage in `src/lib/store.jsx` (browser only, passwords not secure). Replace signUp/signIn/signOut/update with Firebase Auth + Firestore before real users.
- YouCam: implemented in `server/youcam.js` (register file, upload, create task, poll). Put your key in `.env` as `YOUCAM_API_KEY`; no key = demo mode. YouCam scores are healthier-is-higher, so they are flipped to concern scores; set `YOUCAM_SCORE_IS_SEVERITY=1` if live results look upside down.
- Products and clinics in `src/data/regions.js` are samples. Verify clinics (KMPDC for Kenya) before marking `verified: true`.
- UV index comes from Open-Meteo (free, no key).

## Features added
Skin-tone tips, ingredient checker, before/after compare, price alerts (simulated feed in `src/lib/prices.js`), clinic booking requests via WhatsApp, English/Kiswahili (`src/lib/i18n.js`; have a native speaker review), routine reminders (while app is open), and a shareable progress card.

## Face profile (YouCam AI Face Attributes & Ratio Analyzer)
Runs once per user on their first scan (or after "Retake face profile"), alongside skin analysis. It requests 14 attributes and 10 ratios (30 units); trim them with `YOUCAM_FACE_ATTRS` / `YOUCAM_FACE_RATIOS`. Gender is deliberately not requested. The server tries a flat request body first, then the documented nested one (`YOUCAM_FACE_BODY=nested` flips the order). Reference ratios are shown as a starting point, never as a beauty score.

## Hackathon journey (demo order)
1. Scan (camera or upload) -> Smart Skin Report: plain-language summary, per-area explanations, next steps, share.
2. Routine tab: tell us your concerns, add a product you already use, and see warnings before it joins the routine. Daily checklist.
3. Skin progress: dated scans, side-by-side compare, trend chart, weekly summary (never claims the routine caused a change).
4. Clinic care: share a summary, save appointments, add to calendar, record visits and follow-ups.

Logic notes: explanations, routines and safety warnings are curated rules in `src/lib/` (insights.js, safety.js, recommend.js, report.js), not AI. YouCam supplies the analysis data. Scans, thumbnails and appointments are stored in the browser for the demo; a real release needs a backend, accounts and consent/deletion controls.
