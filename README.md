# Calorie Ledger

A calorie and macro tracker that works like an expense app. You get a daily calorie **budget**; food is **spending**, exercise is **income**, and the big number is what you have **left**.

It's a single-page web app you can install on your iPhone's home screen. It works offline, and your data stays on your device.

## Features

- **Daily budget**: calories left, food minus exercise, and a progress bar
- **Macros**: protein, carbs and fat per entry, with daily targets
- **Meals as categories**: Breakfast, Lunch, Dinner, Snack, Drink
- **Quick add** for common foods and workouts, and autocomplete from your history
- **Photo estimates** (optional, uses your Gemini API key): snap a meal and get calories and macros for each item
- **Garmin screenshots**: screenshot a workout in Garmin Connect and the app reads the calories off it
- **80% exercise setting**: counts only 80% of watch calories, since watches tend to overestimate
- **History**: day-by-day navigation, breakdown by meal, last-7-days chart
- **Budget calculator**: Mifflin–St Jeor estimate of calories burned per day, plus macro targets (protein 1.8 g/kg, fat 0.9 g/kg, the rest from carbs)
- **Backup**: export and restore your data as a JSON file

## Install on iPhone

1. Open the GitHub Pages link in **Safari**.
2. Tap **Share → Add to Home Screen**.
3. Open it from the home screen icon. It runs full-screen, like an app.

## Turn on photo estimates (optional)

1. Get a Gemini API key at [Google AI Studio](https://aistudio.google.com/apikey).
2. In the app, scroll to **Photo estimates (Gemini)**, paste the key and tap **Save**.

The key is saved only in your browser on this device and is sent only to Google's Gemini API. It's never stored in this repository. The default model is `gemini-3.5-flash-lite`, and you can change it in Settings.

## Your data

Everything is stored in your browser's local storage on this device. Nothing syncs between devices. **Clearing Safari's website data erases your log**, so use **Export backup** now and then.

## Run locally

It's plain HTML with no build step:

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app: markup, styles and script |
| `manifest.json` | Lets the browser install it as an app (name, icon, colors) |
| `sw.js` | Service worker that caches the app so it works offline |
| `icons/` | Home screen and app icons |

Calorie numbers for quick-add items and AI estimates are rough. This app is not medical advice.
