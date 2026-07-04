# fouralba.com

Company website for **Four Alba LLC** — a static multi-page site built from the
Claude Design prototype `Fouralba Site Light.dc.html` (light theme).

Its primary purpose is to satisfy Google Play / Google Developer Console
requirements: a real developer website with app listings, a privacy policy,
terms of service, support contact, and account-deletion instructions.

## Structure

Plain HTML/CSS — no build step, no framework. Deploy the folder as-is to any
static host (Cloudflare Pages, Netlify, GitHub Pages, Vercel).

```
/                       Home — hero + app grid
/apps/mtt-gto-trainer/  MTT GTO Poker Trainer
/apps/scansitplay/      ScanSitPlay
/apps/blapl/            BLAPL
/apps/too-easy-qr/      Too Easy QR
/apps/poker-clock/      Poker Clock
/privacy/               Privacy Policy        ← paste into Google Play Console
/terms/                 Terms of Service
/support/               Support & Contact
/account-deletion/      Account & Data Deletion  ← paste into Google Play Console
/css/site.css           All styles (design tokens from the handoff)
/assets/                Logos, app icons, screenshots
/sitemap.xml, /robots.txt
```

Links are root-relative (`/apps/...`), so the site must be served over HTTP —
opening `index.html` directly from disk won't resolve paths. For local preview:
`python -m http.server` (or any static server) from this folder.

## Before launch (owner checklist)

- [ ] **Review the Privacy Policy and Terms drafts** — both pages carry a
      visible "*Draft — review before publishing*" note. Remove those `<em>`
      notes (in `privacy/index.html` and `terms/index.html`) once reviewed.
- [ ] Set the real "Last updated" dates on Privacy and Terms at launch.
- [ ] Deploy to a static host, point `fouralba.com` DNS at it, HTTPS on.
- [ ] Paste `https://fouralba.com/privacy/` and
      `https://fouralba.com/account-deletion/` into Google Play Console.
- [ ] Optional: generate a real `favicon.ico` / sized apple-touch icons from
      `assets/four-alba-icon.png` (the PNG is referenced directly for now).
- [ ] Optional: crop window chrome from the tops of some screenshots.

## Reference

`_handoff/` contains the original design handoff (prototype file, design
README, and source assets). Not needed in production — exclude it from deploys
or delete it once the site is live.
