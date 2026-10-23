# Video gallery (screening room)

A one-page Next.js demo styled as a film contact sheet. It holds **one hard-coded card** ("Intro to the OS",
Tutorial, 12:04). It does not host, embed or play any video: the page itself says "Static catalog, not a media
player" and "NO STREAM ATTACHED".

Live: https://video-gallery.bookchaowalit.com (deployed by Vercel CLI; it can lag `main`).

## What it does

- Search the card by title, summary or category, and filter by All / Tutorial / Talk ("Talk" is empty).
- `/api/mcp` answers JSON-RPC `initialize` and `tools/list` (an empty tool list); it echoes the request id and
  returns a JSON-RPC error for any `tools/call`, unknown method or bad JSON. It exposes no data.

## What it does not do

No YouTube, Vimeo or MP4 players, no playlists, no related-project links. Earlier portfolio copy claimed these; the
card is marked Prototype in `portfolio-site-web/docs/audits/CARD-CLAIMS-REVIEW-2026-10.md` (row `video-gallery`).

## Run

```bash
npm ci
npm run dev        # http://localhost:3000
npm run lint && npx tsc --noEmit && npm run build
```

CI: shared `platform-ci-workflows` v1.1.1 (lint, typecheck, build, security scan). There are no tests: this repo is
recommended for archive (see PRODUCT.md), so it is kept at L1 only.
