# Lawn HQ

A personal, weather-driven lawn care web app — no subscription required.

## Features

- **Today's Tasks** — Daily task cards generated from real live weather data (mowing, watering, fertilizer timing, pre-emergent alerts, heat stress warnings, disease scouting)
- **Mowing Schedule** — Enter your last mow date and frequency; see your full upcoming schedule with overdue alerts
- **Treatment Tracker** — Log every fertilizer, herbicide, fungicide, and aeration with product name, rate, and area
- **AI Diagnosis** — Upload a photo of a lawn problem; Claude AI identifies weeds, disease, or pests and recommends treatment
- **Annual Program** — Personalized seasonal guide based on your grass type

## Running locally

Just open `index.html` in any browser — no server, no build step, no dependencies to install.

```
open index.html         # macOS
start index.html        # Windows
xdg-open index.html     # Linux
```

## Running from GitHub Pages

1. Push this folder to a GitHub repository
2. Go to **Settings → Pages**
3. Set source to **main branch / root**
4. Your app will be live at `https://yourusername.github.io/your-repo-name`

## Running on your phone

- **GitHub Pages** (above) works great on mobile — just bookmark it on your home screen
- Or use a local server on your computer: `python3 -m http.server 8080` then visit `http://YOUR_LAN_IP:8080` from your phone

## APIs used (all free, no API key needed)

- **Open-Meteo** — 7-day weather forecast, soil temperature, evapotranspiration
- **Open-Meteo Geocoding** — Location search by city or zip
- **Anthropic Claude API** — AI photo diagnosis (uses your Claude.ai session automatically when run from claude.ai; if running locally, you will need to add your API key)

## Adding your Anthropic API key (for local use)

If running locally (not via claude.ai), add your key to the fetch call in `index.html`:

```js
headers: {
  'Content-Type': 'application/json',
  'x-api-key': 'sk-ant-YOUR_KEY_HERE',   // add this line
  'anthropic-version': '2023-06-01',
  ...
}
```

Get a key at https://console.anthropic.com

## Your data

All data (settings, treatment log, mow dates, task completions) is stored in your browser's **localStorage** — nothing is sent to any server except weather API calls and AI diagnosis requests. Use the Export button in Settings to back up your data as JSON.
