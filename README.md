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
- `public/hero-london.jpg` — current London skyline hero photograph.
- `public/hero-industrial.jpg` — previous industrial hero photograph.
- `public/architecture.jpg` — previous hero photograph, retained as an alternative.
- `public/fonts/` — local Geist fonts and their licence.
- `public/icon.svg` — favicon using the original logo’s “A” in site blue on a white rounded square.
- `public/icons/` — 192px and 512px app icons, separate maskable variants, and a 180px Apple touch icon.
- `public/site.webmanifest` — app name, icon references, theme colours and standalone launch settings.

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

Hero photography: [Carmen Dominguez on Unsplash](https://unsplash.com/photos/sunset-over-a-river-with-a-city-skyline-QIaCZ3gTqCs), used under the Unsplash License.
Previous industrial photography: [Declan Sun on Unsplash](https://unsplash.com/photos/steel-beams-of-an-industrial-buildings-roof-Jfr7YZWcyVY), used under the Unsplash License.
Previous architecture photography: Unsplash, photo-1486406146926-c627a92ad1ab.
Geist fonts: Vercel, SIL Open Font License (included in `public/fonts/OFL.txt`).

The hero has a CSS-only 4.8-second background zoom and staggered text entrance. Motion is disabled when the visitor prefers reduced motion.

App icons are rendered from `public/icon.svg`. Maskable variants have an opaque white background and extra padding for device-specific icon shapes. The manifest provides home-screen identity; offline caching is not included. Test installation over HTTPS or localhost, rather than opening the HTML file directly.
