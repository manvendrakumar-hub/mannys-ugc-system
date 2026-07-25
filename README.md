# Manny's UGC System

Public presentation website for Manny's AI-assisted UGC production system.

**Production:** https://manny-ugc-systems.vercel.app

This repository contains the complete standalone website: presentation content,
optimized production media, PM/TH code snapshots, and Vercel configuration.

## Run locally

```bash
python3 -m http.server 4173
```

Then open `http://localhost:4173`.

## Deploy

The repository deploys to the existing Vercel project
`manny-s-projects11/manny-ugc-systems`. Pushes to `main` deploy through the
included GitHub Actions workflow, or deploy manually from the repository root:

```bash
vercel --prod
```

## Replacing media

- PM Downloads outputs are copied to `assets/videos/pm-downloads/`; numbered `01–03` appear first, followed by the remaining Downloads files and the original wired outputs.
- `cover.mp4` is the visible PM video in “Output, not theory”; `one more.mp4` is included in the PM browser.
- TH Downloads outputs are copied to `assets/videos/th-downloads/` and replace the previous TH library in `01–05` order.
- Product modelling/video-editing uploads go in `assets/manny-work/product-modelling-video-editing/`.
- Lottie files and previews go in `assets/manny-work/lottie-systems/`.
- App videos go in `assets/manny-work/app-videos/`.
- The original Manny-work uploads remain untouched. Optimized browser copies and poster frames live in each folder's `web/` subfolder.
- The Lottie Systems card uses `lottie-fast-forward-cover.mp4`, a 4× montage of all seven studies in sequence; the individual library clips remain available.
- AI Cost Sheet: the shared Google Sheet is connected by default in `#investment`.

The deployment uses optimized H.264 copies under `assets/web-videos/`.

## Review workflow

- Use **Browse PM outputs**, **Browse TH outputs**, or **Play reel** to inspect the wired media library.
- Use the fixed **Review notes** button to save section-specific feedback or questions for Bella.
- Notes stay in the current browser through `localStorage`; **Export JSON** creates a handoff file.
- `localStorage` is not shared between reviewers. A Vercel deployment needs an API route plus a shared database (for example Vercel Postgres, Supabase, or another approved store) before Manny/Bella can centrally receive feedback.
- Use **Open sheet** for the shared AI Cost Sheet. **Change link** can set a browser-specific override through `localStorage`.
- Add the cost per credit in the calculator to see daily and 30-day currency estimates.
- **Open PM Tool** and **Open TH Tool** point to the local Flask apps on ports `7860` and `7861`.
