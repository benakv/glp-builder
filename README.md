# GLP Builder

A visual editor for building **Global Landing Pages** for ReadMe Enterprise
groups. Design the page with forms — or edit the raw HTML with a live
preview — then copy the generated snippet into
`dash.readme.io → your group → Global Landing Page`.

## Features

- **7 templates**, modeled on ReadMe's official GLP examples
  (glp-rr-group-1…7) plus docs.dlocal.com: Audience Split, Solutions Grid,
  Launchpad, Bento, Help Center, Quick Links, Terminal Archive
- **Liquid mode** — cards auto-generate from your group's child projects
  via ReadMe's Liquid templating (`parentProject.childrenProjects`), so the
  page updates itself when projects are added or removed. Optionally lists
  each project's top guide categories.
- **Shareable links** — the Share button encodes your whole design into the
  URL (`#c=…`); anyone opening the link sees your exact configuration
- Native ReadMe **dark/light/system theming** via `data-color-mode` — no JS
  theme hacks
- 4 font pairings, per-card accent colors, hero buttons/chip, announcement
  ticker, section headings, contact banner, layout controls
- Copy or download the finished HTML

## Deploying (GitHub → Netlify)

1. Push this folder to a GitHub repository (`index.html` at the root).
2. In Netlify: **Add new site → Import an existing project → GitHub**, and
   pick the repo.
3. Build settings: leave **Build command** empty, set **Publish directory**
   to `/` (the included `netlify.toml` does this automatically).
4. Deploy. Every push to `main` redeploys automatically, and pull requests
   get deploy previews.

No build step exists — the app is a single self-contained `index.html`
(React + Babel from CDN, compiled in the browser). To update the app, just
edit/replace `index.html` and push.

## Notes

- Share links carry the design in the URL fragment; nothing is stored
  server-side. Unsaved work is lost on refresh unless you use **Share link**,
  **Download .html**, or **Copy HTML**.
- In Liquid mode the in-app preview shows 3 sample projects; ReadMe renders
  your real child projects server-side once the code is pasted into the dash.
