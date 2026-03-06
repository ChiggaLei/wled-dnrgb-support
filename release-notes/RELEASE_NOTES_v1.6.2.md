# Release Notes - v1.6.2

## Plugin Thumbnail Fix

- Fixed plugin packaging so `thumb.png` is always included in release zip assets.
- This ensures Jellyfin can display the plugin image on installed/active plugin cards.

## Build/Release Workflow Hardening

- Updated both GitHub workflows that produce release packages to include `thumb.png`.
- Workflows now fail early if the thumbnail is missing, preventing broken image releases.

## Installation & Upgrade

- For installation and upgrade instructions, see `INSTALLATION.md`.
- After upgrading:
  1. Restart Jellyfin once to load plugin `1.6.2`.
  2. Hard refresh the Jellyfin web UI so cached plugin images are refreshed.
