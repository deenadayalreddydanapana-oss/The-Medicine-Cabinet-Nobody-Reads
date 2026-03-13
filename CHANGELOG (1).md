# Changelog

All notable changes to MediCare are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [3.0.0] — 2025

### Added — Multilingual Support
- 🌐 **4-language support**: English, हिंदी (Hindi), తెలుగు (Telugu), मराठी (Marathi)
- Language switcher bar on every screen — login, onboarding, patient dashboard, caretaker dashboard, family dashboard
- Switching language on any screen syncs all bars app-wide
- **99-key translation dictionary** covering all UI strings: labels, buttons, tabs, card titles, dropdown options, notification text, status chips, empty states
- **Noto Sans Devanagari** font for Hindi and Marathi (Google Fonts)
- **Noto Sans Telugu** font for Telugu (Google Fonts)
- Multilingual **voice reminders** — spoken alert uses selected language + correct speech synthesis locale (`hi-IN`, `te-IN`, `mr-IN`, `en-IN`)
- Native language greetings in voice: नमस्ते (Hindi), నమస్కారం (Telugu), नमस्कार (Marathi)
- Time-of-day greetings localised (सुबह/दोपहर/शाम, ఉదయం/మధ్యాహ్నం/సాయంత్రం, सकाळ/दुपार/संध्याकाळ)
- All dynamically rendered elements (schedule chips, inventory labels, log empty states) update on language switch
- `data-i18n` attribute system — 104 attributed HTML elements
- `t(key)` helper function for runtime-rendered content
- Meal dropdown options translated in all 4 languages

### Changed
- `speakReminder()` now uses `getVoiceMessage()` and `getVoiceLang()` helpers
- `renderTodaySchedule()`, `refreshCTSchedule()`, `refreshFamSchedule()` use `t()` for status labels
- `renderInventoryCard()`, `renderFamInventory()` use `t()` for "Tablets left" / "Full pack"
- `renderCTLog()`, `renderFamLog()` use `t()` for empty state
- `showLogout()` preserves `currentLang` across sessions
- Login screen layout updated to accommodate lang bar above the login box

---

## [2.0.0] — 2025

### Added — Voice Reminders
- 🔊 Web Speech API integration (`SpeechSynthesisUtterance`)
- Personalised reminder message: patient name + time of day + medication details
- Animated soundwave visualisation while speaking
- Tap-to-stop functionality
- Auto-speaks 600ms after notification popup opens
- Voice triggers inventory alerts for family role

### Added — Tablet Count Tracker
- Total tablet count field in medication onboarding form
- Auto-decrement on "taken" confirmation
- Visual stock bar (colour-coded: green/amber/red)
- Refill prompt — patient can log new tablets added
- Critical (≤5) / Low (≤10) / OK thresholds
- Inventory alert banners on patient dashboard

### Added — Expiry Date Tracking
- Expiry date (month picker) per medication
- Colour-coded expiry badges: OK / Soon (≤30d) / Urgent (≤7d) / Expired
- Expiry alerts in patient dashboard top banner
- Family inventory tab shows live expiry status

### Added — Family Inventory Alerts
- Auto-popup on family login if any medication is critically low or near expiry
- Dedicated "Inventory" tab in Family dashboard
- Voice alert on critical inventory events

---

## [1.0.0] — 2025

### Added — MVP
- Multi-role login: Patient, Caretaker, Family
- 3-step patient onboarding (health info → medications → schedule timings)
- Today's medication schedule with status tracking
- Monthly calendar (taken / missed / refused)
- 3-phase escalation notifications: Patient → Caretaker → Family
- Action log for caretaker and family interventions
- Demo seed data (Ravi Kumar, 3 medications)
- GitHub Pages auto-deployment via GitHub Actions
