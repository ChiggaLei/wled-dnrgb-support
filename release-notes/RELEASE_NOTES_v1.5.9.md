# Release Notes - v1.5.9

## ⏸ Improved Pause Behavior

- When playback is paused, Ambilight now continuously re-sends the last video frame to WLED so the LEDs stay frozen on that frame instead of reverting to the controller’s previous effect or color.
- On resume, playback timing is preserved so Ambilight continues in sync with the video.

## 📦 Installation & Upgrade

- For installation and upgrade instructions, see the `INSTALLATION.md` file in the repository.
- After upgrading:
  1. Restart Jellyfin once to load the new plugin version.
  2. Verify that pausing/resuming playback now keeps Ambilight locked to the paused frame and resumes smoothly in sync.

