# SD Retreat MTL 2026 — More of What Matters

Countdown and info minisite for the SketchDeck HQ retreat in Montreal,
Tuesday 29 September – Friday 2 October 2026.

## Running it

It is a static site. Open `index.html`, or serve the folder:

```bash
python3 -m http.server 8000
```

## Contents

| Path | What it is |
| --- | --- |
| `index.html` | The whole site: markup, styles and scripts in one file |
| `assets/` | Photography, the Montreal drone loop and its poster, the ferris wheel and the favicon |

## Sections

Hero with live countdown, the "more of us" scroll statement, Montreal photo band,
agenda by day, downtown campus with a walking map, arrival information,
live weather, what to bring, suggestions and good to know.

## Live data

- **Weather** comes from [Open-Meteo](https://open-meteo.com) for downtown Montreal.
  Days beyond the forecast window show typical late-September conditions until they
  come into range.
- **Campus map** uses [MapLibre GL](https://maplibre.org) with an
  [OpenFreeMap](https://openfreemap.org) basemap. The walking route is the real
  588 m / 8 minute path from OpenStreetMap routing.

Both need a network connection and degrade gracefully without one.

## The Montreal band

`assets/montreal-drone.mp4` is a 12 second aerial loop over Mount Royal, encoded
to 1280x720 H.264 at roughly 10 MB. It autoplays muted and inline, and falls back
to `montreal-poster.jpg` while it loads, if autoplay is blocked, or when the
visitor prefers reduced motion. To swap the footage, re-encode to the same size
and replace both files.

## Editing

The agenda lives in the `DAYS` array near the top of the script block in
`index.html`. Each entry is `[start, end, type, title, description, optional, tbc]`
with times in Montreal local time.
