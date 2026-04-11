# Golf Globe ⛳

An interactive 3D globe showing your golf round history.

## How to open

Double-click `index.html` to open it in Chrome (or drag it into a Chrome tab).

No server needed — everything loads from CDN and local files.

## Controls

| Action | How |
|---|---|
| Rotate globe | Click + drag |
| Zoom | Scroll wheel / pinch |
| Click a pin | Shows all rounds at that course |
| Close popup | Click ✕ or click the globe background |

The globe auto-rotates on load and stops the moment you touch it.

## Pin colors

| Color | Meaning |
|---|---|
| 🟢 Green | Average score < 90 at that course |
| 🟡 Yellow | Average score 90–99 |
| 🔴 Red | Average score 100+ |

## Updating your data

If you fix coordinates in `location_review.csv` or add new rounds to `scores.csv`:

1. Re-open `geocode.html` in Chrome to re-run the geocoder
2. Download the new `processed_scores.json`
3. Open `data.js` in a text editor and replace the array contents

Alternatively, you can manually edit `data.js` directly — find any course entry and
change its `lat`/`lon` values, then reload `index.html`.

## Known coordinate issues to fix

These courses were geocoded to wrong locations. Edit `data.js` to fix:

| Course name in data.js | Issue | Correct coords (approx) |
|---|---|---|
| `St. Davids Golf Club` | Geocoded to Wales | `lat: 40.0440, lon: -75.3930` |
| `St Davids Golf Club` | Same issue | same as above |
| `St. Davids-Silver` | Geocoded to Canada (St. Davids, Ontario) | `lat: 40.0440, lon: -75.3930` |
| `St. Davids-Black` | Same issue | same as above |
| `Laurel Valley Golf Club` | Wrong state (NC vs PA) | `lat: 40.1887, lon: -79.2710` |
| `Turtle Creek Golf Course` | Geocoded to Michigan | `lat: 40.2233, lon: -75.5137` |
| `Turtle Creek-Blue` | Same issue | same as above |
| `Rolling Green-White` | Geocoded to western PA | `lat: 40.1540, lon: -75.2260` |

## Files

| File | Purpose |
|---|---|
| `index.html` | The globe app |
| `data.js` | Golf data as a JS variable (edit to fix coords) |
| `scores.csv` | Original data export |
| `geocode.html` | Re-run geocoding if you update scores.csv |
| `location_review.csv` | Geocoding confidence review |
| `processed_scores.json` | Geocoded JSON (used to generate data.js) |
