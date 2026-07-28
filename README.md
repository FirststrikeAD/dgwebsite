# deflyinggravity.com

Static marketing site for DeFlying Gravity Real Estate Media (Metro Atlanta).

- `index.html` — the whole site (single page, no build step, no dependencies)
- `assets/` — hero photo, gallery photos, property reels, logo

The hero is rendered with hand-written WebGL (no libraries): the listing photo is
mapped to a gently curved plane with a perspective camera that responds to the
cursor. Falls back to a CSS background if WebGL is unavailable or the visitor
prefers reduced motion.

Booking runs on Spiro at book.deflyinggravity.com (separate host — not part of
this repo, and its DNS record must not be changed).

To edit: change `index.html`, commit, push. GitHub Pages redeploys automatically.
