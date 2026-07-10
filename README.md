# Hampton Hounds website

The live website for **Hampton Hounds Grooming** — boutique dog & cat grooming in
Hampton Village. A modern, responsive, single-page site hosted free on GitHub Pages.

**Live at:** https://www.hamptonhounds.co.uk

## Structure
- `index.html` — the entire site (single-page, self-contained: all CSS is inline in a
  `<style>` block; a small inline script handles the sticky header; the social feed and
  Google map load from external embeds)
- `images/` — logo assets (`logo-white.png` / `logo-black.png` are processed transparent
  versions; `hh-logo.jpg` is the original) and `images/new-web/` (the optimised photos
  actually used on the site)
- `CNAME` — custom domain (`www.hamptonhounds.co.uk`)
- `.nojekyll` — tells GitHub Pages to serve files as-is
- `images/New website photos/` — original full-size source photos (HEIC/JPG). **Git-ignored**
  (not deployed) — kept locally as the source for optimisation.

## Hosting / DNS
- **GitHub Pages** from the `main` branch, root. Pushing to `main` deploys automatically.
- Custom domain + HTTPS (Let's Encrypt, "Enforce HTTPS" on). DNS at GoDaddy: apex `A`
  records → GitHub Pages IPs (`185.199.108–111.153`), `www` CNAME → `tomjonesxx.github.io`.
- **Email** (`info@hamptonhounds.co.uk`) is **Microsoft 365**, provisioned via GoDaddy —
  its DNS records (`MX`, SPF `TXT`, `autodiscover`, `msoid`) must not be touched.

## Editing
- **Content/design:** edit `index.html` directly.
- **Adding photos:** optimise new images into `images/new-web/` before use — convert
  HEIC→JPEG, apply EXIF rotation, resize longest edge to ≤2000px, quality ~82 (keeps files
  small and browser-compatible). Reference them with root-absolute paths (`/images/new-web/…`).
- **Social feed:** the "Follow the pack" section is a [Curator.io](https://curator.io)
  combined Instagram + Facebook feed (embed div + loader script near `</body>`). It
  auto-updates from approved posts in the Curator dashboard — no code changes needed to
  refresh content.

## History
This replaced a flattened mirror of the old GoDaddy Website Builder site (retired
2026-07-10). That old site is preserved in git history if ever needed.
