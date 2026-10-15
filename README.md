# GooseMath v1.0.7

Updated `index.html` and `game.html` to use assets served by the same Cloudflare Worker from the GitHub repository:

- `cubes.svg`: background image for the main page and sidebar (replaces embedded base64 cube SVG and v1.0.6 gradient override).
- `goosemath.svg`: text wordmark in the logo tile (previously a hidden duplicate goose image).
- `goose.png`: goose mascot image (also fixes the game page embedded mascot).
- `logo.jpg`: favicon (unchanged).

**Upload `cubes.svg`, `goosemath.svg`, `goose.png`, and `logo.jpg` to the root of the repository alongside `index.html`, `game.html` and `games.json`.** The SVG assets are linked, not bundled, because you said they are in the repository.

Existing game card links, metadata and CDN icon URLs are unchanged. The existing Cloudflare Worker serves these root SVG files if its GitHub asset routing is enabled.
