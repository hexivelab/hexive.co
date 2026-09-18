# Hexive

Hexive Startup Lab's website, built with Astro and TypeScript. The site introduces the team’s approach, working principles, client testimonial, and partner companies.

## Development

Use Node.js 22.12 or newer.

```sh
npm ci
npm run dev
```

## Validation and production

```sh
npm run check
npm run build
npm run preview
```

The production build is a static site in `dist/`.

## Deployment

GitHub Pages hosts the site at https://hexive.co. The workflow in `.github/workflows/deploy.yml` checks, builds, and deploys pushes to `main`. It can also be started manually from the repository's Actions tab.

The workflow uses Node.js 24 and the committed npm lockfile. GitHub Pages must use **GitHub Actions** as its deployment source, with **hexive.co** as the custom domain and **Enforce HTTPS** enabled.

`astro.config.mjs` sets the production URL, and `public/CNAME` includes the domain in the build. No repository `base` prefix is needed because the site is served at the domain root.

Deployment configuration follows the [Astro GitHub Pages guide](https://docs.astro.build/en/guides/deploy/github/).

## Project structure

- `src/pages/index.astro` assembles the homepage.
- `src/components/` contains the navigation, hero, introduction, principles, testimonial, partners, and footer.
- `src/layouts/Layout.astro` defines the document layout and metadata.
- `src/styles/global.css` contains typography, layout utilities, colors, and responsive styles.
- `src/styles/site.css` contains navigation behavior styles, keyboard focus indicators, and reduced motion support.
- `src/site.ts` defines the contact URL.
- `public/assets/` contains locally hosted images, logos, and fonts.

## Navigation and contact

“What we do” links to the homepage introduction. All “Let’s talk” links open an email to `hey@hexive.co`. Update `src/site.ts` to change the address.

The mobile menu supports keyboard navigation, Escape to close, and automatic closing after selecting a link or switching to desktop width.

No environment variables or backend services are required.
