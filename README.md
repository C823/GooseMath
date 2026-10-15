# GooseMath v1.0.6 — integrated homepage and game pages

Upload the **contents** of this folder to the root of your GitHub repository `C823/GooseMath`, replacing the older `index.html`, `game.html` and `games.json`. Enable GitHub Pages with **Deploy from a branch** and select your main branch/root, or deploy the same files to Cloudflare Pages.

The homepage has 456 game links. Every card opens `game.html?game=SLUG` and the game page loads title, creator and logo from `games.json`. Icons were extracted from your saved HTML into `assets/game-icons/`. The sample Eagle Craft credits Markus. Other games intentionally say **Creator not listed** until you enter a verified PERSON's name.

**To enable gameplay**, edit the `gameUrl` field for a game to point to a game you host or may embed. The uploaded snapshots do not contain a complete playable library. A blank `gameUrl` shows an informative notice, except the preserved Eagle Craft demo snapshot, which is not guaranteed to play.

This version works on GitHub Pages project sites because all routing uses file-relative URLs. The older `_redirects` route is not needed.

Some features from the SingleFile snapshots such as login, scores, external API calls, and cross-page React navigation are not fully functional without the original source/services.

## CDN Game Icons (v1.0.5)
All 456 catalog entries load their game thumbnails from:
`https://cdn.jsdelivr.net/gh/mathlesson/mathlesson.github.io/img3/GAMENAME.webp`
where `GAMENAME` is the existing game's URL slug (e.g. `eagle-craft`).
The homepage and detail page fall back to existing packaged thumbnails if the CDN image is missing or cannot load.
To use a different CDN filename for a game, edit its `logo` in `games.json` and the matching icon `src` in `index.html`.

## Blue branding (v1.0.6)
- Blue brand palette based on `#2c84e8` across homepage and game details, including sidebar and background.
- Goose artwork now uses `https://raw.githubusercontent.com/C823/GooseMath/main/goose.png`.
- Favicon uses `https://raw.githubusercontent.com/C823/GooseMath/main/logo.jpg`.
- Ensure **both files are committed** to your public repository main branch.
- Existing game CDN icons, metadata, and links are unchanged.
