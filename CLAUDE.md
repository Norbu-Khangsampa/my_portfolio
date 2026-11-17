# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A personal portfolio website for Tenzin Norbu Gurung ("Tenzo"), a Mechatronics Engineering undergrad at Kent State, aimed at internships/co-ops in automation, embedded systems and controls. The site is a plain static page: `index.html`, `css/tokens.css` (colors, fonts, timing; dark default, light via `data-theme="light"`), `css/style.css`, `js/main.js`. No framework, build, lint or tests — open `index.html` in a browser to preview. Intended host: GitHub Pages.

Build status: all sections are built as a first pass (hero in the bolder "Side A" mood, 01 Motor Testbed, 02 SURE Research, 03 Project Sentinel, Liner notes, About, Contact, footer). The user will review and request changes later; they prefer changes one section at a time. Dashed "coming soon" boxes (`.slots`) and `<!-- TODO -->` comments in `index.html` mark where real media, code links and the résumé go.

Pending from the user: the Pi/MQTT motor-testbed code and the working Sentinel tracking code are on their Raspberry Pi and will be added later — leave clearly marked slots for code/media rather than describing the laptop-only snapshots as final. Résumé goes at `assets/resume.pdf` (hero button is a "soon" placeholder until then). If a music player is ever added it must start paused.

`material/` is the source content for the site, not site code:

- `about-me.md` — bio, coursework, tools, experience, contact links, and a **"Keep OFF the website"** list.
- `motor-testbed.md` — flagship project (Arduino edge + Raspberry Pi 5 gateway + Flask/MQTT dashboard, heartbeat fail-safe).
- `project-sentinel.md` — early learning project (Pi + OpenCV + servo, one-axis tracking).
- `sure-haptic-deadband.md` — summer 2026 SURE research (jitter-aware deadband for haptic teleoperation).
- `*.py`, `test_*/*.ino`, `SENTINEL.zip` — raw project code kept for reference/snippets. Sentinel files (`vision.py`, `tracker.py`, `servo_test.py`, `sentinel_core.py`, `color_turner.py`, `fps_test.py`) run on a Pi; `arduino.py` / `arduino_02.py` are the laptop-side serial reader and Flask dashboard (COM5, 9600 baud); `test_3.0` and `test_UART` are Arduino firmware snapshots.

`material/` is gitignored on purpose: the repo will be public and the notes (especially the SURE research) must not be.

## Content rules (these matter more than anything else here)

The markdown files encode explicit honesty constraints. Follow them when writing site copy:

- **Never publish** GPA, visa/work-authorization status, home address or phone number.
- Only present things as built if the notes say they are built. "Planned" / "NOT built yet" items (e.g. the closed-loop encoder/PID upgrade of the motor testbed) may appear at most as a short "Next" line.
- Project Sentinel is an *early learning build*: do not claim 3D-printed brackets, a tuned P controller, or a Flask dashboard for it.
- SURE research: show only title + one-paragraph summary until the user confirms what the advisor allows. Do not invent results or mention the planned follow-up simulation.
- Media/repo links marked "coming soon" are not available — use placeholders, don't fabricate URLs.
- Resolve remaining `TODO`s by asking the user, not by guessing.
- Some notes don't match the code in `material/`: e.g. the motor-testbed "Web Speed Slider Fix" says JSON parsing was added to the C firmware, but the firmware snapshots here use `<state,speed>` framing with no JSON or MQTT, and no switch/case state machine. The final Pi/MQTT version may not be in this folder — check with the user before publishing technical claims that the code doesn't back up.

## Visual direction: lo-fi hip-hop meets Edo-period Japan
Mood: late-night lo-fi beats, vinyl crackle, ink brush on old paper, calm
but with swagger. Inspired by the feel of Samurai Champloo and Nujabes,
but NEVER copy them: no characters, logos, show stills, album art, lyrics,
or their names anywhere on the site. Everything must be original.

Do NOT use the default Claude/AI look: no copper/orange accents, no purple
gradients, no glassmorphism, no generic rounded SaaS cards, no Inter font.

Palette (warm, muted, slightly faded like an old print):
- Paper background #EFE6D2 (light) / night ink #15130F (dark)
- Sumi ink text #1C1A17 / warm off-white #E8DFCC on dark
- Hanko seal red #B23A2B as the ONE accent, used sparingly
- Faded indigo #2F4A5C and moss #6B6F45 as secondary tones

Type:
- Headings: a Japanese-style serif such as "Shippori Mincho" or "Zen Old Mincho"
- Body: a clean readable serif or sans at 17–18px
- Labels, dates, specs: a monospace like "IBM Plex Mono", styled like
  track listings on a record sleeve (e.g. "01 — Motor Testbed  · 2026")

Texture and details (all made with CSS/SVG, no downloaded images):
- Subtle paper grain / film noise overlay
- Brush-stroke underlines and dividers drawn as SVG paths
- A small red square "hanko" seal with my initials (TNG) as the logo
- Optional vinyl-record or cassette motif for section markers
- Optional vertical text on the side as decoration only

Motion: slow and smooth, like a beat at 85 BPM. Gentle fade/slide on
scroll. Nothing flashy, no autoplay sound.

Readability comes first: a recruiter must find my projects, skills and
contact in under 10 seconds. Style supports the content, never hides it.
Good contrast (WCAG AA), works on phone, respects reduced-motion.
