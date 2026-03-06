# Release Notes - v1.6.3

## Installed Plugin Image Endpoint Fix

- Fixed installed plugin thumbnail resolution for Jellyfin's local image endpoint:
  `/Plugins/b3f6b4c70a3d4bd4a7e3c8d5a0a1e3f0/{version}/Image`.
- Release packages now consistently include both:
  - `thumb.png`
  - `meta.json` with `imagePath: "thumb.png"`.

## Workflow Packaging Consistency

- Updated release/build packaging logic to ensure image metadata and file are always shipped together.
- Prevents future releases from publishing without the required thumbnail files.

## Installation & Upgrade

- For installation and upgrade instructions, see `INSTALLATION.md`.
- After upgrading:
  1. Restart Jellyfin once to load plugin `1.6.3`.
  2. Hard refresh the Jellyfin web UI so cached plugin images are refreshed.
