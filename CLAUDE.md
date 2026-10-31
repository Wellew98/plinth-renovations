# CLAUDE.md — Plinth Renovations and Construction

> Permanent project context. Always stays in this repo. Keep it updated when
> durable facts change (brand, address, deploy flow, conventions).

## What this is

Static marketing site for **Plinth Renovations and Construction**, a renovation /
construction company in Cape Town, ZA. Page structure/flow is *inspired by*
https://thecoloradohandyman.com/ — never copy their HTML/CSS verbatim (copyrighted);
all code and copy here is original.

## Business facts

- Address: 64 Oxford Street, Richmond Estate, Goodwood, Cape Town, 7460
- Phone: `066 150 5770` (`tel:+27661505770`)
- Hours: Mon–Fri 7AM–6PM | Sat 8AM–2PM
- Service area: Cape Town (~25km of Goodwood), Stellenbosch / Somerset West
  by arrangement for larger jobs
- Positioning: renovations/construction, NOT a handyman — zero "handyman" mentions
- Tagline: "Built on vision · Crafted with precision"
- Young company: **no invented stats, warranties, timelines, or reviews.** Every
  number or claim on the site must be owner-approved and real.

## Brand

- Ink black `#0d0d0c`, champagne gold `#c9a86a`, bronze `#b8772a`
- Fraunces (display serif) + DM Sans (body). Logo: `logo.jpg` (header lockup).
- Design motto: "Rich people love space, not clutter; furniture must not touch
  walls." Prefer whitespace over content. One idea per screen.

## Repo & deploy

- Workspace root (this folder). GitHub: `https://github.com/Wellew98/plinth-renovations`,
  branch `main`. Live: `https://plinthrenovations.co.za` (apex; registered at Regery,
  DNS on Cloudflare, `www` 301s to apex). The old
  `https://plinth-renovations.wellefp.workers.dev` still resolves and should be
  turned off once the domain is verified.
- Cloudflare auto-deploys from `main` in ~1 min — wait, then hard-refresh.
- Domain-specific plumbing lives at the repo root: per-page canonical + OG/Twitter
  tags, `sitemap.xml`, `robots.txt`, `og-cover.jpg` (1200x630). Any domain change
  must update all of them together.
- Commit as: `git -c user.name="Plinth" -c user.email="plinth@cape.town" commit -m "..."`
- Only commit/push when asked or when finishing a requested change; inspect
  `git status` / `git diff` first, never commit secrets.

## Files

- Pages: `index.html`, `services.html`, `gallery.html`, `projects.html`, `blog.html`,
  `faq.html`, `areas.html`, `about.html`, `estimate.html`
- Root assets: `sitemap.xml`, `robots.txt`, `og-cover.jpg` (1200x630 social preview).
- `styles.css` (all styling, mobile breakpoints at 1120px / 600px / 380px),
  `script.js` (nav, reveal-on-scroll, counters, gallery slideshow, testimonial
  rotator, FAQ accordion, to-top, estimate form).
- Media: `images/` (all self-hosted), `hero-video.mp4` (5s Kling 720p, muted/loop/
  playsinline, `preload="metadata"` + poster), `logo.jpg`.

## Hard rules

1. **Self-host everything visual.** Owner uses Tor; Pexels/Unsplash and remote
   images are blocked. Only exception: the Google Fonts link.
2. **No emojis in UI** (use inline stroke SVGs). **No em dashes** in copy.
3. **Honest claims only** (see Business facts). Sample/testimonial content must be
   labeled or removed — never present placeholders as real reviews.
4. Mobile is primary: verify 390px (and 360px) plus desktop 1440px. Sticky-call FAB
   (bottom-right, mobile only) and `.to-top` arrow (bottom-left on mobile) must not
   overlap; to-top fades and hides over the footer.
5. SEO lives on inner pages (`services`, `areas`, `blog`); index stays quiet and
   spacious. Keep title/meta/H1/H2s meaningful.
6. Cape Town is winter-rainfall (May–Aug); seasonal copy must stay factual.
