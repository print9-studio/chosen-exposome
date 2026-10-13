# Know Your Exposome — activation deck (web version)

Interactive version of the LIFEATBRIDGE EVENTS activation proposal for CHOSEN by Dermatology.
Public link (GitHub Pages): `https://print9-studio.github.io/chosen-exposome/`
Also deployed to Cloudflare Workers (behind the account's Access login): `https://chosen-exposome.print9-everything.workers.dev`

## Password
The slide content is encrypted inside `public/index.html` (PBKDF2 + AES-GCM) and decrypted in the browser after the password is entered. The password is not stored in this repo; to change it, rebuild with `DECK_PASSWORD=... python3 build.py` from the build folder.

## Controls
- Arrow keys / space / click right or left edge / swipe: move between slides
- `F`: fullscreen · `N`: toggle presenter notes (also `?presenter` in the URL)
- `#12` in the URL jumps to slide 12

## Deploy
GitHub Pages: Settings → Pages → Source: GitHub Actions. Every push to `main` publishes `public/`.

Cloudflare: Push to `main` → GitHub Actions runs `wrangler deploy` with the two repository secrets:
- `CLOUDFLARE_API_TOKEN` (token with "Workers Scripts: Edit")
- `CLOUDFLARE_ACCOUNT_ID`

Or locally: `npx wrangler deploy` (after `npx wrangler login`).

## Source
`public/` is generated from the slide files of the Claude Slides artifact; edit there and rebuild, or edit `public/index.html` directly.
