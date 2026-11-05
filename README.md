# ig-local-saver

A single local HTML page for saving Instagram posts, reels, stories and highlights **that your own account can already see**, in the best quality Instagram serves. A local alternative to "private downloader" websites, so your session data never goes to a third party.

## How it works

Instagram only serves private content to logged-in followers. Instead of handing your data to a website, you fetch it yourself from instagram.com with your own session, then paste it into this page, which runs entirely offline in your browser and extracts the media links.

## Usage

1. Download `index.html` and open it in your browser.
2. Paste a link (`/p/…`, `/reel/…`, `/stories/<username>/`, `/stories/highlights/<id>/`) and click **Generate**.
3. Get the data:
   - **Option A:** open the generated URL in the browser where you're logged in, copy all, paste into step 2 (posts only, less reliable).
   - **Option B (recommended):** on instagram.com open DevTools (F12) → Console, paste the generated snippet, then run `copy(__ig)`. The snippet is short and readable; it only calls Instagram.
4. Click **Extract media**, then download items individually or with:
   - **Download all (best quality):** photos + videos that have no HQ version.
   - **Download all images** / **Download everything** (standard quality).
5. For HQ videos, copy the generated terminal command and run it. It uses `curl` + `ffmpeg` to fetch the separate best video/audio tracks and merge them losslessly into `~/Downloads/*_HQ.mp4`.

## Notes

- Works only for content your account can view. It does not bypass privacy.
- Media links are signed and expire, so download soon after extracting.
- Instagram changes its internal endpoints occasionally; if extraction breaks, the endpoints in `index.html` may need updating.
- Never paste your cookies or unknown scripts into the console. Read the snippet before running it.
- Respect creators' privacy and Instagram's Terms of Use. Don't redistribute other people's private content.
