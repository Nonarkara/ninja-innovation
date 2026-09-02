<p align="center">
  <img src="docs/hero-banner.png" alt="Manga illustration of a civic studio: makers at a workbench with blueprints, a drone, and a robotic hand; teammates at a sticky-note wall; a waterfront city of temples and towers beyond the window." width="100%">
</p>

# Ninja Innovation

An interactive HTML ebook by **Non Arkara, PhD**. A people-centric practice for public-sector work in the AI era: how a public servant replaces million-dollar platforms with curiosity, public data, and a second-hand laptop.

**Read it live:** [https://ninja.nonarkara.org/](https://ninja.nonarkara.org/)

Edition 1.0 · Bangkok · March 2026 · NON·ISM PRESS

The colophon identifies the author as Senior Smart City Expert at Thailand’s Digital Economy Promotion Agency (depa). This repository is the book — a single static page — not a dashboard, not a vendor platform, and not the source code of the field systems it describes.

## What this is

Ninja innovation, as the book defines it, is solving a real public problem by combining three things that are now available to anyone with a laptop and curiosity:

1. **Public data** — satellite feeds, open APIs, and government records that are already obligated to be open if you read the fine print
2. **Generative and agentic AI** — to extend the reach of one person’s hands, not to replace their judgment
3. **A sideways question** — a useful proxy when the “right” data sits behind a paywall, a ministry, or a six-month terms of reference

The whole book is one file (`index.html`) with embedded styles and a small client-side reading layer. Fourteen chapters, three parts, plus a glossary, sources, and colophon.

| Part | Title | What it covers |
| --- | --- | --- |
| I | The Manifesto | What the practice is; the vendor trap; the Four Ps (Purpose, Practical, Proof, People); solve first, policy later; public data as the new gold |
| II | Field Notes | Nakhon Si Thammarat; Phuket; Rayong; a national livability index; an aerosol / satellite proxy |
| III | The Toolkit | The solo stack; designing for real use rather than demos; incentives; a coda on imagination and ethics |

Sister titles on the same imprint, linked from the page itself: [100 Days of Solitude](https://100days.nonarkara.org), [The Things You Can See Only When You Slow Down](https://slowdown.nonarkara.org), [What I Mean When I Say](https://mean.nonarkara.org), [Reading Dao De Jing with Dr. Non](https://dao.nonarkara.org).

## Philosophy

The ninja posture in this book is not heroic and not adversarial. It is oblique. You do not climb the wall. You find a substitute that is, for the purpose at hand, good enough — and already sitting in plain view.

The diagnostic the book keeps returning to is the **Four Ps**, in failure order:

| P | Verb | Test |
| --- | --- | --- |
| Purpose | Design | A measurable outcome, committed before anything is built — not a feeling, not a demo |
| Practical | Data | Name the physical decision this data changes within forty-eight hours, or the data is decoration |
| Proof | Optimize | Every belief is a hypothesis until the system confirms it. Ship, measure, then improve |
| People | Incentivize | Align self-interest with the public good. Instructions fade; incentives stay |

Around that frame sit a few other commitments, all taken from the text rather than invented for this README:

- **The flip.** The prototype is the proposal. The contract does not lead to the project; the project leads to the contract. The cost of being wrong is meant to stay in the range of a coffee.
- **Solve first, policy later.** Build a small working system. Watch what people do with it. Codify what works. Policy becomes a description, not a guess.
- **The proxy.** Ask not “how do I get the data I want?” but “what would tell me almost the same thing?” Aerosol as a stand-in for combustion. Flight arrivals as a stand-in for bus demand.
- **Real life, not demos.** One action per screen. Zero training assumption. Show the number, not the chart. Mobile first. Design for the confused person at 9am on a Monday.
- **Incentives beat instructions.** In the Nakhon Si Thammarat case the book records, citizen ratings feed a visible leaderboard that feeds promotion. Self-interest and public interest are made to point the same way.
- **Cheap enough to kill.** If a system does not work, turn it off. The freedom to build and the freedom to stop come from the same place: the cost is low.

The ninja innovator’s question is not *why is this so hard?* It is *what is the smallest move I can make right now that gets us partway there?*

## Ethical use

This repository is a book. It does not ship a surveillance stack, a tracker, or a credential store. The practice the book teaches is another matter. The same public data, the same models, and the same solo stack can build a pothole-repair bot or a system that follows people who have not consented to being followed.

Chapter 14 puts the constraint where it now belongs:

> The question that used to be “can we build this?” has become “should we?” The constraint has moved from engineering to imagination to ethics. In that order. We are now on step three.

Use this work in that spirit:

- **Serve, do not harvest.** The field notes are about flood response, buses, care, livability, and public satellite layers used as proxies — not about tracking movement without consent.
- **Stay cheap enough to stop.** The book trusts the practice because the systems it describes are small enough to fail and small enough to turn off. Scale that removes the kill switch also removes the ethic.
- **Put oversight in the incentive.** Where citizens can rate the service, the rating is a form of distributed audit. It is not perfect oversight. It is better than none.
- **Read the fine print of the data you use.** Public does not mean unbounded. Satellite agencies, messaging APIs, and open records each have terms. The book’s claim is that the fine print is often more permissive than procurement assumes — not that terms do not exist.
- **Do not treat this README, or the book, as a license to skip law.** Procurement exists in part as a discipline against corruption. The flip removes that discipline from the *front* of the process by making the prototype almost free. It does not repeal procurement, privacy, or criminal law.

If you fork the reader, keep it a reader. Do not add credentials, target lists, or private keys to a public tree. None are required to read the book.

## How it works

```
index.html          # the ebook: markup, CSS, and the reading script
_headers            # Cloudflare Pages cache rules
assets/photos/      # cover and part-divider photographs
docs/hero-banner.png
LICENSE
README.md
```

There is no build step, no package manager, no backend, and no environment file. Open the page and the book is there.

What the page does in the browser, all client-side:

- Chapter drawer, table of contents, and a reading-progress bar
- Bookmark memory, a continue-reading toast, and visited-chapter marks — stored in `localStorage` (`ninja:bookmark`, `ninja:bookmark-ts`, `ninja:visited`), not on a server
- Keyboard movement between chapters
- A print stylesheet and `prefers-reduced-motion` support
- A library footer to the other NON·ISM PRESS titles on `*.nonarkara.org`

The colophon states the live site is deployed on **Cloudflare Pages**. `_headers` matches that: HTML is not cached; files under `/assets/` may be cached for a day. The cover photograph and field photographs are from GITEX 2026, Singapore, as the colophon records.

## How to use

**Read online.** [https://ninja.nonarkara.org/](https://ninja.nonarkara.org/)

**Read locally.** Open `index.html` in a browser, or serve the repo root so the photographs load over HTTP:

```bash
python3 -m http.server 8080
```

Then visit [http://localhost:8080](http://localhost:8080). No packages, environment variables, or API keys are required.

| Key | Action |
| --- | --- |
| `j` or `→` | Next chapter |
| `k` or `←` | Previous chapter |
| `?` | Toggle contents |
| `Esc` | Close the drawer |

If you only read one part, the book’s own advice is to read the field notes. The principles sound obvious there. They are not obvious until you watch them work.

## License

This repository — the reader and its accompanying files — is licensed under the [MIT License](LICENSE). Copyright 2026 Non Arkara.
