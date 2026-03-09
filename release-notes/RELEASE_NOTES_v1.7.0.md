# Release Notes - v1.7.0

## RGBW Removal And RGB-Only Pipeline

- Removed the RGBW extraction configuration option from plugin settings.
- Removed RGBW extraction and playback code paths from the runtime.
- AMb2 generation and playback now use RGB (3-channel) only for consistent color behavior.

## Documentation Update

- Clarified `Input Position` mapping in README from viewer perspective:
  - `0` is the top-left LED.
  - `1` is the next LED to the right.
  - Continue clockwise around the screen.

## Runtime Configuration Reliability

- Updated runtime services to always consume the latest plugin configuration without requiring a Jellyfin restart.
- Device mappings, extraction queue settings, extraction LED counts, hardware acceleration, auto-extraction toggles, and playback tuning now refresh correctly from current saved config.

## Extraction Metadata In Item JSON

- Added extraction provenance fields in item metadata JSON files:
  - Plugin version used to extract the binary.
  - Extraction LED layout used for that extraction (`top`, `right`, `bottom`, `left`).
- This improves traceability/control when validating existing binaries after config changes or upgrades.

## Extraction Manager UX

- Removed JavaScript alert popups for item-level extract/delete actions in favor of non-blocking feedback.

## Installation & Upgrade

- For installation and upgrade instructions, see `INSTALLATION.md`.
- After upgrading:
  1. Restart Jellyfin once to load plugin `1.7.0`.
  2. Re-extract content that was previously generated with RGBW enabled.
