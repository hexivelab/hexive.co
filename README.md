# Hexive · Astro

A faithful recreation of the Hexive homepage archived on 28 April 2025, built with Astro and locally hosted source assets.

## Development

```sh
npm install
npm run dev
```

```sh
npm run check
npm run build
npm run preview
```

Node.js 22.12 or newer is required. The production build is static HTML in `dist/`.

## Structure

- `src/pages/index.astro` assembles the homepage.
- `src/components/` contains the eight page sections.
- `src/styles/source.css` preserves the original responsive design and self-hosted font declarations.
- `src/styles/site.css` adds accessible navigation, focus states, and reduced motion support.
- `src/site.ts` configures the contact destination.
- `public/assets/` contains recovered original images, SVGs, and font files.

No React, jQuery, Webflow JavaScript, remote font service, or archive scripts are required at runtime. The mobile menu supports keyboard navigation, Escape, closing after navigation, and resizing back to desktop.

## Source and recovery

Reference: https://web.archive.org/web/20250428023459/https://hexive.webflow.io/

The archive's stylesheet requests failed, but the exact stylesheet referenced by its HTML remained available from Webflow's CDN. The reference was restored using that stylesheet and its original assets before desktop and mobile inspection. The archive toolbar and Webflow hosting badge are excluded from the recreation.

The source includes the hero, introduction, six working principles, testimonial, 27 company logos, call to action, four insight cards, and footer. Original copy and responsive image variants are retained.

## Unavailable destinations

The Contact, What we do, and Insights destination pages returned 404 from the archive; the original live homepage also returned 404. What we do and Insights navigation now target their corresponding homepage sections. Article links retain the original external URLs; their full articles are not reconstructed.

All “Let’s talk” links open `mailto:hey@hexive.co`, configured in `src/site.ts`. No environment variables are required. This site does not submit forms or send messages.

Only publish the original fonts, imagery, and branding if you have the necessary rights.
