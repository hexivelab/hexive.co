# Hexive reconstruction QA

final result: passed

Scope: visual fidelity and local interactions of the recoverable homepage. This is not a claim that the missing Contact or article destination pages work.

## Source and evidence

The source is the 28 April 2025 archived homepage, restored from its HTML using the exact referenced Webflow CSS and original CDN assets. The live site and archived primary destination pages returned 404. No replacement artwork or guessed typography was used.

- Source desktop: `docs/evidence/source-desktop.png`
- Implementation desktop: `docs/evidence/implementation-desktop.png`
- Source mobile: `docs/evidence/source-mobile.png`
- Implementation mobile: `docs/evidence/implementation-mobile.png`
- Full-view combined comparisons: `docs/evidence/desktop-comparison.png` and `docs/evidence/mobile-comparison.png`
- Focused hero comparison: `docs/evidence/hero-comparison.png`
- Open mobile menu comparison: `docs/evidence/menu-comparison.png`

Desktop CSS viewport: 1280 × 720; source and implementation full-page captures: 1280 × 7380 pixels. Mobile CSS viewport: 390 × 844; both full-page captures: 390 × 7432 pixels. Captures use density 1 and were compared at equal dimensions. An early reference captured at browser zoom 110% was discarded and replaced with a 100% capture. All lazy images were loaded by scrolling before final capture.

States: full homepage, closed mobile navigation, expanded mobile navigation. The implementation's closed mobile capture includes the keyboard focus ring after an Escape test; this is intentional accessibility feedback. The source's Webflow hosting badge is intentionally absent from the Astro page.

## Fidelity surfaces

- Typography: original Recife Display and Inter fonts hosted locally. Display sizes, paragraph widths, heading wraps, weight, line height, letter spacing, and two-line article excerpts match the recovered reference.
- Spacing and layout: the hero, introduction, six principles, testimonial, 27 logos, CTA, four insights, and footer match the desktop and mobile section rhythm. Full-page heights agree at both checked sizes.
- Colors: original cream, near-black, peach accents, muted text, borders, and underlines retained from the source stylesheet.
- Images: source SVG logos, vintage-device image, texture, and all four editorial illustrations retained with their responsive variants. No missing images were reported by the browser after scrolling.
- Copy: original source homepage copy preserved. Semantic heading levels improved without changing visual styles.

## Comparison history

1. A raster-image dimension change enlarged rows of partner logos (P2). Removed the conflicting explicit dimensions from the partner section. The revised desktop comparison shows matching logo dimensions, row spacing, and CTA position.
2. The replacement mobile menu initially displayed its three links inline (P1). Added block layout for open-menu links. The revised combined menu screenshot shows the original vertical alignment and spacing.
3. Final desktop and mobile comparisons: no outstanding P0/P1/P2 visual discrepancies. Focused crops of typography, partner logos, article cards, footer, and menu were inspected alongside each corresponding source crop.

## Interaction and technical checks

- Desktop Insights link reaches the local Insights section.
- Mobile menu opens and closes with the correct accessible label and expanded state.
- Escape closes the mobile menu and restores focus to its trigger.
- Mobile What we do link closes the menu and reaches the introduction section.
- Home link returns to the top of the homepage.
- Browser console: no errors or warnings observed on the implementation.
- Mobile document width equals the 390px viewport; no horizontal overflow.
- `npm run check`: zero errors, warnings, or hints.
- `npm run build`: successful static production build.
- Local build assets validated for existence.

## External limitations

Contact and article links retain original external destinations. Those destination pages were not reconstructed and are not included in this QA pass. `PUBLIC_CONTACT_URL` accepts a real email or booking link; an email address was requested during implementation but none was supplied. What we do and Insights navigation target the matching homepage sections. The site has no form-submission backend.

## Implementation checklist

- [x] Source assets and fonts hosted locally
- [x] Desktop and mobile visual comparison
- [x] Mobile navigation and local section links verified
- [x] Astro check and production build
- [ ] Supply a valid contact destination before publication
- [ ] Supply source content for additional pages if they should be recreated
