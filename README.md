# Coloring Fun — Big Machines & Rescue Vehicles

A free online coloring site for kids, built as a **single static page**
(plain HTML/CSS/JS — no build step, no frameworks, no external dependencies).

Visitors pick one of 12 line-art pictures (big machines and rescue vehicles),
tap/click a part of the picture to flood-fill it with a color from the palette,
then download their finished picture as a PNG or print it. Works with mouse
and touch; the layout is mobile-first (most visitors arrive from Pinterest
on phones).

Under the coloring area there is a promo block for the printed book
**“Dinosaurs & Big Machines Coloring Book” by MapleHandsCo** with a
“Get the Book on Amazon” button.

## Files

- `index.html` — the whole site (markup, styles and script in one file)
- `images/pic-01.png` … `pic-12.png` — full-size coloring pages (1200×800)
- `thumbs/pic-01.png` … `pic-12.png` — gallery thumbnails (240×160)

The artwork is the owner's own line art (pages from the “Big Machines &
Rescue Vehicles” coloring book project).

## How coloring works

The line art is drawn to an offscreen canvas and turned into a barrier mask
(dark pixels, dilated by 1px so outlines stay sealed). Taps flood-fill the
enclosed region on a separate color layer underneath; the visible canvas is
the color layer with the line art multiplied on top, so the black outlines
always stay crisp. Undo (up to 40 steps) and Clear are included, plus a
17-color palette and an eraser.

## Deploy to GitHub Pages

The site is static — publish this folder exactly as-is:

1. Create a GitHub repository and upload the contents of this folder
   (`index.html`, `images/`, `thumbs/` — keep `index.html` at the root).
2. In the repo: **Settings → Pages → Build and deployment → Source:
   “Deploy from a branch”**, pick the main branch and the `/ (root)` folder.
3. GitHub Pages serves the site at `https://<username>.github.io/<repo>/`.
   Every later push to the branch updates the site automatically.

(Any other static host works the same way — Netlify, Cloudflare Pages, etc.:
just drop the folder in.)

## Amazon link / Associates tag

The “Get the Book on Amazon” button currently uses a **plain Amazon link
with no Associates tag**:

```
https://www.amazon.com/dp/B0HQBPPZNQ
```

To earn Associates commission later, append the tag to the `href`, e.g.
`https://www.amazon.com/dp/B0HQBPPZNQ?tag=YOURTAG-20`.
The spot is marked in `index.html` with the HTML comment `<!-- AMAZON-LINK: ... -->`
(two places: the CSS comment for the promo block and the comment right above
the button link).
