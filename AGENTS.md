## Project overview

SaaS-style landing page based on the **Syntro Astro** starter.
Built with **Astro 5** and **Tailwind CSS 4**, using `.astro` components for
reusable sections (hero, pricing, etc.) and a shared base layout.

- **Tech stack**
  - Astro (`astro.config.mjs`) with `@astrojs/sitemap`
  - Tailwind CSS via Vite plugin (`@tailwindcss/vite`)
  - `OptimizedImage.astro` for optimized images
- **Scripts** (`package.json`)
  - `dev` / `start`: `astro dev`
  - `build`: `astro build`
  - `preview`: `astro preview`

## UI structure

- **Global layout**
  - `src/layouts/BaseLayout.astro` wraps all pages:
    - Renders `<BaseHead />`, `<Navigation />`, `<Footer />`
    - Uses `<slot />` for per-page content

- **Navigation**
  - `src/components/global/Navigation.astro`
    - Logo from `/logo.svg`, current brand text **Syntro**
    - Links: `Features`, `Updates`, `Changelog`, `Faq`
    - Auth buttons: `Sign up` (`/signup`), `Log in` (`/login`)
    - Mobile menu controlled via `x-data` / `@click` (Alpine-style attributes)

- **Footer**
  - `src/components/global/Footer.astro`
    - Logo + short product description
    - Newsletter form (email + submit button)
    - Four link groups: All pages, Company, Developers, Support
    - Credits: “Your Company Name”, Getastrothemes, Bektur Aslan

- **Landing page**
  - `src/pages/index.astro`
    - Uses `BaseLayout` and mounts:
      - `Hero`, `SectionOne`, `SectionTwo`
      - `WhyChooseUs`, `HowItWorks`, `Pricing`, `Testimonial`
  - `src/components/landing/Hero.astro`
    - Hero copy (title, description, CTA, `featuresList`)
    - Buttons linking to the original repo and theme list
    - Main screenshot `/dashboard.png` via `OptimizedImage`

## Existing pages

- `src/pages/index.astro` → main landing
- `src/pages/login.astro` → login form
- `src/pages/signup.astro` → signup form
- `src/pages/faq.astro` → FAQs
- `src/pages/terms.astro` → terms
- `src/pages/privacy.astro` → privacy policy

> Footer and navigation include links to extra routes (`/about`, `/pricing`,
> `/features`, `/docs`, etc.) that do not exist yet. Create new `.astro` files
> in `src/pages/` if you want those pages to be real.

## Customization guidelines

- **Branding**
  - Replace “Syntro” with the real product name in:
    - `Navigation.astro` (logo / header text)
    - `Footer.astro` (name and credits)
  - Update `/src/assets/images/logo.svg` and/or `public/logo.svg`

- **Marketing copy**
  - Edit `Hero.astro` (tagline, main headline, body text, CTAs)
  - Adapt `SectionOne`, `SectionTwo`, `HowItWorks`, `WhyChooseUs`,
    `Pricing`, `Testimonial` to your actual value proposition

- **Legal & auth forms**
  - Adjust copy in `faq.astro`, `terms.astro`, `privacy.astro` to match
    your real business/legal requirements
  - `login.astro` and `signup.astro` are static; wire them to a backend
    or auth provider if needed

## Astro configuration

- File: `astro.config.mjs`
  - `site`: currently `https://yoursite.com` → set to the real production URL
  - `experimental.fonts`: loads Google font `Inter` as `--font-sans`
  - Integrations: `sitemap()` to generate `sitemap.xml`
  - Vite: Tailwind CSS plugin `tailwindcss()`

## Conventions for future changes

- Keep the current layout structure:
  - Global layout in `BaseLayout.astro`
  - Pages in `src/pages/`
  - Reusable sections in `src/components/landing/` or `src/components/global/`
- New page:
  - Create `.astro` file in `src/pages/` and wrap content in `BaseLayout`
- New reusable UI block:
  - Create a component in `src/components/` and import it into pages

## Assistant behavior

- Default responses to the user: **Spanish**, unless they explicitly request another language.
- Code, file names, and config examples: **English**, concise, and copy‑pasteable.
- Prefer short answers and minimal code snippets to reduce token usage.

