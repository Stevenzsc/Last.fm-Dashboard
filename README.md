# Last.fm Dashboard

A dark-themed, browser-based Last.fm dashboard with recent scrobbles, top charts, local cache backup utilities, and a smooth Bar Chart Race visualization for artist listening history.

## Features

- Recent scrobble history with track, artist, album, timestamp, and artwork.
- Top Artists, Top Tracks, and Top Albums dashboard sections.
- YouTube-style Bar Chart Race with smooth ranking transitions, year filters, and cached artwork.
- Local IndexedDB cache for scrobble history and artwork blobs.
- Incremental scrobble sync after the first cache load.
- Offline cache backup and restore with local `jszip.min.js`.
- Dark theme UI with modern scrollbars, progress bars, and loading states.

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
- Use **Settings** to export or import scrobble cache and image cache ZIP backups.

## Local Cache

The dashboard stores data in the browser with IndexedDB:

- Scrobble history is cached locally to avoid refetching everything every time.
- Artwork is stored as binary Blob data instead of Base64 to reduce memory and storage overhead.
- Cache exports are compressed into ZIP files fully offline with local JSZip.

## Notes

- This is a static frontend app. No backend server is required.
- Browser storage is local to the browser/profile you use.
- If you clear site data, IndexedDB cache and saved credentials will be removed.
