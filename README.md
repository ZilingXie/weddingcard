# Yu-Gi-Oh Card Maker — Wedding Sign‑in Edition

Generate personalized Yu‑Gi‑Oh‑style cards as wedding sign‑in keepsakes. This is a Nuxt 2 static SPA that renders cards on an HTML5 canvas and lets guests download the result as a JPG.

![Preview](static/images/default.jpg)


## Key files

- [package.json](package.json)
- [nuxt.config.js](nuxt.config.js)
- [pages/index.vue](pages/index.vue)
- [store/index.js](store/index.js)
- [plugins/font-awesome.js](plugins/font-awesome.js)
- [static/lang.ui.json](static/lang.ui.json)
- [static/lang.card_meta.json](static/lang.card_meta.json)
- [netlify.toml](netlify.toml)


## Features

- Multi-language UI: Simplified Chinese zh, Japanese jp, English en
- Wedding-themed header and copy
- Card maker supports Monster, Spell, Trap types; multiple subtypes including Fusion, Ritual, Synchro, Xyz, Link, Token
- Effects flags normal, toon, spirit, union, gemini, flip, tuner
- Attributes and Types selection, with custom Type input
- Pendulum and Special Summon toggles; Levels, Ranks, or Link arrows
- Upload photo, pick title color, optional square-foil stamp, rarity N/R/UR
- Auto redraw every 1.5 s; safe filename generation; one-click Download
- Subtle 3D hover effect on the card preview


## Tech stack

- Nuxt 2.15, SPA mode ssr: false, target: static — see [nuxt.config.js](nuxt.config.js)
- Bootstrap 4 + BootstrapVue 2.21
- Font Awesome 5 via nuxt-fontawesome
- nuxt-font-loader for local and Google fonts
- Axios installed but not required for core functionality


## Requirements

- Node.js 16.x recommended (matches [netlify.toml](netlify.toml))
- npm 7+ or 8+


## Getting started

1. Install dependencies

   ```bash
   npm install
   ```

2. Run the dev server

   ```bash
   npm run dev
   ```

3. Open http://localhost:3000


## Available scripts (from [package.json](package.json))

- Dev: `npm run dev` — start Nuxt in development with HMR
- Build: `npm run build` — build for production
- Start: `npm run start` — start the production server
- Generate static: `npm run generate` — pre-render to dist for static hosting
- Lint: `npm run lint` — run ESLint
- GitHub Pages build/generate with `DEPLOY_ENV=GH_PAGES`
  - `npm run build:gh-pages`
  - `npm run generate:gh-pages`


## Usage

- Choose UI Language and Card Language from the top of the form
- Enter Card Name (e.g., your guest name)
- Upload a photo with the couple
- Pick Card type and subtype, set effects, attribute, and type
- Toggle Pendulum and Special Summon as needed
- For Link monsters, pick link arrows; for others, set Level or Rank
- Adjust text size fields for main and pendulum areas
- Click Download to save the rendered card as a JPG


## Internationalization (i18n)

- UI strings are defined in [static/lang.ui.json](static/lang.ui.json)
- Card layout metadata, offsets, fonts, and defaults are in [static/lang.card_meta.json](static/lang.card_meta.json)
- To add a language, add a new top-level key in both files and provide translations and card meta


## Project structure highlights

- Page and UI logic: [pages/index.vue](pages/index.vue)
- Vuex store module for loading dialog: [store/index.js](store/index.js)
- Fonts packaged under [static/fonts](static/fonts/font-face.css) with face definitions
- Card template assets and icons under [static/images](static/images)


## Build and deploy

### Static hosting

```bash
npm run generate
```

Outputs static site to `dist` which you can deploy to any static host.

### Netlify

- This repo includes [netlify.toml](netlify.toml) which sets Node version and build command
- Default command: `npm install --legacy-peer-deps && npm run generate`
- Publish directory: `dist`

### GitHub Pages

- The scripts `build:gh-pages` and `generate:gh-pages` set `DEPLOY_ENV=GH_PAGES` for GA tags
- If you deploy to a repository subpath, configure `router.base` accordingly in [nuxt.config.js](nuxt.config.js)


## Configuration notes

- App head metadata and analytics tags live in [nuxt.config.js](nuxt.config.js)
- Font Awesome is registered via [plugins/font-awesome.js](plugins/font-awesome.js)
- Components are auto-imported (`components: true`)


## License

MIT License. See [LICENSE](LICENSE).


## Acknowledgments

- Original work by 林子佑 (Copyright 2021) per [LICENSE](LICENSE)