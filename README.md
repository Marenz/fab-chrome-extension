# Fab Content Downloader

**English** | [中文](README.zh.md)

Download Unreal Engine assets you own from Fab without installing the Epic Games Launcher.

![Fab Content Downloader library page](images/page-example.webp)

## Requirements

- Desktop Chrome 103 or newer.
- An Epic Games/Fab account that owns the content you want to download.
- Enough disk space and memory for the download.
- A tool that can extract `.tar` archives.

The Epic Games Launcher and Unreal Engine are not required.

## Install

There is no Chrome Web Store listing. Install the extension manually:

1. Download or clone this repository.
2. Open `chrome://extensions` in Chrome.
3. Enable **Developer mode**.
4. Click **Load unpacked** and select the repository directory containing `manifest.json`.
5. Optionally pin the extension to the toolbar.

After updating the files, reload the extension from `chrome://extensions`.

## Usage

1. Sign in to [Fab](https://www.fab.com/) in Chrome.
2. Open the extension and click **Login with Epic Games**.
3. Click **Open Library** after authentication completes.
4. Find an asset and select the version you need.
5. Start the download and choose a local destination when prompted.
6. Inspect and extract the resulting `.tar` archive.

## Troubleshooting and Known Limitations

- If authentication or the library page stops responding, reload the extension at `chrome://extensions` and sign in again.
- Downloads can use substantial memory and disk space because assets are assembled into a local TAR archive.
- Fab may change its private APIs or asset formats without notice, which can temporarily break this extension.
- This fork accepts the custom-field v3 manifests used by UE 5.8-era builds and handles CDN chunks whose served size differs from the manifest's recorded compressed size. Older builds without this fix fail with `Unsupported custom-field data version 3` or a chunk-size error.

## Fork and Upstream

This is a fork of [SkylakeOfficial/fab-chrome-extension](https://github.com/SkylakeOfficial/fab-chrome-extension). It includes our upstream [English README PR](https://github.com/SkylakeOfficial/fab-chrome-extension/pull/1) and [UE 5.8 compatibility PR](https://github.com/SkylakeOfficial/fab-chrome-extension/pull/2).

## Disclaimer

This is an unofficial, vibe-coded, low-maintenance project. It is not affiliated with Epic Games or Fab, and continued updates, compatibility, and support are not guaranteed. Use it at your own risk. Only download content you are entitled to access; you are responsible for your account, data, licences, compliance with platform terms, and local files. For implementation details, see [SPECS.md](SPECS.md).

## License

GPL-3.0
