# Qubit Analytics — website

Single-page marketing site for the Qubit Analytics intraday trading course.
Everything is in `index.html`: markup, styles and scripts in one file, no build step.

## Running it locally

Any static server works, for example:

```bash
python -m http.server 5173
```

Then open <http://localhost:5173>.

## What is in here

| Path | |
|---|---|
| `index.html` | the whole site — five sections: hero, indicator, course, pricing, contact |
| `assets/mark.png` | the cube mark, used in the header and footer |
| `assets/lockup.webp` | the "Qubit Analytics" wordmark lockup |
| `assets/lockup.png`, `assets/logo.webp` | earlier artwork, no longer referenced |

## Notes for whoever edits this next

- **The contact form posts through EmailJS.** The service, template and public key sit
  near the top of the first `<script>` block. The public key belongs in client-side
  code; it is not a secret.
- **The logo artwork is drawn for light backgrounds.** `lockup.webp` ships on a solid
  black matte with no alpha, so it is composited with `mix-blend-mode: screen`. That
  only works on a dark background — a transparent export would remove the need for it.
- **Responsive range is 240px to 3840px.** The hero content is capped at 1920px so it
  does not sprawl on very wide screens; sections are capped at 1160px.
- **`<meta charset>` and `<meta name="viewport">` must stay.** Without them the page is
  decoded as windows-1252 and phones lay it out at 980px.
