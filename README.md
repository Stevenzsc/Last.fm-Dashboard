# Last.fm Dashboard

A dark-themed, browser-based Last.fm dashboard with recent scrobbles, top charts, local cache backup utilities, a smooth Bar Chart Race visualization, and deep listening analytics for artist obsession patterns.

## Features

- Recent scrobble history with track, artist, album, timestamp, and artwork.
- Top Artists, Top Tracks, and Top Albums dashboard sections.
- YouTube-style Bar Chart Race with smooth ranking transitions, year filters, and cached artwork.
- Listening Obsessions analytics with top streaks, heavy rotation detection, monthly heat bars, and compact artist image tiles.
- Cinematic Heavy Rotation playback with preloaded local artwork and heartbeat-style animation.
- Local IndexedDB cache for scrobble history and artwork blobs.
- Incremental scrobble sync after the first cache load.
- Offline cache backup and restore with local `jszip.min.js`.
- Dark theme UI with modern scrollbars, progress bars, loading states, and isolated horizontal archive rails.

## Files

- `index.html` - Main dashboard app.
- `jszip.min.js` - Local JSZip library used for offline ZIP export/import.
- `README.md` - Project notes.

## Setup

1. Clone or download this repository.
2. Make sure `jszip.min.js` is in the same folder as `index.html`.
3. Open `index.html` in a browser.
4. Enter your Last.fm API key and username when prompted.

You can create a Last.fm API key here:

https://www.last.fm/api/account/create

## Usage

- Use **Recent History & Charts** to view recent scrobbles and top listening stats.
- Use **Bar Chart Race** to animate artist rankings over time.
- Use the year tabs under **Bar Chart Race** to switch between `All-Time` and individual years.
- Use **Listening Obsessions** to review all-time top streaks and heavy rotation events grouped by year.
- Click monthly heat blocks to jump the matching year's horizontal archive rail to that month.
- Use **Play Cinematic** to watch a visual playback of peak heavy-rotation moments.
- Use **Settings** to export or import scrobble cache and image cache ZIP backups.

## Local Cache

The dashboard stores data in the browser with IndexedDB:

- Scrobble history is cached locally to avoid refetching everything every time.
- Artwork is stored as binary Blob data instead of Base64 to reduce memory and storage overhead.
- Heavy Rotation tiles hydrate artwork from local track images first, then fall back to cached artist or album artwork.
- Cache exports are compressed into ZIP files fully offline with local JSZip.

## Release Notes

### v1.1

- Added **Listening Obsessions** with streak detection and heavy rotation analytics.
- Added compact Heavy Rotation Archive year rails with monthly heat-bar navigation.
- Added artist image tiles with local IndexedDB artwork hydration.
- Added **Play Cinematic** mode with preloaded images and heartbeat animation.
- Improved Bar Chart Race with daily timeline aggregation and a 10x speed option.
- Added local ZIP export/import for scrobble and image cache backups.
- Improved IndexedDB image caching with Blob storage and safer object URL handling.
- Modernized progress indicators, loading states, and dark scrollbars.
- Fixed Recent Scrobbles artist display, stale blob image errors, and tab-switch animation cleanup.
- Improved horizontal and vertical scrolling isolation across the dashboard.

## Notes

- This is a static frontend app. No backend server is required.
- Browser storage is local to the browser/profile you use.
- If you clear site data, IndexedDB cache and saved credentials will be removed.
