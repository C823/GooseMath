# GooseMath v1.0.17

## Live games list
The homepage and game detail pages load `/api/powerhouse-games` from your Cloudflare Worker. The Worker fetches the current JSON array from `https://raw.githubusercontent.com/C823/Powerhouse/main/games.txt`.

**Deploy BOTH:** upload this ZIP to GooseMath repository `assets/` and replace Cloudflare Worker with `GooseMath-Worker-v1.0.17.txt`.

Games auto-update from Powerhouse roughly once per minute (depending on caching). Existing hard-coded game cards were removed. The game thumbnail attempts jsDelivr `img3/<game-slug>.webp`, then the existing fallback JavaScript tries `.jpg` and `.png`. Creators are listed only when the source contains a `creator` field; otherwise `Creator not listed`.

Games whose publishers forbid iframing may require clicking `Open game in new tab`. The source `link` is used as-is after HTTPS validation.
