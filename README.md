# Pi Trailblazer

A single-page memory-training game for reciting the first 100 decimal digits of π.

## What it is

Type the digits of π from memory, one at a time, and watch a winding trail climb toward a
"summit" at digit 100. Two modes:

- **Learn** — the upcoming digits stay visible (dimmed) while you type, for rehearsal.
  Mistakes just shake and let you retry; they never reset the walk.
- **Recall** — digits are hidden. You must recall each one before typing it. A wrong digit
  reveals the correct one and restarts the walk from digit 1. A live timer tracks the walk,
  and reaching digit 100 records a completion and (if it's faster) a new best time.

Progress is drawn as an SVG trail: orange marks the current walk, green marks the
furthest you've ever reached (your personal record), with checkpoints every 10 digits
up to the summit. Your personal best distance and best completion time are saved in the
browser's `localStorage`, so they persist between visits on the same device/browser.

## Files

- `index.html` — the entire app (HTML, CSS and JavaScript in one file, no build step,
  no dependencies other than Google Fonts loaded via `<link>`).

## Running it locally

No build tools or server required — just open `index.html` in any modern browser:

```bash
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Or serve it locally if you prefer:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/
```

## Customizing

- The 100 digits are hardcoded as `PI_DIGITS` near the top of the `<script>` block —
  swap in a different constant's digits to repurpose the app.
- Digit grouping in the readout (currently pairs of two) is controlled by the modulus
  check in `renderReadout()` (`(i+1) % 2 === 0`).
- Colors and fonts are defined as CSS custom properties at the top of the `<style>`
  block, with separate light/dark palettes.

## License

Do whatever you like with this — it's a small personal practice tool.
