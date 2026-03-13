# 💊 MediCare — Multilingual Medication Adherence App

![HTML](https://img.shields.io/badge/HTML5-Single%20File-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-Dark%20Theme-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla%20ES6-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Languages](https://img.shields.io/badge/Languages-English%20%7C%20हिंदी%20%7C%20తెలుగు%20%7C%20मराठी-brightgreen?style=flat)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)
![Deployment](https://img.shields.io/badge/Deploy-GitHub%20Pages-222?style=flat&logo=github)

A zero-dependency, single-file web application that helps elderly patients and their families track daily medication adherence — with full support for **English, Hindi (हिंदी), Telugu (తెలుగు), and Marathi (मराठी)**.

---

## 🌐 Live Demo

> **[https://YOUR_USERNAME.github.io/medicare-app/](https://YOUR_USERNAME.github.io/medicare-app/)**
>
> *(Replace `YOUR_USERNAME` with your GitHub username after deployment)*

---

## ✨ Features

### 👥 Multi-Role System
| Role | Description |
|------|-------------|
| 👴 **Patient** | Receives reminders, logs medication, tracks inventory |
| 🧑‍⚕️ **Caretaker** | Monitors patient, logs intervention calls & visits |
| 👨‍👩‍👧 **Family** | Gets escalation alerts, views live inventory |

### 🌐 Multilingual Support (v3.0)
- **4 languages** — English, हिंदी (Hindi), తెలుగు (Telugu), मराठी (Marathi)
- Language switcher bar on **every screen** — login, onboarding, all dashboards
- **99 translation keys** covering every label, button, tab, notification, and status chip
- **Regional script rendering** — Noto Sans Devanagari for Hindi/Marathi, Noto Sans Telugu for Telugu
- **Multilingual voice reminders** — spoken reminder adapts to selected language with native greeting (नमस्ते / నమస్కారం / नमस्कार / Hello)
- Correct speech synthesis language codes: `hi-IN`, `te-IN`, `mr-IN`, `en-IN`

### 🔊 Voice Reminders (v2.0)
- Web Speech API integration
- Personalised spoken reminder: name + time of day + medication name + dose
- Animated soundwave UI while speaking
- One-tap to play or stop
- Automatically triggers on notification popup open

### 🔢 Tablet Count Tracker (v2.0)
- Add total tablet count during onboarding
- Count decrements automatically when medication is marked "taken"
- Visual stock bar (green → amber → red as stock falls)
- Refill prompt — enter how many tablets were added
- Critical (≤5) / Low (≤10) / OK threshold indicators

### 📅 Expiry Date Tracking (v2.0)
- Set expiry date per medication
- Color-coded badges: ✅ OK · 🟡 Expiring soon (≤30d) · 🔴 Urgent (≤7d) · ❌ Expired
- Auto-alerts at top of patient dashboard
- Family inventory tab shows live expiry status

### 📦 Family Inventory Alerts (v2.0)
- Auto-popup when a family member logs in (if any med is low/expiring)
- Dedicated Inventory tab in Family dashboard
- Voice alert spoken on critical inventory events

### 📅 Medication Calendar
- Monthly calendar with per-day status colour coding
- Visible to patient, caretaker, and family

### 🔔 3-Phase Escalation Notifications
1. Patient notified → 15 min countdown
2. No response → Caretaker alerted
3. Caretaker can't resolve → Family alerted

---

## 🗂️ Project Structure

```
medicare-app/
├── index.html          ← Complete single-file app (HTML + CSS + JS)
├── README.md           ← This file
├── CHANGELOG.md        ← Version history
├── CONTRIBUTING.md     ← How to contribute
├── LICENSE             ← MIT License
├── .gitignore
└── .github/
    └── workflows/
        └── deploy.yml  ← Auto-deploy to GitHub Pages on push to main
```

---

## 🚀 Quick Start

### Option 1 — Run Locally
```bash
git clone https://github.com/YOUR_USERNAME/medicare-app.git
cd medicare-app
# Open index.html in any modern browser — no server needed
open index.html       # macOS
start index.html      # Windows
xdg-open index.html   # Linux
```

### Option 2 — GitHub Pages (Recommended)
1. Fork or push this repo to GitHub
2. Go to **Settings → Pages**
3. Set Source to **GitHub Actions**
4. Push to `main` — the app deploys automatically
5. Visit `https://YOUR_USERNAME.github.io/medicare-app/`

---

## 🎮 Demo Walkthrough

The app pre-fills **Ravi Kumar** with 3 medications on login for instant demo:

| Step | Action |
|------|--------|
| 1 | Open the app — **Ravi Kumar** is pre-filled |
| 2 | Select **Patient** → Continue |
| 3 | Step through onboarding (3 steps) |
| 4 | On the dashboard, click **"Trigger demo notification"** to see the full reminder + voice flow |
| 5 | Switch language using the **🌐 bar** at the top — all text updates instantly |
| 6 | Log out and try **Caretaker** or **Family** role |

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Markup | HTML5 (single file) |
| Styling | CSS3, CSS Variables, Google Fonts |
| Logic | Vanilla JavaScript ES6 |
| Fonts | DM Serif Display · DM Sans · Noto Sans Devanagari · Noto Sans Telugu |
| Speech | Web Speech API (`SpeechSynthesisUtterance`) |
| Deploy | GitHub Pages via GitHub Actions |
| Dependencies | **Zero** — no npm, no bundler, no framework |

---

## 🌍 Language Details

| Language | Script | Font | Speech Code | Greeting |
|----------|--------|------|-------------|---------|
| English | Latin | DM Sans | `en-IN` | Hello |
| हिंदी | Devanagari | Noto Sans Devanagari | `hi-IN` | नमस्ते |
| తెలుగు | Telugu | Noto Sans Telugu | `te-IN` | నమస్కారం |
| मराठी | Devanagari | Noto Sans Devanagari | `mr-IN` | नमस्कार |

---

## 🗺️ Future Scope

- [ ] SMS/WhatsApp notifications via Twilio
- [ ] Backend sync (Firebase / Supabase)
- [ ] Kannada (ಕನ್ನಡ) and Tamil (தமிழ்) language support
- [ ] Prescription upload via camera (OCR)
- [ ] Doctor portal dashboard
- [ ] PWA (installable on phone home screen)
- [ ] Dark/Light theme toggle

---

## 📄 License

MIT © 2025 — free to use, modify, and distribute.

---

> Built as part of a college project on digital health solutions for elderly care in India.
