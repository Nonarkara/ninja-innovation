# Ninja Innovation

An interactive HTML ebook by **Non Arkara, PhD**. It is a people-centric practice for public-sector work in the AI era: how a public servant can replace expensive platforms with curiosity, public data, and a small solo tool stack.

**Live:** [https://ninja.nonarkara.org/](https://ninja.nonarkara.org/)

Edition 1.0 · Bangkok · 2026 · NON·ISM PRESS

## What this is

The whole book is a single static page (`index.html`) with embedded styles and a small interaction layer. There is no build step and no backend.

Ninja innovation, as the book defines it, is solving a real public problem by combining:

1. **Public data** — satellite feeds, open APIs, and records that are already available
2. **Generative and agentic AI** — to extend what one person can research and ship
3. **A sideways question** — a useful proxy when the “right” data is behind a wall

The text is organized as fourteen chapters in three parts, plus a glossary, sources, and colophon.

| Part | Title | Chapters |
| --- | --- | --- |
| I | The Manifesto | What ninja innovation means; the vendor trap; the Four Ps (Purpose, Practical, Proof, People); solve first, policy later; public data |
| II | Field Notes | Nakhon Si Thammarat; Phuket; Rayong; a national livability index; an aerosol / satellite proxy |
| III | The Toolkit | The solo stack; designing for real use rather than demos; incentives; a closing chapter on imagination and ethics |

The author is identified in the colophon as Senior Smart City Expert at Thailand’s Digital Economy Promotion Agency (depa).

## Features

Client-side only; reading position is stored in the browser (`localStorage`), not on a server.

- Chapter drawer and table of contents
- Reading-progress bar
- Continue-reading toast and visited-chapter marks
- Keyboard navigation: `j` / `→` next chapter, `k` / `←` previous, `Esc` close drawer, `?` toggle contents
- Print stylesheet
- `prefers-reduced-motion` support
- Footer library links to other titles on `*.nonarkara.org`

## Repository layout

```
index.html          # the ebook (markup, CSS, and script)
_headers            # Cloudflare Pages cache rules
assets/photos/      # cover and part-divider photographs
```

## Run locally

Open `index.html` in a browser, or serve the repo root so assets load over HTTP:

```bash
python3 -m http.server 8080
```

Then visit [http://localhost:8080](http://localhost:8080).

No packages, environment variables, or API keys are required to read the book.

## Deploy

The colophon states the site is deployed on **Cloudflare Pages**. `_headers` is the Pages cache config used here: HTML is not cached; files under `/assets/` may be cached for a day.

## License

This repository is licensed under the [MIT License](LICENSE).
