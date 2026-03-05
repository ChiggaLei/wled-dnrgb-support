# Release Notes - v1.6.0

## Sequential Auto-Extraction For New Library Items

- New videos added to non-excluded libraries are now extracted one by one.
- Parallel extraction runs are now serialized through a single extraction gate to reduce CPU spikes on the Jellyfin host.
- This also prevents overlap between automatic, manual, and scheduled extraction triggers.

## Extraction Manager Disk Usage Counter

- The Extraction Manager now shows the total disk space used by extracted `.bin` files.
- The total appears to the right of the status counters.
- Size is automatically formatted using the best-fitting unit (`MB`, `GB`, or `TB`).

## Versioning

- Plugin version bumped to `1.6.0`.
- Manifest metadata now includes the `1.6.0` release entry.

## Installation & Upgrade

- For installation and upgrade instructions, see `INSTALLATION.md`.
- After upgrading:
  1. Restart Jellyfin once to load plugin `1.6.0`.
  2. Add a couple of new videos and verify extraction proceeds sequentially (one item at a time) in logs.
