# Publishing Guide

This guide explains how to publish new releases of the Jellyfin Ambilight Plugin.

## Prerequisites

- Push access to the GitHub repository
- Git configured locally
- .NET 8 SDK installed

## Release Process

### 1. Update Version Numbers

Update the version in these files:

1. **Jellyfin.Plugin.Ambilight.csproj**
   ```xml
   <AssemblyVersion>1.6.4</AssemblyVersion>
   <FileVersion>1.6.4</FileVersion>
   ```

2. **CHANGELOG.md**
   - Add a new section for the version
   - List all changes since last release

### 2. Commit Changes

```bash
git add .
git commit -m "Release v1.0.0.0"
git push origin master
```

### 3. Create and Push Tag

```bash
git tag v1.0.0.0
git push origin v1.0.0.0
```

This will automatically trigger the GitHub Actions workflow that:
- Builds the plugin
- Creates a release package (zip file)
- Calculates the MD5 checksum
- Creates a GitHub release
- Uploads the package as a release asset

### 4. Manifest.json is Updated Automatically

The manifest.json file is **automatically updated** as part of the release workflow. When you push a tag, the workflow will:

1. Build the plugin
2. Create the release with the zip file
3. Calculate the MD5 checksum
4. **Prepend** the new version to the `versions` array in manifest.json (with changelog from `release-notes/RELEASE_NOTES_vX.Y.Z.md`), keeping all previous versions
5. Commit and push the changes

**No manual action required!** Do not manually add a new version to manifest.json before releasing—the workflow adds it and deduplicates by version so the same version is never listed twice.

## Repository URL

Users can add your plugin repository to Jellyfin:

**Repository URL:** `https://raw.githubusercontent.com/gabrielprat/jellyfin-ambilight/master/manifest.json`

## Verification

After publishing, verify:
1. Release appears on GitHub releases page
2. Zip file is attached to release
3. Manifest.json is accessible at the raw GitHub URL
4. Plugin can be installed from the repository in Jellyfin
