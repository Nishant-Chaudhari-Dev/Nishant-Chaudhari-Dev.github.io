# Nishant Chaudhari | Portfolio

Personal portfolio site, live at [nishant-chaudhari-dev.github.io](https://nishant-chaudhari-dev.github.io).

A single-page site with a sci-fi HUD look: a page-spanning neural network in the background that scrolls with parallax and fires in chain reactions, a boot sequence, live clocks, a radial agent-loop diagram, project filters, and a small terminal. Covers background, projects, skills, experience, and contact info.

## Stack

Plain HTML, CSS, and vanilla JS in one file. No build step, no framework, nothing to install.

- Fonts: Orbitron, Inter, and JetBrains Mono from Google Fonts
- Live data: GitHub API (repo count, last push) and Open-Meteo (Boston weather), both keyless. If either is down, the page shows a fallback instead of fake numbers.

## Structure

```
.
├── index.html                  # the whole site
├── Nishant_Chaudhari_Master_Resume.docx   # the resume behind every download button
└── photo.jpg                   # optional; shows up in the About section automatically
```

## Running locally

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`. Opening `index.html` directly also works.

## Deployment

GitHub Pages, straight from the `main` branch. Push to `main` and the site updates within a minute or two. If the repo is ever switched to private and back, Pages gets turned off: re-enable it under Settings > Pages (deploy from `main`, root folder).

## Updating content

Everything lives in `index.html`:

- **Projects:** each one is an `<article class="proj-card">` inside `#projects`, newest first. Set `data-cat` to one or more of `agents infra rag industry robotics` so the filters pick it up. The project count in the hero and the filter counts update themselves.
- **Skills:** `.skill-cat` blocks inside `#skills`
- **Experience:** `.tl-item` blocks inside `#experience`
- **Photo:** add a square `photo.jpg` to the repo root
- **Resume:** replace `Nishant_Chaudhari_Master_Resume.docx` with a file of the same name. The site checks for `Nishant_Chaudhari_Master_Resume.pdf` first, then the `.docx`, then the old `Nishant_Chaudhari_CV.docx`, and links whichever exists. To use a different name, edit the `CANDIDATES` list in `index.html`.

## Accessibility

- Respects `prefers-reduced-motion`: the boot sequence, neural animation, reveals, decrypt text, tilt, and counters all fall back to static
- Decorative layers are `aria-hidden` and never take clicks
- Visible keyboard focus on every interactive element

## License

Content (copy, resume, project descriptions) is all rights reserved. Feel free to reference the code structure.
