# Video Script Builder

A single-file, Mad Libs–style outline builder for the belief-shift video format
(Thompson structure: STORY → PROBLEM → SOLUTION → CTA). Fill the blanks on the
left; a beat-by-beat outline renders live on the right. The point is format
discipline — the structure can't be skipped or reordered.

No build step, no dependencies, no backend. Just `index.html`.

## Run it locally

Open `index.html` in a browser.

- **Chrome** is recommended locally: it allows `localStorage` on `file://`, so
  saved drafts persist across reloads.
- **Safari** blocks `localStorage` on `file://`. The app still works and warns
  you — drafts are kept for the session only and won't survive a reload. Use
  **Download .md** to save your work, or host it on GitHub Pages (below).

## Host on GitHub Pages (recommended)

Pages serves over HTTPS, which fixes both `file://` limitations: clipboard copy
works via the modern API, and drafts persist in `localStorage` for real.

1. Push this repo to GitHub.
2. Repo → **Settings** → **Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Choose your branch (e.g. `main`) and folder **/ (root)**, then **Save**.
5. Wait ~1 minute, then open:
   `https://<your-username>.github.io/<repo>/Files/Web/video-script-builder/`

Notes:
- **Public repo = public tool.** Anyone with the URL can open it and view source,
  which exposes the constants (credibility line, offer, story names, concept
  definitions). Drafts stay private — they live in each visitor's own browser,
  never on the server. For a private tool, use a private repo with Pages
  (requires a paid GitHub plan) or keep it local.
- **Drafts are per-browser/per-device** and don't sync. **Download .md** is the
  portable copy.

## Editing the format (constants)

The locked format values live in one `CONSTANTS` object at the top of the
`<script>` in `index.html` — edit them in code, not in the UI. Three sets are
placeholders pending your framework doc:

1. **Concept definitions** — the one-sentence def for Tool Debt / Backwards
   Automation / Running on Improv (shown in beat 6).
2. **Story summaries + numbers** — Laura Brazan, Annie, Paolo, Craig (left blank).
3. **Beat timestamps** — the `ts` values in `SECTIONS`, targeted at a 12–15 min
   video.
