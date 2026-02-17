# YouTube Search Tool

A web-based tool to search YouTube videos and livestreams in true chronological order using your own YouTube API key.

## Features
- Search videos or livestreams in chronological order (most recent first)
- Filter results by a specific date or a custom date range using an interactive calendar
- Date filtering automatically switches to Videos only — Livestreams are disabled while it is active
- API key saved in browser for convenience
- Clean, modern interface
- Shows time ago for each video
- Click any result to open the video

## How to Get a YouTube API Key
1. Go to Google Cloud Console at console.cloud.google.com
2. Create a new project or select existing
3. Enable YouTube Data API v3
4. Go to Credentials then Create Credentials then API Key
5. Copy your API key
6. Paste it into the website

Note: The free tier gives you 10,000 quota units per day. Each search uses about 100 units, so you can do about 100 searches per day for free.

## Privacy
- Your API key is stored locally in your browser
- No data is sent to any server except Google YouTube API
- All processing happens client-side in your browser

## Usage
1. Paste your YouTube API key and it will be saved for future visits
2. Choose Videos or Livestreams
3. Enter your search topic
4. Optionally toggle Filter by Date and pick a single day or a date range on the calendar
5. Click Find Most Recent, or Search when date filtering is active
6. Click any result to open the video

## Technical Details
- Pure HTML CSS JavaScript with no frameworks
- No backend required
- Uses YouTube Data API v3
- Fetches 50 most recent results sorted by date
- Date filtering uses YouTube API publishedAfter and publishedBefore parameters server-side
