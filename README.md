# Are Mobile Developers Disappearing?

Talk deck for **AINNOVATE 2026 · Mobile Track** (10 minutes + Q&A) by Muhammad Luthfi Arifin, Product Engineer at Tech in Asia.

> Mobile developers are not disappearing. But the value of a mobile developer is moving beyond writing mobile code.

**Live:** https://luthfiarifin.github.io/slide-are-mobile-developers-disappearing/

Part of [luthfiarifin/research](https://github.com/luthfiarifin/research) (linked as a submodule under `99-talks/`) and deployed to GitHub Pages by CI.

## Slides

| # | Slide | Layout |
|---|---|---|
| 01 | Are mobile developers disappearing? | Cover with portrait |
| 02 | Journey: Android → Flutter → Mobile Product → Product Engineer | S11 horizontal timeline |
| 03 | Tech in Asia rebuild: problem → build → measure → learn → iterate | S14 loop |
| 04 | Result: +611% average session length, +120% DAU | S03 split statement |
| 05 | Writing the interface is becoming cheaper | S09 statement |
| 06 | The role is expanding | S08 duo compare |
| 07 | Evidence: what companies are hiring for | S16 screenshot cards |
| 08 | If I were learning mobile today… | S05 layers |
| 09 | The definition is expanding (closing) | Split closing |
| 10 | Questions? | S12 manifesto + banner |

## Presenting

Open `index.html` in a browser (no server needed).

| Key | Action |
|---|---|
| `←` `→` / wheel / swipe | Previous / next slide |
| `Esc` | Slide overview |
| `P` | Presenter view: notes, timer, next slide, audience window sync |
| `B` | Static (low-power) mode, no animations |

Speaker notes live in the `SPEAKER_NOTES` array near the end of `index.html`, keyed by each slide's `data-slide-id`. Planned timing is 8.5 minutes for a 10-minute slot.

Icons (Lucide), fonts (Google Fonts) and a Motion fallback load from CDNs; `assets/motion.min.js` is bundled, so the deck still works offline with system fonts.

## Development

```bash
npm ci
npx playwright install chromium   # enables rendered layout checks
npm test
```

`npm test` runs:

- `scripts/check-assets.mjs`: every local `src`/`href` resolves to a file
- `scripts/validate-swiss-deck.mjs`: registered Swiss layouts, image slots, and rendered overflow / nav-safe / title-gap measurements
- `scripts/validate-presenter-mode.mjs`: slide IDs, speaker notes and the 90% timing budget

## CI/CD

`.github/workflows/ci.yml`:

- **Pull requests:** run `npm test` in headless Chromium.
- **Push to `main`:** run the same checks, then publish only the site files (`index.html`, `cover.jpg`, `assets/`, `images/`) to GitHub Pages.

Dependabot keeps the Actions and npm dependencies up to date.

## Credits and license

Built on the Swiss Style template from [guizang-ppt-skill](https://github.com/op7418/guizang-ppt-skill) (Lime Green theme), with the presenter UI translated to English. The template and the vendored validator scripts are AGPL-3.0, so this repository is licensed under [AGPL-3.0](LICENSE).

Slide copy, speaker notes and the portrait are © Muhammad Luthfi Arifin. Screenshots on slide 07 are public LinkedIn posts, shown as evidence and cropped to the post content.
