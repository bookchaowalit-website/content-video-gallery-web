# Video gallery (screening room) — Product truth

> Inferred from the code and copy (no user interview). Checked against the portfolio card claims review
> (`portfolio-site-web/docs/audits/CARD-CLAIMS-REVIEW-2026-10.md`, row `video-gallery`) on 2026-10-23.

## What it is

A static page with one hard-coded catalog card, a search box and category tabs. No media is stored, embedded or
played.

## Recommendation: archive

- The whole catalog is one card in `app/page.tsx`; the "Talk" tab is always empty; there are no media assets.
- The card's earlier claims (embedded YouTube/Vimeo/MP4 players, playlists, related links) do not exist.
- Same shape as `content-photo-web` (one hard-coded entry), which is also recommended for archive.
- Owner decision: archive the repository and retire the `video-gallery` card, or keep it and invest in a real
  catalog. Until then it is kept at L1 (patched Next, lint on, shared CI green) without tests or Sentry.

## Live URL and deploy state

- Live: https://video-gallery.bookchaowalit.com (HTTP 200 on 2026-10-23).
- Vercel project `bookchaowalit-video-gallery-frontend`, deployed only by CLI; last production deploy is the CVE
  patch (2026-10-23, CLI, commit 8208664). Its Git link names the old repository
  `bookchaowalit/bookchaowalit-video-gallery-frontend`, so a push to `main` does not deploy (owner action D9 if kept).
