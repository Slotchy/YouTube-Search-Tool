# 📺 YouTube Search Tool

A web-based tool to search YouTube videos and livestreams in **true chronological order** using your own YouTube API key. No sign-in required — just paste your key and search.

---

## ✨ Features

- 🔍 Search **videos or livestreams** sorted by most recent first
- 📅 **Filter by date** — pick a single day or a custom date range using an interactive calendar
- 🕐 **Hour filter** — narrow results to a specific time window within a selected date (auto-converts your local timezone to UTC)
- 🚫 **Filter Out Shorts** — hides videos 60 seconds or under from your results
- 🎨 **8 color themes** — Purple, Cyan, Emerald, Rose, Amber, Blue, Pink, and Lime via a swatch panel
- 💾 **API key and color theme saved** in your browser automatically
- ✨ Animated particle background, pre-filled on load
- 🕒 Shows **time ago** for each result
- 🖱️ Click any result to open the video directly

> **Note:** Livestreams mode is disabled when date filtering is active.

---

## 🔑 How to Get a YouTube API Key

1. Go to [console.cloud.google.com](https://console.cloud.google.com)
2. Create a new project or select an existing one
3. Enable **YouTube Data API v3**
4. Navigate to **Credentials** → **Create Credentials** → **API Key**
5. Copy your API key and paste it into the tool

> **Quota:** The free tier provides **10,000 units/day**. Each search costs ~100 units (~100 searches/day for free). Enabling **Filter Out Shorts** uses an additional API call to check video durations (~1 extra unit per video).

---

## 🚀 Usage

1. Paste your **YouTube API key** — it saves automatically for future visits
2. Choose **Videos** or **Livestreams**
3. Type your **search topic**
4. *(Optional)* Check **Filter Out Shorts** to exclude videos ≤ 60 seconds
5. *(Optional)* Toggle **Filter by Date** and select a day or date range on the calendar
6. *(Optional)* If a date is selected, set a **Start** and **End** hour to filter by time of day
7. Click **Find Most Recent** (or **Search** when date filtering is on)
8. Click any result card to open the video
9. Use the **color swatches** on the right to change the accent theme — remembered between visits

---

## 🔒 Privacy

- **API key** stored locally in your browser (`localStorage`) — never sent anywhere except to Google
- **Color theme preference** stored locally in your browser
- **No backend** — all processing happens client-side
- The only external requests made are to the **Google YouTube Data API v3**

---

## 🛠️ Technical Details

| Detail | Info |
|---|---|
| Stack | Pure HTML, CSS, JavaScript — no frameworks |
| Backend | None — fully client-side |
| API | YouTube Data API v3 |
| Results | Up to 50, sorted by date |
| Date filtering | Uses `publishedAfter` / `publishedBefore` API parameters |
| Shorts filtering | Second API call fetches `contentDetails` (duration), filters client-side for ≤ 60s |
| Theming | CSS custom properties (`var(--accent)`) swapped via JavaScript |
| Particles | Negative `animation-delay` values so particles pre-populate the screen on load |
| Storage | `localStorage` for API key and theme preference |
