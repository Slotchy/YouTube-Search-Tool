🌐 [Español](README.es.md) · [中文](README.zh.md) · [हिन्दी](README.hi.md) · [العربية](README.ar.md) · [Português](README.pt.md) · [Français](README.fr.md) · [日本語](README.ja.md)

# 📺 YouTube Search Tool

A web-based tool to search YouTube videos and livestreams in true chronological order using your own YouTube API key. No sign-in required — just paste your key and search.

## **YouTube Search Tool:** <https://slotchy.github.io/YouTube-Search-Tool>
## **API Key Tutorial:** <https://www.youtube.com/watch?v=eE5WGiwqlFE>

---

## ✨ Features

* 🔍 Search videos or livestreams sorted by most recent first
* 📅 Filter by date — pick a single day or a custom date range using an interactive calendar
* 🕐 Hour filter — narrow results to a specific time window within a selected date (auto-converts your local timezone to UTC)
* 🚫 Filter Out Shorts — hides videos that contain hashtags (`#`) in their title or description
* ⏱️ Video length filter — when Videos is selected, filter by Short (<4 min), Medium (4–20 min), or Long (20+ min)
* 🎨 8 color themes — Purple, Cyan, Emerald, Rose, Amber, Blue, Pink, and Lime via a swatch panel
* 💾 API key and color theme saved in your browser automatically
* ✨ Animated particle background, pre-filled on load
* 🕒 Shows time ago for each result
* 🖱️ Click any result to open the video directly
* ⭐ Favorite any video with one tap — favorites persist across sessions
* 📋 Add notes to any video — tap the Notes button on a card to expand a text area, saved automatically
* 📄 Export your full search session as a `.md` file — includes all results across every search performed, with URLs, thumbnail links, favorites, and notes, all with zero extra API quota

> **Note:** Livestreams mode is disabled when date filtering is active. Video length filter is only available in Videos mode.

---

## 🔑 How to Get a YouTube API Key

1. Open a new tab and go to [Gmail](https://mail.google.com) and sign into your Google account
2. Navigate to [console.cloud.google.com](https://console.cloud.google.com)
3. When prompted, accept the **Terms of Service** and click **Agree and Continue**
4. At the top left of the page, click **Select a Project**, then at the top right of that window click **New Project**
5. Give your project a name and click **Create** — wait for it to finish creating
6. Open the **Navigation Menu** (the three bars at the top left), scroll down to **APIs & Services**, and click **Library**
7. Scroll down until you find **YouTube Data API v3** and click on it
8. Click **Enable** and wait for it to fully activate
9. On the left-hand side, click **Credentials**
10. At the top, click **Create Credentials → API Key**, then click **Create**
11. Once your key is generated, click on the **API Key** to open its settings
12. Under **API Restrictions**, click **Restrict Key**, then click **Select APIs**
    - If YouTube Data API v3 doesn't appear right away, refresh the page
    - Scroll down, select **YouTube Data API v3**, and click **OK**
13. Click **Save**
14. Click **Show Key**, then copy your key
15. Go to the [YouTube Search Tool](https://slotchy.github.io/YouTube-Search-Tool), paste your key, and run a search to confirm it's working

> **Quota:** The free tier provides 10,000 units/day. Each search costs ~100 units (~100 searches/day for free).

---

## 🚀 Usage

1. Paste your YouTube API key — it saves automatically for future visits
2. Choose **Videos** or **Livestreams**
3. Type your search topic
4. *(Optional)* Select a **Video Length** to filter by duration (Videos mode only)
5. *(Optional)* Check **Filter Out Shorts** to exclude videos with hashtags in their title or description
6. *(Optional)* Toggle **Filter by Date** and select a day or date range on the calendar
7. *(Optional)* If a date is selected, set a **Start** and **End** hour to filter by time of day
8. Click **Find Most Recent** (or **Search** when date filtering is on)
9. Click any result card to open the video
10. *(Optional)* Click **☆ Favorite** on any card to save it as a favorite
11. *(Optional)* Click **📋 Notes** on any card to expand a notes area and type a note
12. Click **Export .MD** (floating button) to download your full session as a Markdown file
13. Use the color swatches on the right to change the accent theme — remembered between visits

---

## 📄 Export

The export button appears automatically after your first search and accumulates results across your entire session. If you search for "fortnite" and then "soccer", both sets of results are included in the download.

The `.md` file is organized as:

* **⭐ Favorites** — all videos you starred, listed first
* **📝 Notes** — all videos with notes attached
* **All Results** — every result grouped by search term, each with title, channel, publish date, URL, and thumbnail link

Favorites and notes persist in your browser across page refreshes via `localStorage`.

---

## 🔒 Privacy

* API key stored locally in your browser (`localStorage`) — never sent anywhere except to Google
* Color theme, favorites, and notes stored locally in your browser
* No backend — all processing happens client-side
* The only external requests made are to the Google YouTube Data API v3

---

## 🛠️ Technical Details

| Detail | Info |
| --- | --- |
| Stack | Pure HTML, CSS, JavaScript — no frameworks |
| Backend | None — fully client-side |
| API | YouTube Data API v3 |
| Results | Up to 50 per search, sorted by date |
| Date filtering | Uses `publishedAfter` / `publishedBefore` API parameters |
| Duration filtering | Uses `videoDuration` API parameter (`short` / `medium` / `long`) |
| Shorts filtering | Client-side — removes any result containing `#` in title or description |
| Theming | CSS custom properties (`var(--accent)`) swapped via JavaScript |
| Particles | Negative `animation-delay` values so particles pre-populate the screen on load |
| Storage | `localStorage` for API key, theme, favorites, and notes |
| Export | Client-side Blob download — no extra API calls, zero quota cost |
