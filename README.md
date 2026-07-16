# hushustest

Astro static site for a Swedish product comparison website inspired by hushustest.

## Project Structure

Astro exposes pages from `src/pages/`.

- `src/pages/index.astro` - homepage with editorial method and latest comparison entry.
- `src/pages/robotdammsugarna-2026-test.astro` - long-form robot vacuum comparison page.
- `src/components/` - shared head, header and footer components.
- `src/styles/global.css` - global design system and responsive utilities.

## Commands

All commands are run from the root of the project:

| Command                           | Action                                      |
| :-------------------------------- | :------------------------------------------ |
| `npm install`                     | Installs dependencies                       |
| `npm run dev`                     | Starts local dev server at `localhost:4321` |
| `npm run build`                   | Builds the production site to `./dist/`     |
| `npm run preview`                 | Previews the built site locally             |
| `npm run build && npm run deploy` | Deploys the site to Cloudflare              |
