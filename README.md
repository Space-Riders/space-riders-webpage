# Space Riders website

The page for Space Riders, a game in development: a landing page, a support
page with the feedback form, and their stylesheet. Static HTML, no build
step.

## Published at

GitHub Pages serves `main` from the repo root:
<https://space-riders.github.io/space-riders-webpage/>

| Page | Address | Used as |
|---|---|---|
| `index.html` | `…/space-riders-webpage/` | The store's Marketing URL |
| `support.html` | `…/space-riders-webpage/support.html` | The store's Support URL, and the game's support link |

If a page is renamed or the site moves, change the game's links in the same
release, and keep the old address answering until the builds that use it
are gone.

## Editing

- `index.html` is the landing page, `style.css` the styles of both pages.
  Preview with `python3 -m http.server` in this folder, then
  <http://127.0.0.1:8000/>; check light and dark mode and a phone's width.
- **Name only what the game really does.** Until it is on a store the page
  says "In development" and "Coming soon"; when it ships, replace the badge
  with the store's official badge linking to its listing.
- The palette in `style.css` (`:root` and its light-mode block) is
  provisional, matching the master design canvas's cover; change it to the
  game's theme once it has one.
- `support.html` holds the questions people ask most, the contact email and
  the feedback form. The form posts to the same endpoint and contract the
  game will use, documented in
  [space-riders-feedback](https://github.com/Space-Riders/space-riders-feedback),
  and the report becomes an issue in the game's private repo. It sends the
  version as `? via website`. The function only answers browsers from this
  site's origin (`https://space-riders.github.io`), so the form fails from a
  local preview or if the site moves to another domain: add the new origin
  to `ALLOWED_ORIGINS` in the function first.
- `icon.svg` is a placeholder icon. Once the game has an icon, export
  `icon-512.png`, `apple-touch-icon.png` (180 px) and `favicon.png` (64 px)
  from it and link them in both pages' heads.
- Images go in `images/` as WebP (`cwebp -q 86`), made from the same sample
  data as the store's screenshots and the master design canvas, never from
  someone else's work.
- The footer links to the Impressum, privacy policy and terms of use in the
  public
  [space-riders-legal-docs](https://github.com/Space-Riders/space-riders-legal-docs)
  repo. If those pages move, update the links here too.
- `.nojekyll` makes Pages serve the files exactly as committed.
