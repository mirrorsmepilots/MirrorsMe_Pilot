# I² Platform — Agentic Solution Demos

A static website that catalogs our agentic AI demos, organized by industry.
No build step, no dependencies — just open `index.html`.

## Structure

```
.
├── index.html              # Home — "Explore solutions by industry" grid
├── healthcare.html         # Healthcare & Life Sciences (fully populated)
├── financial-services.html # Financial Services (example cards)
├── retail.html             # Retail (example cards)
├── high-tech.html          # High Tech (example cards)
├── manufacturing.html      # Manufacturing (example cards)
└── assets/
    └── styles.css          # Shared styles for every page
```

## How it works

- The **home page** (`index.html`) shows one card per industry. Each card links to that
  industry's page.
- Each **industry page** lists the agentic solutions for that sector as cards, modeled on
  the reference layout (icon, title, description, status, "View demo").
- All pages share `assets/styles.css`. Each industry page sets its own accent color via two
  CSS variables on the `<body>` tag, e.g. `style="--accent:#0E9F8E;--accent-soft:#E6F6F3;"`.

## Customizing

**Add a solution to an industry page** — copy one `<div class="scard">…</div>` block, then
edit the title, description, `chip` tags, the status (`live` / `demo` / `wip`), and replace
`href="#"` with the URL of the actual demo.

**Add a new industry** — duplicate any industry page, change the accent variables and content,
then add a matching `<a class="icard">` block to the grid in `index.html`.

Healthcare is filled in with real demos. The other four industries ship with example cards —
swap them for your real ones (look for the comment at the top of each file).

## Hosting

**GitHub Pages**
1. Push this folder to a GitHub repo.
2. Repo → Settings → Pages → Source: `main` branch, `/ (root)`.
3. Your site goes live at `https://<username>.github.io/<repo>/`.

**Netlify Drop** — drag the whole folder onto https://app.netlify.com/drop for an instant URL.

## Local preview

Open `index.html` in a browser, or run a tiny server from this folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```
