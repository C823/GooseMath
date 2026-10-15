# GooseMath v1.0.12 — October 14, 2026

Changes:
- Homepage and game page promo image (`img.egg-image`) now loads `/promo.jpg` from the root of your GitHub repository, replacing embedded Base64 image data.
- Added a small visible version/date label to the bottom right of both pages and updated existing copyright version labels.
- Preserved the jsDelivr game icon fallback sequence, blue palette, `cubes.svg`, `wordmark.svg`, game navigation, and `games.json`.

## Deployment
Upload the contents of this ZIP to the root of `C823/GooseMath`, replacing the previous files. **Also upload a file named `promo.jpg` to the repository root.** The image is referenced but not included in this archive because it was not supplied. Existing GitHub-backed Cloudflare Worker needs no change.
