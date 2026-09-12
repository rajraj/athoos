# Athoos Ltd

A simple one-page HTML and CSS website. No framework, JavaScript, npm installation or build step is needed.

## View locally

Open `public/index.html` directly in your browser.

Or serve the site from this folder:

```sh
python3 -m http.server 8000 --directory public
```

Visit http://localhost:8000. Refresh the browser after editing. Press Ctrl+C to stop the server.

## Edit

- `public/index.html` — all page content, navigation and inline SVG icons.
- `public/styles.css` — styling, responsive layout and CSS animations.
- `public/athoos.svg` — vector logo used in the header and footer, with its viewBox fitted to the artwork.
- `public/athoos-logo.jpeg` — original JPEG, retained as a backup.
- `public/architecture.jpg` — hero photography.
- `public/fonts/` — local Geist fonts and their licence.
- `public/icon.svg` — temporary favicon.

All asset links are relative, so the page also works when opened as a local file. The footer year is plain text; update it when needed.

Contact: hello@athoos.uk.

## Cloudflare

The optional `wrangler.jsonc` publishes only the files in `public/`. No Worker code or build is required.

With Node.js available, sign in and deploy:

```sh
npx wrangler login
npx wrangler deploy --config wrangler.jsonc
```

To check the upload without publishing:

```sh
npx wrangler deploy --config wrangler.jsonc --dry-run
```

Alternatively, upload the contents of `public/` using Cloudflare Pages Direct Upload. Place `index.html` at the upload root; leave the build command empty if the dashboard asks for one.

## Credits

Architecture photography: Unsplash, photo-1486406146926-c627a92ad1ab.
Geist fonts: Vercel, SIL Open Font License (included in `public/fonts/OFL.txt`).
