# Hampton Hounds website

Mirrored from the original GoDaddy Website Builder site, cleaned up, and flattened
for GitHub Pages hosting.

## Structure
- `index.html`, `about-us.html`, `our-salon.html`, `our-services.html`, `location.html` — pages
- `images/` — all photos, renamed from GoDaddy's hashed filenames to descriptive ones
- `site.css` — GoDaddy's Website Builder engine stylesheet (layout depends on it — don't delete)

## What was cleaned up
- Removed the GoDaddy attribution badge
- Removed dead tracking scripts (GoDaddy's own traffic analytics, and a Universal
  Analytics snippet that stopped working when Google sunset UA in 2023)
- Removed the `duel.js` builder runtime and its loader config — it only powered two
  edge-case behaviours (an IE-specific background fix, and a hidden "force desktop
  view" toggle) that aren't needed
- Removed ~22 unused decorative `@font-face` declarations (Allura, Pacifico,
  Sacramento, etc.) — confirmed none were actually applied anywhere; kept Josefin Sans,
  the only font actually in use
- Consolidated the duplicate `home.html` (identical to `index.html`) into one file
- Renamed every image from GoDaddy's hashed filename + query string to something
  readable, and moved them into `images/`

## Known limitation
This site uses a fixed-width (997px), absolutely-positioned layout — GoDaddy's legacy
"Website Builder 7" canvas format, not a modern responsive layout. It renders correctly
as static HTML/CSS but isn't easily hand-editable or drag-and-drop friendly, since every
element is pinned by pixel coordinates rather than flowing naturally. Treat this as the
"preserve what's live and get off GoDaddy's bill" version — a from-scratch rebuild is a
better long-term base if you want to edit the design freely.

## To-do before fully cutting over from GoDaddy
- Update the `og:image` meta tags (one per page) to full absolute URLs once the site
  has a final home (e.g. `https://hamptonhounds.co.uk/images/salon-interior.jpg`) —
  they're currently relative paths, which works for browsers but not reliably for
  social-media link previews
- Check whether any page has a working contact form — if so, it's likely wired to a
  GoDaddy backend endpoint that will stop working once the plan is cancelled
- The `info@hamptonhounds.co.uk` inbox needs a replacement hosting solution before
  cancelling GoDaddy
