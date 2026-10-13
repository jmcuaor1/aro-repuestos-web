# ARO Repuestos — Landing Page

Single-page marketing/catalog site for ARO, a Colombian manufacturer and wholesale distributor of spare parts for blenders and pressure cookers.

## Live Demo

[TODO: add live link] — no deployed URL was found in the repository.

## Screenshots

> Add screenshots to a `/screenshots` folder and reference them below.

![Home](./screenshots/home.png)
![Catalog](./screenshots/catalog.png)
![Contact](./screenshots/contact.png)

## The Problem It Solves

ARO manufactures and distributes replacement parts (blades, bases, lids, couplings, gaskets, fuses, valves, handles) for blenders and pressure cookers, targeting wholesale buyers, distributors, and repair professionals in Colombia. The site replaces ad-hoc catalog sharing (phone/WhatsApp) with a browsable, filterable online catalog that routes every inquiry straight to WhatsApp, and includes a Spanish-language personal-data consent flow aligned with Colombian data-protection law (Ley 1581 de 2012). *(Inferred from `src/App.tsx` content and copy; not stated explicitly as a mission anywhere in the repo.)*

## Features

- Responsive, single-page layout with a sticky header and mobile menu
- Product catalog (`PRODUCTS` in `src/App.tsx`) with category/subcategory filters (blenders vs. pressure cookers) and a text search box
- Per-product WhatsApp inquiry links generated via `wa.me` deep links
- Google Maps embed and directions link built from the business address
- Wholesale ("mayorista") benefits section
- Spanish personal-data consent checkbox and policy dialog (Ley 1581 de 2012)
- Scroll-triggered reveal animations via `IntersectionObserver`
- SEO basics: canonical URL, Open Graph/JSON-LD `LocalBusiness` structured data, `robots.txt`/`sitemap.xml` in `public/`

## Tech Stack

- **React 19** + **React DOM 19**
- **TypeScript 5.7**
- **Vite 8** (`@vitejs/plugin-react`)
- **Tailwind CSS v4** (`@tailwindcss/vite`)
- **pnpm** (version pinned via `.mise.toml`) and **Node 22** (via `.mise.toml`)
- **oxfmt** for code formatting

> The project was originally scaffolded for the "Figma Make" platform (see `vite.config.ts` plugins and `AGENTS.md`). Several Figma Make-specific plugins/config (e.g. the `./.figma/make/site.json` import in `vite.config.ts`) reference a `.figma/` directory that has since been removed from this repo — see **Known Issues** below.

## Project Structure

```
.
├── index.html              # Vite HTML shell, SEO meta tags, LocalBusiness JSON-LD
├── public/                 # Static assets: product photos, favicon, robots.txt, sitemap.xml
│   ├── licuadora/           # Blender part photos (cuchillas, bases, tapas, acoples, empaques)
│   └── olla-presion/        # Pressure cooker part photos (cauchos, fusibles, pitos-valvulas, manijas)
├── src/
│   ├── main.tsx             # React entry point
│   ├── App.tsx              # Entire application: data, components, sections
│   ├── index.css            # Tailwind v4 import, theme tokens, global styles
│   └── vite-env.d.ts
├── vite.config.ts          # Vite + React + Tailwind config, Figma Make dev-only plugins
├── tsconfig.json
└── package.json
```

## Getting Started

### Prerequisites

- Node.js 22
- pnpm 10 (pinned in `.mise.toml`)

### Installation

```bash
pnpm install
```

### Environment Variables

No `.env` file or app-level secrets are used. `vite.config.ts` reads these optional platform variables at build/dev time (all have defaults and are tied to the removed Figma Make tooling, not required for a standard Vite setup):

- `FIGMA_PUBLIC_URL`
- `FIGMA_DEV_SERVER_HOST`
- `PORT`

### Run

```bash
pnpm dev       # start the Vite dev server
pnpm build     # production build
pnpm preview   # preview the production build locally
pnpm format    # format code with oxfmt
```

> **Known issue:** `vite.config.ts` imports `./.figma/make/site.json`, but the `.figma/` directory was removed from this repository (see git history). As-is, `pnpm dev`/`pnpm build` will fail to resolve that import outside the original Figma Make environment. [TODO: restore a minimal `.figma/make/site.json` or remove the Figma Make plugins from `vite.config.ts` to run this project standalone.]

## Tests

No test setup (test runner, test files, or CI test scripts) was found in this repository.

## Author

**Juan Miguel Cuao Ríos**
Portfolio: [TODO: add portfolio link]
LinkedIn: [https://www.linkedin.com/in/juan-miguel-cuao-rios-b888081a9](https://www.linkedin.com/in/juan-miguel-cuao-rios-b888081a9)
