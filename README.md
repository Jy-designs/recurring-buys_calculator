# Venga · Recurring Buys

Landing page for Recurring Buys (DCA), built from the Figma section "Recurring buys – QA fixes" (node 7643:47446) in the "🎨 Website" file, in English and Spanish, with motion throughout.

Plain HTML, CSS and a little JavaScript: no build step or dependencies.

## Files
- `index.html`: markup, with English as the fallback copy
- `styles.css`: all styles, including the breakpoints and the motion states at the bottom
- `i18n.js`: every string in English and Spanish, plus the FAQ questions and draft answers
- `motion.js`: intro, scroll reveals, stacking step cards, count-ups, chart drawing, FAQ, blog switcher, nav and language menu
- `assets/v2/`: SVGs and images exported from the Figma section (photos compressed to JPEG, coins resized)
- `assets/`: the step phone mockups and step patterns from the first build, which are reused here
- `fonts/`: Labil Grotesk (excluded from git by `.gitignore`, see below)

## Breakpoints
These follow the four Figma frames:

| Range | Figma frame |
|---|---|
| 1280px and up | Desktop 1440 |
| 1025–1279px | Desktop 1025 |
| 768–1024px | Tablet |
| below 768px | Mobile |

## Languages
- The switcher in the nav changes between English and Spanish. The choice is remembered, and the URL takes `?lang=es` or `?lang=en`, so you can share a link in either language.
- Without a saved choice, the page follows the browser language.
- Keys follow the Lokalise Website convention (`sectionname::element::title`, tag `recurringbuy_post`), so they match the proposed keys in `../recurringbuy_post_keys.md`. Headings are written in sentence case and set in capitals by CSS.
- Prices and percentages are formatted per language (`€17,877.13` / `17.877,13 €`).
- Not translated: the phone screenshots in the steps and the "Scan & Download" label on the QR image, because they are images exported from the app.

## Motion
- Hero: the headline rises word by word, then the chart line draws, the pins drop in one by one, and the order card and coin settle in.
- Section headlines rise word by word, so it works in either language. Everything else reveals on scroll.
- Tiles: coins float, the slider runs and the bars grow.
- Example: the balance counts up and the chart line draws, with a pulsing dot at the end.
- Setting up: the step cards pin under the nav and stack, and covered cards shrink back and dim.
- Hover states only on things you can interact with. `prefers-reduced-motion` shows everything in its resting state.

## Run locally

    python3 -m http.server 3200

then open http://localhost:3200.

## Fonts
Labil Grotesk is a licensed typeface, so `fonts/` is ignored by git. Without it the page falls back to the system font. Copy the four `.otf` files into `fonts/` locally (they are in the other Venga projects).
