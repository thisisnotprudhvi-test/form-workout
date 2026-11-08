# Form — personal workout log

Form is a phone-friendly, Hevy-inspired workout tracker. It is a static web app made with plain HTML, CSS, and JavaScript. There is no account or server database: routines, sessions, bodyweight, and settings live in this browser's `localStorage`.

## Project structure

```text
Workout app/
├── index.html             # App shell and navigation
├── styles.css             # Visual design and responsive layouts
├── app.js                 # App screens, workout flow, and local data
├── manifest.webmanifest   # Installable app name and launch settings
├── sw.js                  # Offline app-shell cache
├── icon.svg               # Home-screen icon
└── README.md              # This guide
```

## What it can do

- Create and edit as many routines as you need; add, reorder, and remove exercises.
- Set planned sets, rest time, exercise notes, and a video link for each movement.
- Browse a starter exercise catalog or add custom exercises.
- Start from a routine or start an empty workout.
- See the last logged performance for each movement while working out.
- Log load, reps, RPE, warm-up/drop/failure set types, and mark sets complete.
- Use a workout timer and automatic rest timer; add or remove sets and exercises during a session.
- Save session notes, bodyweight, and history; reopen a past workout to edit it.
- Review bodyweight trends, weekly training consistency, and exercise load charts.
- Download a JSON backup and restore it later.

## Run on your computer

1. Open this folder in File Explorer.
2. Click the address bar, type `powershell`, and press Enter.
3. In PowerShell, run `python -m http.server 8000`. If that command is unavailable, try `py -m http.server 8000`.
4. Keep PowerShell open and visit `http://localhost:8000` in your browser.

## Install on Android

Host the folder at an HTTPS address, open the address in Chrome on Android, then tap **⋮ → Install** or **Add to Home screen**. GitHub Pages can host the static files; see [GitHub's Pages setup](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site). A free GitHub Pages site requires a public repository. The site's code is public, but the workout data entered in the app stays in each browser on each device.

## Data, backups, and changes

The app stores data using the `form-workout-data-v2` local-storage key and migrates the earlier v1 data when it opens. Browser storage is tied to the site address and device; it does not sync between your computer and phone. Clearing the browser's site data can erase the log, so use **↧ → Download backup** regularly. Restore replaces the current browser's app data with the selected backup.

Change screen behavior and data fields in `app.js`; change colors and layout in `styles.css`. The exercise catalog is the `DEFAULT_LIBRARY` list near the top of `app.js`. If you change files cached by the service worker, increment `CACHE_NAME` in `sw.js` so the browser installs the new version.
