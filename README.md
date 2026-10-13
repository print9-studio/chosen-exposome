# Know Your Exposome — activation deck (web version)

Interactive version of the LIFEATBRIDGE EVENTS activation proposal for CHOSEN by Dermatology.
Served as static assets on Cloudflare Workers: `https://chosen-exposome.print9-everything.workers.dev`

## Controls
- Arrow keys / space / click right or left edge / swipe: move between slides
- `F`: fullscreen · `N`: toggle presenter notes (also `?presenter` in the URL)
- `#12` in the URL jumps to slide 12

## Deploy
Push to `main` → GitHub Actions runs `wrangler deploy` with the two repository secrets:
- `CLOUDFLARE_API_TOKEN` (token with "Workers Scripts: Edit")
- `CLOUDFLARE_ACCOUNT_ID`

Or locally: `npx wrangler deploy` (after `npx wrangler login`).

## Source
`public/` is generated from the slide files of the Claude Slides artifact; edit there and rebuild, or edit `public/index.html` directly.
