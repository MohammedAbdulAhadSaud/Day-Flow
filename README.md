# DayFlow

A clean, private, offline-friendly habit and task tracker you can install straight to your phone's home screen — no app store, no account, no backend. Your data stays on your device.

Built as a single-page web app that works as a full PWA (Progressive Web App): once installed, it looks and feels like a native app, launches full-screen, and keeps working without an internet connection.

---

## Features

- **Calendar view** — see and check off today's tasks; past days are read-only (edit history from Insights instead)
- **Tasks** — organize tasks into categories, each with its own icon
- **Per-task and per-category controls** — rename, delete (keeps history), and pin whether a task/category can be edited retroactively
- **Insights** — daily completion ring, current/longest streaks, a 7-day rhythm chart, and a category filter (like a digital-wellbeing app switcher) so you can zoom into one category's trend
- **Weekly Coverage grid** — for any category, see a heatmap of which tasks got done on which days that week
- **Safe deletion** — deleting a task keeps its history for every day before the deletion; it just stops appearing going forward
- **Backup & restore** — export/import your data as a JSON file any time from Settings
- **Fully offline after first load** — a service worker caches the app and its dependencies

---

## Tech

- Plain HTML + React (loaded via CDN, transformed in-browser with Babel Standalone) — no build step, no `npm install`
- Data persisted in the browser's `localStorage`
- PWA manifest + service worker for installability and offline support

## Files

```
├── index.html      # the entire app (UI, logic, styling)
├── manifest.json   # PWA metadata (name, icons, colors)
├── sw.js           # service worker — caches the app for offline use
├── icon-192.png    # app icon (small)
└── icon-512.png    # app icon (large)
```

---

## Deploying (GitHub Pages)

This is a static site — no server, no build process. GitHub Pages hosts it for free.

1. **Create a repository** on GitHub (keep it Public — GitHub Pages' free tier requires a public repo unless you're on GitHub Pro/Enterprise).
2. **Upload all 5 files** listed above to the repo root (drag-and-drop via "Add file → Upload files," or `git push` if you're using the CLI). They all need to sit in the same folder.
3. **Commit** the changes.
4. Go to the repo's **Settings → Pages**. Under "Build and deployment," set:
   - Source: `Deploy from a branch`
   - Branch: `main`, folder `/ (root)`
5. Save, then wait a minute or two. Refresh that Settings page — you'll see your live URL:
   `https://<your-username>.github.io/<repo-name>/`

That URL is your live app. Anyone with the link can open it, but each person's data is local to their own browser/device — nothing is shared or synced between visitors.

### Updating the app later

Edit `index.html` (or any of the other files) in the repo and commit — GitHub Pages redeploys automatically within a minute or so. If you change `index.html` or `sw.js`, bump the cache version string near the top of `sw.js` (e.g. `dayflow-cache-v14` → `v15`) so installed devices pick up the update instead of serving a stale cached copy.

---

## Installing to your phone (home screen / app drawer)

Once your GitHub Pages link is live, open it on your phone in a real browser (not a link preview or in-app browser) and add it to your home screen. This gives you a proper app icon that launches full-screen, with no browser address bar.

### iPhone (Safari)
1. Open your GitHub Pages URL in **Safari**.
2. Tap the **Share** icon (square with an arrow) in the toolbar.
3. Scroll down and tap **"Add to Home Screen."**
4. Confirm the name, tap **Add**.
5. A "DayFlow" icon appears on your home screen — tap it to launch full-screen.

### Android (Chrome)
1. Open your GitHub Pages URL in **Chrome**.
2. Tap the **⋮** menu (top-right).
3. Tap **"Install app"** (or "Add to Home screen" depending on your Chrome version).
4. Confirm — DayFlow now appears in your app drawer and home screen like any other installed app.

> If "Install app" doesn't show up, make sure you're loading the `https://` GitHub Pages link — installability requires a real secure connection, which local files or `file://` links don't satisfy.

---

## Data & privacy

- Everything (tasks, categories, completion history) is stored only in your browser's local storage on your device.
- Nothing is sent to a server — there is no backend.
- Clearing your browser's site data, uninstalling the app, or switching browsers/devices will lose your data unless you've exported a backup first (Settings → Download backup).
- Data does **not** sync between devices. If you use DayFlow on your phone and your laptop, they're two separate, independent copies.

---

## Resetting / starting over

Settings → **"Erase everything & reset"** wipes all tasks, categories, and history back to the starting defaults. This can't be undone, so back up first if you want to keep anything.
