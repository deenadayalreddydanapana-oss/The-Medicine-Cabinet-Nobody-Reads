# Contributing to MediCare

Thank you for your interest in contributing! This is an academic project, but contributions are welcome.

## Development Setup

No build tools required — it's a single HTML file.

```bash
git clone https://github.com/YOUR_USERNAME/medicare-app.git
cd medicare-app
open index.html   # or use any live-server tool
```

For live reload during development:
```bash
# Using VS Code Live Server extension, or:
npx live-server .
```

## Adding a New Language

1. Open `index.html` and locate the `TRANSLATIONS` object in the `<script>` block
2. Add a new language block following the same key structure as `en`, `hi`, `te`, or `mr`:
   ```js
   kn: {   // Kannada example
     login_sub: 'ಕುಟುಂಬಗಳಿಗಾಗಿ ನಿರ್ಮಿಸಲಾದ ಔಷಧ ಅನುಸರಣೆ ಅಪ್ಲಿಕೇಶನ್',
     full_name: 'ಪೂರ್ಣ ಹೆಸರು',
     // ... all 99 keys
   }
   ```
3. Add a language button to every `lang-bar` div across all 5 screens:
   ```html
   <button class="lang-btn" onclick="setLang('kn',this)">ಕನ್ನಡ</button>
   ```
4. Add the script font to `getVoiceLang()` mapping:
   ```js
   function getVoiceLang() {
     return { en:'en-IN', hi:'hi-IN', te:'te-IN', mr:'mr-IN', kn:'kn-IN' }[currentLang] || 'en-IN';
   }
   ```
5. Add voice message logic to `getVoiceMessage()` for the new locale
6. Add Noto Sans font import for the new script if needed (Google Fonts)
7. Update the `mealMap` in `applyLang()` with translated meal options

## Voice Reminder Notes

- The Web Speech API is browser-dependent — Chrome gives best results
- `speechSynthesis.getVoices()` is async; voices are loaded via `voiceschanged` event
- Regional Indian language voices (`hi-IN`, `te-IN`, `mr-IN`) are available in Chrome on Windows/Android
- macOS and iOS may fall back to `en-IN` — this is expected behaviour

## Pull Request Guidelines

1. Keep the app as a **single HTML file** — no build steps, no npm
2. Test in Chrome (primary), Firefox, and Safari
3. Verify all 4 language strings display correctly
4. Ensure voice reminder works in selected language (Chrome recommended)
5. Describe what you changed in the PR description

## Reporting Issues

Open a GitHub Issue with:
- Browser and OS
- Which language was selected
- Screenshot or screen recording if possible
