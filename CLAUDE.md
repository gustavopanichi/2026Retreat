# 2026Retreat

One-page static site for the SketchDeck HQ retreat in Montreal, 29 Sep – 2 Oct 2026.
Live at <https://2026-retreat-tan.vercel.app>; every push to `main` deploys there.

## Source of truth

`index.html` is hand-edited and authoritative. There is **no build step** — no
template, no generator, no preprocessor. An earlier version of this site was
assembled from a `template.html` carrying `{{PLACEHOLDER}}` tokens; that workflow is
retired and the templates are gone.

Never regenerate `index.html` from a template or replace it wholesale. Edit it in
place. Other people edit this file directly on GitHub, so a regenerate-and-replace
would silently discard their work.

## Layout

- `index.html` — the entire site: markup, styles and scripts in one file
- `assets/` — photography, the Montreal drone loop and its poster, the four stamps,
  the flag, the Spotify mark, the favicon

## Conventions

- Type is Syne (display) and Inter (body). No other families — Geist was removed
  deliberately.
- Palette: `--moon:#161638` `--sun:#F95104` `--pink:#FFB2D5` `--off:#F4F4F0`
  `--brown:#7E5735` `--sky:#C0D8FF`. Pink is always `#FFB2D5`.
- The agenda is the `DAYS` array in the script block:
  `[start, end, type, title, description, optional, tbc]`, Montreal local time.
- Weather (Open-Meteo) and the campus map (MapLibre + OpenFreeMap) are keyless and
  must degrade gracefully offline.
- There is no staging environment. Verify in a browser before pushing.
