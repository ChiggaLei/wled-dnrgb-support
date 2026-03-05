# Installation Guide

## Docker Data Volume (Do This First For Docker)

If running Jellyfin in Docker, add a persistent volume for ambilight data before installing the plugin:

```yaml
services:
  jellyfin:
    image: jellyfin/jellyfin
    volumes:
      - /path/to/config:/config
      - /path/to/ambilight-data:/config/data/ambilight  # Add this line
```

Or with docker run:
```bash
docker run -v /path/to/ambilight-data:/config/data/ambilight jellyfin/jellyfin
```

## Preferred: Plugin Repository Install

1. Go to **Jellyfin Dashboard** -> **Administration** -> **Plugins** -> **Repositories**
2. Click **Add Repository**
3. Enter:
   - **Repository Name**: `Ambilight`
   - **Repository URL**: `https://raw.githubusercontent.com/gabrielprat/jellyfin-ambilight/refs/heads/master/manifest.json`
4. Save, open **Catalog**, find **Ambilight**, and click **Install**
5. Restart Jellyfin

## Manual Install (Fallback)

1. Download the latest `jellyfin-plugin-ambilight_x.x.x.zip` from [Releases](https://github.com/gabrielprat/jellyfin-ambilight/releases)
2. Extract the zip file
3. Copy the `Jellyfin.Plugin.Ambilight` folder to your Jellyfin plugins directory:
   - Linux: `/var/lib/jellyfin/plugins/`
   - Windows: `C:\ProgramData\Jellyfin\Server\plugins\`
   - Docker: `/config/plugins/`
4. Restart Jellyfin

## Verification

After installation:
1. Go to **Dashboard** → **Plugins**
2. You should see **Ambilight** in the list
3. Click **Settings** to configure

## Next Steps

See the [README](README.md) for configuration instructions.
