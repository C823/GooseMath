# GooseMath v1.0.8

Updated `index.html` and `game.html` to use assets served by the same Cloudflare Worker from the GitHub repository:

- `cubes.svg`: background image for the main page and sidebar (replaces embedded base64 cube SVG and v1.0.6 gradient override).
- `wordmark.svg`: text wordmark in the logo tile (previously a hidden duplicate goose image).
- `goose.png`: goose mascot image (also fixes the game page embedded mascot).
- `logo.jpg`: favicon (unchanged).

**Upload `cubes.svg`, `wordmark.svg`, `goose.png`, and `logo.jpg` to the root of the repository alongside `index.html`, `game.html` and `games.json`.** The SVG assets are linked, not bundled, because you said they are in the repository.

Existing game card links, metadata and CDN icon URLs are unchanged. The existing Cloudflare Worker serves these root SVG files if its GitHub asset routing is enabled.

## v1.0.9 — CDN icons now allowed by the browser
The saved SingleFile HTML pages contained restrictive Content Security Policy (CSP) metadata.
Although the icons pointed to `https://cdn.jsdelivr.net/gh/mathlesson/mathlesson.github.io/img3/GAMENAME.webp`, the policy blocked images from jsDelivr.
Both `index.html` and `game.html` now allow jsDelivr CDN images, as well as the GitHub Raw host for the GooseMath logo.
The game page also allows same-origin `fetch('games.json')` with `connect-src 'self'`, which was previously blocked.
Some icons may still fall back if the actual CDN filename is not present; those names need a per-game mapping.
Upload the replacement site files to the repository root. Existing Worker v1.0.4 needs no changes.

## v1.0.10 — CDN-only game icons
Every game card icon and every entry in `games.json` uses:
`https://cdn.jsdelivr.net/gh/mathlesson/mathlesson.github.io/img3/{game-slug}.webp`
All local icon fallbacks were removed, including the homepage `error` handler and the game detail page's `fallbackLogo` handling. If a CDN filename is absent, its icon will be missing instead of silently showing an older local icon. Check CDN filename availability separately.
