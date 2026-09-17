# SD Retreat MTL 2026 — More of What Matters

Countdown and info minisite for the SketchDeck HQ retreat in Montreal,
Tuesday 29 September – Friday 2 October 2026.

## Source of truth

`index.html` **is** the site. It is hand-edited and authoritative: no build step,
no template, nothing to compile. Edit it directly, commit, and Vercel publishes to
<https://2026-retreat-tan.vercel.app> within about a minute.

## Running it

It is a static site. Open `index.html`, or serve the folder:

```bash
python3 -m http.server 8000
```

## Contents

| Path | What it is |
| --- | --- |
| `index.html` | The whole site: markup, styles and scripts in one file |
| `assets/` | Photography, the Montreal drone loop and its poster, the four MTL stamps and the favicon |

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

`index.html` is the only file to touch. It is one self-contained document —
markup, styles and scripts together — so a change is: edit, commit, done.

**Without cloning anything.** Open the repo on GitHub and press <kbd>.</kbd>; a full
editor opens in the browser. Edit `index.html`, commit to `main`, and the live site
updates in about a minute.

**With git.**

```bash
git clone https://github.com/gustavopanichi/2026Retreat.git
cd 2026Retreat
python3 -m http.server 8000   # then open http://localhost:8000
```

Every push to `main` deploys straight to the live URL. There is no staging step and
no review gate, so preview locally before you push.

### The agenda

The agenda is the `DAYS` array near the top of the script block. Each entry is
`[start, end, type, title, description, optional, tbc]`, times in Montreal local
time; the last two flags can be omitted. `optional` draws the dashed outline,
`tbc` adds the TBC badge.
