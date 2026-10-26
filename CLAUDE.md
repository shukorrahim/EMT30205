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

## Course plan (9 chapters) and topic owners
Each topic is taught in full in ONE chapter only. Other chapters give a one-line recap and link to it.
The lecturer's HMI source file (old chapter 4) is split into Chapters 4 and 5, so chapters 6 to 9
now match the numbers of the lecturer's source files again.

| Ch | Title | Owns | Links back to |
|---|---|---|---|
| 1 | Introduction to SCADA | control philosophy, SCADA parts, RTU vs PLC, alarms, what an HMI is (1.10) | – |
| 2 | Communication Protocols | protocol idea, envelope, OSI, TCP/IP, Ethernet/CSMA-CD, Modbus, IEC 60870-5, DNP3, IEC 61850/GOOSE | serial details → Ch 3 |
| 3 | Serial Communication | RS-232/422/485, differential signalling, half/full duplex, converters, nodes, wired topologies (bus, ring, star, tree), PLC networking | OSI and "what is a protocol" → Ch 2 |
| 4 | Human Machine Interface (Part 1) | HMI in the loop, input/output, architecture under the screen, evolution, industries, the 5 HMI design rules (schematic, colour, layout, values, consistency) | "what is an HMI" → Ch 1.10 |
| 5 | Human Machine Interface (Part 2) | HMI components, HMI reading/writing PLC addresses, CX-Designer, Tutorial 1 and Tutorial 2 | design rules → Ch 4; serial link → Ch 3; work bits → Lab 2 |
| 6 | IoT Fundamentals | what IoT is, history, the "thing" (connect/compute/communicate), architecture, communication models, data, security/issues | IP basics → Ch 2 |
| 7 | IoT Protocols and Zigbee | the single wireless comparison table, MQTT/CoAP, Zigbee in depth (802.15.4, device types, mesh, self-healing) | star topology → Ch 3 |
| 8 | IoT in Monitoring Systems | ESP32/Pi/Arduino, gateways, cloud platforms, monitoring examples, SCADA vs IIoT | IoT definition/architecture → Ch 6; protocol table → Ch 7 |
| 9 | Design PLC and SCADA Systems | the design process (11 steps), FAT/SAT, documentation, one worked project | control philosophy → Ch 1; I/O list → Lab 1; comms → Ch 2/3; HMI screens → Ch 4/5 |

## Style rules
- Industrial look: grey HMI-style page, Barlow / Barlow Condensed fonts, colour used mainly
  for status and alarms. Light and dark mode via the same CSS tokens and `scada-theme` key.
- System figures are dark SCADA HMI screens (`.hmi`: title bar, nav tabs, mimic, value boxes,
  alarm banner, faceplates with select-then-execute).
- Every section has something interactive. Plain, simple English with analogies; keep Malay
  terms where the lecture notes use them.
- Images: the lecturer's own slide images, freely licensed Wikimedia Commons photos with
  credits, or SVG diagrams. No watermarked or textbook-scanned images.
- Chapters 1 and 2 end with a quiz. From Chapter 3 on (and in Lab 2) the lecturer chose no
  quiz: instead a "Jargon buster" section near the end, then the class game.
- Analogy boxes (`.ana`) give the Bahasa Melayu version after the English, in italics and in brackets.
- Animations are slow enough to read, step by step with a caption, and start from the button
  press (drive them from JS, not SVG `begin` times that start at page load).
- Every chapter ends with a last section "Class game: who answers?": the
  student-name roulette wheel (copy section, CSS and script from chapter1.html). Names are
  shared across chapters in localStorage key `class-names` and are never written into the
  page (the site is public). Each chapter keeps its own `chN-pool` / `chN-picked` keys.
- Every page except the homepage links back to `index.html` in three places: "← Course homepage"
  at the top of the hero (`.hero .back`), in the desktop side menu (`.side .home`), and as the
  first item of the phone/tablet section menu (`<li class="home-m">⌂ Home</li>` in `#navlist`).
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
