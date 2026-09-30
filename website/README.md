# Plainly Studio website

A four-section site for Plainly, an AI web design studio. It recreates the final
design from the "Sonnet 5.5 web design" walkthrough video: a pinned 3D hero whose
headline changes as you scroll, then Services, Process and Contact.

Everything is in one file, `index.html`. There is no build step.

## What's on the page

- **Hero:** glossy 3D shapes (three.js, loaded from cdnjs) move through three
  stages as you scroll. They start scattered, then line up on a shelf, then circle
  a small website. The headline changes with each stage.
- **Services:** "Three things, done well." (Website design, Build and launch, Copy and content).
- **Process:** "Fast because it's simple." A four-week timeline with Brief, Draft and Launch.
- **Contact:** "Tell us what you're building." Email with a copy button, plus availability.

The page follows the visitor's light or dark setting and works on phones. It also
respects reduced-motion preferences. If WebGL or the CDN isn't available, the
hero falls back to a static gradient and the text still works.

## Run it locally

Open `index.html` in a browser, or serve the folder:

```sh
cd website
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy

On Vercel, import the repository and set **Root Directory** to `website`
(Framework preset: Other, no build command). Netlify, GitHub Pages and
Cloudflare Pages work the same way: publish the `website` folder as-is.

## Make it yours

- **Copy:** every word is plain HTML in `index.html`. The three hero statements
  are the `.stage` blocks.
- **Colours and fonts:** the design tokens are at the top of the `<style>` block.
  The 3D shapes read `--cobalt`, `--periwinkle`, `--graphite` and `--porcelain`
  from there too.
- **Email:** search for `hello@plainly.studio`.
- **Timing:** the scroll points where the headline changes are `THRESHOLDS` in the
  first script. The hero's scroll length is `.js .hero { height: 330svh }`.
