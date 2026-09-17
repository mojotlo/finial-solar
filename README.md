# Finial Solar

Static marketing site for **Finial Solar Consulting** — a clean, dependency-free rebuild migrated off Squarespace, designed to host on **Cloudflare Pages**.

## Stack

- Plain HTML + CSS + a few lines of vanilla JS. No build step, no framework.
- Fonts: Cormorant Garamond (display serif) + Inter (body), via Google Fonts.
- Contact is handled with simple `mailto:` links (`taylor@finialsolar.com`) — no backend.

## Structure

```
index.html          Home (hero, intro, services, CTA)
our-team.html       Taylor Jackson bio
contact-us.html     mailto contact
404.html            Not-found page
assets/
  css/styles.css    All styles
  js/main.js        Mobile nav toggle + footer year
  img/              Logo, team photo, favicon
_redirects          Preserves old Squarespace URLs (/our-team, /contact-us)
_headers            Security + cache headers (Cloudflare Pages)
robots.txt, sitemap.xml
```

## Local preview

Any static server works, e.g.:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy — Cloudflare Pages

1. Cloudflare Dashboard → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
2. Pick this repo. Build settings:
   - **Framework preset:** None
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/`
3. Deploy. Then add the custom domain `finialsolar.com` / `www.finialsolar.com` under **Custom domains** and update DNS.

`_redirects` and `_headers` are picked up automatically by Cloudflare Pages.

## Content source

Text and imagery mirror the original finialsolar.com. To update copy, edit the HTML directly.
