# dumpty-website

The public website for dumpty, to be served at https://dumpty.bot. It is the page people find when they look the company up after receiving an email, for example from an exchange's institutional team.

It is a single static page with no build step:

| File | What it is |
|---|---|
| `index.html` | the page: headline, intro, four short sections and the contact address, over an animated 3D contour landscape under a night sky whose constellations draw like price charts, with a light film grain |
| `assets/logo.svg` | the logo used in the header (Figtree ExtraBold outlines with the falling constellation) |
| `assets/favicon.svg`, `favicon-32.png`, `favicon-48.png` | browser-tab icons |
| `assets/apple-touch-icon.png` | 180 px icon for phone home screens |
| `assets/og.png` | 1200 by 630 image shown when the link is shared |

Logo source files, colours and the design explorations are in the sibling repo `dumpty-design`.

## Notes

- The landscape is drawn with WebGL2 at up to 60 frames a second. Browsers without WebGL2 get a still canvas version. Everything stops for visitors who turn on reduced motion, and the animation pauses in background tabs.
- Fonts (Instrument Serif, Geist, Geist Mono) load from Google Fonts. The logo is outlines, so it needs no font.
- The copy stays general: no venues, strategies, figures or internal project names.
- Asset links are root-relative (`/assets/...`), so preview it through a local server rather than by opening the file: `python3 -m http.server` in this folder, then open http://127.0.0.1:8000.

## Hosting

Served by GitHub Pages from the `main` branch root of this public repo (public only because free Pages needs it; it holds nothing the site does not already show). `CNAME` sets the custom domain dumpty.bot, and `.nojekyll` makes Pages serve the files as they are. Pushing `main` publishes.

DNS for dumpty.bot, at the domain's registrar:

| Type | Name | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |
| CNAME | www | danielhaaser.github.io |

## Email

hello@dumpty.bot (shown on the page) goes through Namecheap's free email forwarding, set on the Domain tab under Redirect Email: a catch-all forwards every dumpty.bot address to the team's Gmail, and Gmail sends as hello@ through its own SMTP server.
