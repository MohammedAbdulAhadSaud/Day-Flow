# DayFlow

> A simple habit and routine tracker to help you stay consistent.

DayFlow is a small personal productivity app built around a simple idea: keep track of the things you want to do every day and see how consistent you are over time.

I wanted something simple enough to open, check my tasks, and move on with the day without having to deal with a complicated productivity system.

## ✨ What it does

DayFlow lets you create daily routines, track your progress, and look back at your consistency.

### 📅 Calendar

View your progress across the month and quickly move between different dates.

Each day gives you a quick overview of how much of your routine was completed.

### Daily tasks

Create your own tasks and organize them into categories such as:

* Exercise
* Study
* Health
* Personal

You can customize the tasks based on your own routine.

### 📊 Insights

DayFlow keeps track of your activity so you can see how you're doing over time.

You can see things like:

* Daily completion
* Weekly progress
* Current streak
* Longest streak
* Category-based progress

Nothing too complicated — just enough to get a quick idea of how consistent you've been.

### ⚙️ Customization

Create and manage your own categories and tasks so the app fits your routine instead of forcing you into a predefined system.

### 🔒 Local-first

Your data is stored locally in your browser using `localStorage`.

There is no account, backend, or database required to use the app.

This also means your personal habit data stays on your device rather than being sent to a server.

## 🚀 Progressive Web App

DayFlow is built as a Progressive Web App (PWA), so it can be installed and used more like a regular app.

It includes:

* Installable app support
* Web app manifest
* App icons
* Standalone display mode
* Service worker
* Offline caching

## 🛠️ Built with

The project keeps things fairly simple:

* React 18
* ReactDOM
* JavaScript
* HTML
* CSS
* Service Workers
* Web Storage API

There is no backend or complicated build setup. The project is intentionally lightweight and easy to explore.

## 🚀 Running locally

Since DayFlow uses a service worker, it should be served through a local web server rather than opened directly from `index.html`.

If you have Python installed, you can run:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

You can also use any other local static web server.

## 📂 Project structure

```text
dayflow-site/
├── index.html        # Main application
├── manifest.json     # PWA configuration
├── sw.js             # Service worker / offline caching
└── img/
    ├── icon-192.png  # App icon
    └── icon-512.png  # App icon
```

The main application currently lives in `index.html`, which keeps the project straightforward and easy to experiment with.

## 💾 Data and privacy

DayFlow does not require an account or external database.

Your tasks, routines, and completion history are stored locally in your browser using `localStorage`.

Because of this, clearing your browser's site data may also remove your DayFlow data.

## 🎯 Why I built it

I wanted a habit tracker that didn't feel like another complicated productivity tool.

The idea behind DayFlow is pretty simple:

**Open it. See what needs to be done. Mark things off. Keep going.**

The goal isn't to track every part of your life. It's just to make it a little easier to build a routine and stick with it.

## 🔮 Possible future improvements

Some things I may add in the future:

* Cloud sync
* Backup and restore
* More detailed analytics
* Custom themes
* Drag-and-drop task ordering
* Recurring tasks
* Improved desktop support
* More PWA features

## 🤝 Contributing

If you'd like to experiment with the project, feel free to fork it and make your own changes.

Suggestions, improvements, and bug fixes are welcome.

## 📄 License

This project does not currently have a license.

If you plan to make the repository open source, consider adding a license such as the MIT License.

---

**DayFlow** — keep it simple, stay consistent.
