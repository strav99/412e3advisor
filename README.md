# 412(e)(3) Advisor — Website

Static microsite for **412(e)(3) Advisor**, a focused practice of **Remain Life Insurance Services, LLC** (Encinitas, California). An exact-match expert microsite in the same family as `1035advisor.com`, both funneling back to `remainlifeinsurance.com`.

Built on the **Remain design chassis** (same fonts, navy/paper palette, components) with the gold accent reskinned to the practice's two greens — **forest green `#2C6840`** and **grass green `#A2C682`**. The green values live in `--gold` / `--gold-soft` in `assets/site.css`; the variable names are kept from the Remain stylesheet so the proven chassis stays intact.

## What's here

- `index.html` — the main landing page: hero, "what it is," metrics band, three-plan comparison (Traditional DB / Cash Balance / 412(e)(3)), who-it-fits, process preview, professional-pension callout, FAQ (incl. the 412(i) reputation question), why-Remain, contact.
- `professional-pension.html` — supporting topic tucked under the 412(e)(3) authority: DB vs cash balance vs 412(e)(3), which structure fits.
- `how-it-works.html` — the full feasibility → design → implementation → exit process, and "who's at the table."
- `404.html` — branded not-found page.
- `assets/site.css` — the single shared stylesheet for every page.
- `remain-mark.png`, `remain-logo.png` — Torrey Pine brand mark (favicon + wordmark).
- `og-image.png` — 1200×630 social preview (shared from the Remain brand).
- `vercel.json`, `sitemap.xml`, `robots.txt` — host config + SEO.
- `MARKETING-PLAN.md` — Google paid-search strategy ($10K/yr → 2+ deals).

Each HTML page is standalone, links the one shared `assets/site.css`, and pulls fonts from Google Fonts. No build step.

## URLs / routing

`cleanUrls: true` in `vercel.json`, so links are extensionless (`/professional-pension`, `/how-it-works`). On Vercel these resolve to the `.html` files automatically.

> Local note: the plain `python3 -m http.server` preview does **not** do clean-URL rewrites, so locally the subpages must be opened as `/professional-pension.html`. On Vercel the extensionless links work.

## Local preview

```
python3 -m http.server 8912 --directory 412e3advisor.com
```
(or the `412e3` config in `.claude/launch.json`)

## Deploying to Vercel

1. Put this folder in a repo (or deploy the folder directly).
2. Import to Vercel, framework preset **Other** (plain HTML).
3. Vercel auto-applies `vercel.json` (clean URLs, security headers, asset caching).
4. Add the domain `412e3advisor.com` in Vercel → Settings → Domains, then point DNS.

## Open items before driving paid traffic

1. **Email inbox** — every CTA uses `office@remainlifeinsurance.com` (mailto), all links verified correctly wired. Inbox reported live (2026-06-02); do a one-time real send-test to confirm receipt before driving paid traffic.
2. **Lead form** — `mailto:` is the current primary CTA. A short form (name, profession, age band, income, contact) would convert and track better than mailto, and is the recommended next build.
3. **Conversion tracking** — install GA4 + Google Ads tags before launch (`MARKETING-PLAN.md §9`).
4. **Licensing/geo** — advertise only where Remain is licensed; start CA-only.
5. **Cross-links** — footers link to `remainlifeinsurance.com` and `1035advisor.com`. Confirm `1035advisor.com` is live before relying on that link.
6. **`og-image.png`** — currently the shared Remain image. Consider a 412(e)(3)-specific OG image later.

## Consistency notes

- The nav, footer nav, and CTAs across all three pages share the same taxonomy. Adding a page means updating the nav + footer on every page, plus `sitemap.xml`.
- Branding is intentionally dual: the practice identity ("412(e)(3) Advisor") sits visibly atop the Remain entity (LLC name, CA License #6019240) so the site reads as a real practice, not a lead-gen shell.
