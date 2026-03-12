# Release Notes - v1.8.0

## Concurrent Extractions

- Added a new setting to allow multiple concurrent extractions. You can now extract up to 10 videos simultaneously.
- Removed sequential limitations in scheduled background task.

## Extraction Management

- Added a **Stop** button during active extractions in the plugin configuration UI.
- Users can now explicitly cancel an ongoing extraction for an item, returning it to pending status.
- Implemented queueing mechanics: excess extractions triggered manually will be queued and show up with a `Queued` status until a concurrency slot frees up. Queued items can also be cancelled.
- Added **Extract Pending** buttons to the series and season headers in the Extraction Manager to quickly queue an entire series or season.
- Improved Extraction Manager layout: episodes are now explicitly identified with their number in a left-aligned column for better readability within a series hierarchy. Also removed redundant "Movie" labels.
- **Fix**: Resolved an issue where videos stuck in `Extracting` or `Queued` state due to a server restart were permanently frozen. They now correctly revert to `Pending` on startup.

## General Improvements

- Minor backend UI fixes and logic changes to correctly handle multiple in-flight extraction tokens.
