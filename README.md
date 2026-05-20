# Chrome/Safari IDE (Start Page)

A minimal, privacy-focused browser start page inspired by lightweight IDE-like dashboards. It provides a large clock, a centered search box with suggestions, and a help overlay listing commands and categories. It's a static HTML/CSS/JS project meant to be opened locally or served from any static hosting.

## Features

- Clean, responsive single-page layout.
- Large clock with AM/PM styling.
- Search input with suggestion list and keyboard navigation.
- Help overlay with categorized commands.
- Simple, dependency-free vanilla JavaScript (no build step).
- Custom font files included in `assets/fonts`.

## Project structure

- `index.html` — main entry page.
- `css/style.css` — styles and responsive rules.
- `assets/` — fonts and icons used by the UI.
- `js/` — application scripts:
  - `body.js` — small DOM & utility helpers.
  - `clock.js` — clock display logic.
  - `config.js` — configuration and data (shortcuts, categories).
  - `form.js` — search form behaviour and keyboard handling.
  - `help.js` — help overlay rendering.
  - `influencers.js` — (project-specific) content providers.
  - `queryParser.js` — parses search queries and commands.
  - `suggester.js` — suggestion generation and rendering.
  - `svg-inject.min.js` — SVG helper for inline icons.
  - `index.js` — bootstrapping and wiring of modules.

> See the `js/` folder for the exact behaviour of each module. The code is written in plain ES5/ES6 JavaScript and runs in modern browsers without transpilation.

## How to run

Since the project is static, you can either open `index.html` directly in a browser or run a tiny local HTTP server (recommended for correct font & asset loading).

Open directly:

- Double-click `index.html` or open it with your browser.

Run a local server (zsh examples):

```bash
# Python 3 built-in server (recommended)
python3 -m http.server 8000

# then open http://localhost:8000 in your browser

# or use a small Node static server if you have npm installed
npx http-server -c-1 .
```

## Recommended browsers

Designed for modern Chromium-based and WebKit browsers (Chrome, Chromium, Edge, and Safari). It aims to work without polyfills, but if you plan to support older browsers, consider adding transpilation and polyfills.

## Customization

- To change the visual style, edit `css/style.css`.
- To replace fonts, update the files in `assets/fonts` and the `@font-face` src paths.
- To add or change commands, suggestions, or categories, edit `js/config.js` and the data used by `suggester.js` and `help.js`.

## Development notes

- There is no build step; the repository is ready to serve as-is.
- JavaScript modules are loaded via plain <script> tags in `index.html`. If you prefer a bundler, you can reorganize files into an ES module structure and add a build pipeline (Webpack, Rollup, Vite, etc.).
- To debug, open the browser DevTools and inspect `console` and the DOM.

## Troubleshooting

- If fonts or icons don't load when opening the file directly, use a local server (see "How to run").
- If keyboard shortcuts don't work, ensure the page has focus (click the page once) and that your OS/browser doesn't capture the same shortcuts.

## Contributing

Small improvements are welcome. Recommended workflow:

1. Fork the repo and create a feature branch.
2. Make small, focused commits.
3. Open a pull request describing the change.

If you'd like me to add a contribution guideline or tests, tell me how you'd like them structured and I'll scaffold them.

## License

No license file is included. If you want this project released under a permissive license (e.g. MIT), add a `LICENSE` file and I can update `README.md` accordingly.

## Credits

This project uses custom code and local assets. The `svg-inject.min.js` helper is included to manage inline SVG icons.


---

