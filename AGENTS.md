# Fab Chrome Extension

## Overview

Chrome Manifest V3 extension for downloading owned Unreal Engine assets from Fab without the Epic Games Launcher.

## Checks

- Parse JavaScript: `node --check <file>`
- Parse the manifest: `node -e "const m=require('./manifest.json'); console.log(m.version)"`
- No browser automation is configured; load the unpacked extension for manual checks.

## Conventions

- Keep browser code dependency-free and compatible with Chrome 103 or newer.
- Preserve explicit input bounds and integrity checks in manifest/chunk parsing.
- Keep `README.md` English-first and cross-linked with `README.zh.md`.

## Architecture

- `background/`: extension service worker and Fab authentication/API orchestration.
- `library/`: asset browser and download UI.
- `lib/`: storage and Unreal manifest/chunk parsing.
- `vendor/fab-download-browser.js`: bounded browser-side download/archive pipeline.

## Pitfalls

- Fab APIs and manifest formats are private and can change without notice.
- CDN response size can differ from a manifest's recorded compressed chunk size.
- Custom-field sections are size-prefixed; unknown versions are skipped because downloads do not consume their contents.

## Dependencies

No package manager or build step. The unpacked repository is the extension.
