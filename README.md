# Nishant Chaudhari — Portfolio

Personal portfolio site, live at [nishant-chaudhari-dev.github.io](https://nishant-chaudhari-dev.github.io).

A single-page site built around a sci-fi HUD look (radial system diagram, boot sequence, live clock, bracket-cornered panels) rather than a template. Covers background, projects, skills, experience, and contact info.

## Stack

Plain HTML, CSS, and vanilla JS. No build step, no framework, no dependencies to install.

- Fonts: Orbitron, Inter, and JetBrains Mono, loaded from Google Fonts
- Everything else (the HUD diagram, animations, starfield, clock) is hand-written SVG/CSS/JS in `index.html`

## Structure

```
.
├── index.html                  # the whole site
└── Nishant_Chaudhari_CV.docx   # linked from the hero and contact sections
```

## Running locally

No build tools needed. Either:

```bash
open index.html
```

or serve it so relative paths behave the same as production:

```bash
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Deployment

Hosted on GitHub Pages straight from the `main` branch. Push to `main` and the live site updates automatically, usually within a minute or two.

## Updating content

Everything is in `index.html`, no CMS or data files:

- **Projects** — each one is a `.proj-row` block inside `#projects`
- **Skills** — grouped under `.skill-cat` blocks inside `#skills`
- **Experience** — `.tl-item` blocks inside `#experience`
- **CV** — replace `Nishant_Chaudhari_CV.docx` with an updated file of the same name, or update the filename in the two places it's linked (hero CTA and contact section)

## Accessibility notes

- Respects `prefers-reduced-motion`: the boot sequence, rotating rings, radar sweep, starfield, and cursor reticle all fall back to static/off
- Decorative elements (canvas starfield, corner brackets, boot overlay, diagram) are marked `aria-hidden`
- Keyboard focus is visible on all interactive elements

## License

Personal project, all rights reserved on content (copy, resume, project descriptions). Feel free to reference the code structure if it's useful to you.
