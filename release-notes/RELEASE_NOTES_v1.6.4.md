# Release Notes - v1.6.4

## Color Fidelity Fix (Extractor + Player)

- Fixed a regression that could produce washed/white-blue ambilight output and poor color matching with video content.
- Player color processing is now hardened to avoid invalid channel math:
  - per-channel gamma values are clamped to a safe range
  - saturation-adjusted channels are clamped before power/gamma transforms
- Extractor FFmpeg filter chain now explicitly enforces RGB conversion (`format=rgb24`) before raw frame output for more consistent colors across hardware/driver combinations.

## Manifest Cleanup

- Removed duplicate historical version entries from `manifest.json` so each release version appears once.

## Installation & Upgrade

- For installation and upgrade instructions, see `INSTALLATION.md`.
- After upgrading:
  1. Restart Jellyfin once to load plugin `1.6.4`.
  2. Re-test playback on content that previously looked white/blueish.
  3. If you still see stale color data on old binaries, re-run extraction for affected items from the Manager tab.
