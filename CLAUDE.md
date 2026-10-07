# EMT30205 Monitoring System Integration — course website

Interactive lecture notes for EMT30205 (Bachelor of Electrical Maintenance System,
Faculty of Electrical Engineering (FKTE)),
served by GitHub Pages at https://shukorrahim.github.io/EMT30205/. Students use it as lecture notes.

## Files
- `index.html` — course homepage. Chapters and labs are listed in the `CH` and `LABS`
  arrays in its script (marked "Edit here"). Set `href` to publish one.
- `chapter1.html`, `chapter2.html`, ... — one page per chapter.
- `lab1.html`, `lab2.html`, ... — Lab 1 is an interactive OMRON CPM1A / CX-Programmer simulation.

Every page is one self-contained HTML file: all CSS and JS inline, no build step.
`chapter1.html` is the style reference for every new page.

## Style rules
- Industrial look: grey HMI-style page, Barlow / Barlow Condensed fonts, colour used mainly
  for status and alarms. Light and dark mode via the same CSS tokens and `scada-theme` key.
- System figures are dark SCADA HMI screens (`.hmi`: title bar, nav tabs, mimic, value boxes,
  alarm banner, faceplates with select-then-execute).
- Every section has something interactive. Plain, simple English with analogies; keep Malay
  terms where the lecture notes use them.
- Images: the lecturer's own slide images, freely licensed Wikimedia Commons photos with
  credits, or SVG diagrams. No watermarked or textbook-scanned images.
- Each page ends with a quiz with instant feedback.
- Progress keys: Chapter 1 uses `scada-seen` / `scada-best`. New pages use their own keys
  (e.g. `ch2-seen`, `ch2-best`) and must be registered in the homepage `CH` array.

## Phones (iOS and Android)
Most students open the site on a phone. Every page must:
- Have no page-wide sideways scroll at 375 px wide.
- Keep HMI/diagram SVG text at about 8 px or larger: on phones (max-width 700px) wrap wide
  SVGs in a `.pan` container with a `min-width` so they swipe sideways, with a `.pan-hint`.
- Give touch targets at least 44 px (36 px inside HMI screens) under `@media (pointer:coarse)`.
- Use the round icon theme button below 1080 px, `theme-color` metas, and
  `-webkit-text-size-adjust:100%` (copy the "Phones and tablets" CSS block from chapter1.html).

## Workflow
Always show the lecturer what changed before pushing to GitHub.
