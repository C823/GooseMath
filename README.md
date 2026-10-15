# GooseMath v1.0.14 - ZIP deployment

Upload this ZIP file UNEXTRACTED into the GitHub repository at:
`C823/GooseMath/assets/GooseMath-Integrated-v1.0.14.zip`

Then install the companion Cloudflare Worker from `GooseMath-Worker-v1.0.14.txt` in your Worker editor.
The Worker automatically discovers the highest semantic-version GooseMath-Integrated-v*.zip file under `/assets/` and serves each file inside it.

IMPORTANT: The release archive deliberately uses ZIP STORED (no compression) so the Worker can extract byte ranges without external npm libraries. For future releases retain this ZIP packaging method.

Existing root files `cubes.svg`, `wordmark.svg`, `goose.png`, `logo.jpg`, and `promo.jpg` are served directly from the GitHub repo as fallbacks if absent from the ZIP.

On a new release: upload only the new ZIP to `/assets/`; the Worker selects it after cache refresh (up to 5 minutes).

Current limitation: ZIP loading transfers the complete archive to the Worker on cache misses; consider Cloudflare R2 or Workers Static Assets for higher traffic.

## v1.0.14

The goose and GooseMath wordmark in the top-left logo are now a real link to `/` on both the homepage and game pages.
