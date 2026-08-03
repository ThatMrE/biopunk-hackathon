# BIOPUNK LAB — website

Static multi-page site for the Biopunk biohackathon movement: *get paid to build biology — no PhD, no entry fee.* Pure HTML + CSS (one shared stylesheet, no build step, no dependencies). Fonts load from Google Fonts over CDN.

## Pages

| File | Page |
|------|------|
| `index.html` | Home — hero, format, tracks, prizes, the lab, past editions, partners |
| `format.html` | The two-weekend + lab-week format, in depth |
| `tracks.html` | Challenge tracks (AI × cognition, longevity, biosensors, biomanufacturing, DeSci, open hardware) |
| `host.html` | Host-your-own playbook (14 sections: timeline → website scaffold) |
| `manifesto.html` | Why Biopunk — the iGEM contrast + portfolio-in-biology thesis |
| `get-involved.html` | The crew, the tribunal (judges), host candidates, partners, join |
| `faq.html` | FAQ for builders, hosts, and sponsors |
| `styles.css` | Shared stylesheet (the whole design system) |
| `404.html` | Themed not-found page |

Everything uses **relative links**, so it works at a domain root, a project subpath, or a custom domain — no config needed.

## Preview locally

Just open `index.html` in a browser. Or serve it (nicer for clean URLs):

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Push to GitHub

```bash
git init
git add .
git commit -m "Biopunk Lab site"
git branch -M main
git remote add origin https://github.com/<you>/biopunk-lab.git
git push -u origin main
```

## Deploy — pick one

### A) GitHub Pages, branch (simplest, zero config)
1. Push the repo (above).
2. Repo → **Settings → Pages**.
3. **Source: Deploy from a branch** → Branch: `main` → Folder: `/ (root)` → **Save**.
4. Live in ~1 min at `https://<you>.github.io/biopunk-lab/`.

The included `.nojekyll` file tells Pages to serve everything as-is.

### B) GitHub Pages, GitHub Actions (auto-deploy on every push)
1. Push the repo (the workflow at `.github/workflows/deploy.yml` is already included).
2. Repo → **Settings → Pages** → **Source: GitHub Actions**.
3. Every push to `main` rebuilds and publishes automatically. Watch it under the **Actions** tab.

### C) Vercel (matches your original host)
1. [vercel.com/new](https://vercel.com/new) → **Import** your GitHub repo.
2. Framework Preset: **Other** · Build Command: *none* · Output Directory: `./`
3. **Deploy.** (`vercel.json` is included.)

### D) Netlify
1. [app.netlify.com](https://app.netlify.com) → **Add new site → Import from Git**.
2. Build command: *none* · Publish directory: `.`
3. **Deploy.** (`netlify.toml` is included.)

## Custom domain
- **GitHub Pages:** add a `CNAME` file containing your domain (e.g. `biopunklab.com`), then set DNS per GitHub's docs.
- **Vercel / Netlify:** add the domain in the dashboard and follow the DNS prompts.

## Before you go live
- **Email signup forms are prototype stubs** (they pop an alert). Wire them to your list — Mailchimp/ConvertKit embed, a Netlify form (`<form netlify>`), Formspree, or an Airtable form — before launch.
- Real external links already point to your **Discord**, **biopunklab.com**, and **Luma** calendar.
- Fonts (Bungee, JetBrains Mono, Permanent Marker, Space Grotesk) load from Google Fonts; they fall back to system fonts offline.

## Credits
Design language modeled on the Biopunk Lab event site. Host playbook adapted from the **MLH Hackathon Organizer Guide** (CC-BY). Built on the shoulders of MLH + iGEM.
