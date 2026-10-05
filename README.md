# fixins.com

Marketing site for **Fixins™**, the household meal planning app by Aerion Health
(Simple Digital Solution LLC). Served at **https://www.fixinsapp.com** (the repo name
says fixins.com; the live domain is fixinsapp.com).

## What's here

- `index.html` — the whole landing page (inline CSS + vanilla JS, no build step)
- `privacy-policy.html`, `delete-account.html` — required by the app stores; keep them linked
- `assets/screens/` — app screenshots shown in the phone frames (see its README for the slot list)
- `og-image.svg` — editable source for `og-image.png` (the social share image)
- `favicon.svg`, `sitemap.xml`, `robots.txt`

## Preview locally

Any static server works, for example:

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy

Every push to `main` deploys to GoDaddy cPanel over FTP via `.github/workflows/deploy.yml`
(secrets: `FTP_SERVER`, `FTP_USERNAME`, `FTP_PASSWORD`). Work on a branch and open a PR;
merging is the release.

## Regenerating the share image

`og-image.png` is a 1200x630 render of `og-image.svg` (which embeds
`assets/screens/classic-home.jpg`). After swapping screenshots, open the SVG in a browser
at 1200x630 and screenshot it, or use Playwright/headless Chrome.

## Launch-day switch

When the store listings exist, set `STORES_LIVE = true` in `index.html` and fill in
`APPLE_URL` / `PLAY_URL` with the real listing URLs.
