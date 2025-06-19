# Dark and Light Pelican Egg

This repository contains a Pelican panel egg for running a **Dark and Light** dedicated server. The egg is fully featured and supports server clustering as well as Steam Workshop mods.

## Features

- **Cluster Travel**: Set `ACTIVATE_CLUSTER` to `true` and provide a unique `CLUSTERID` to enable travel between servers. The `CLUSTER_DIR_OVERRIDE` variable controls where the shared cluster directory is mounted. Ensure the directory has read/write permissions.
- **Mod Support**: Mods must be uploaded manually via SFTP. Copy both the mod's folder and its corresponding `.mod` file into the server's `Mods` directory. Populate the `MOD_LIST` variable with comma‑separated mod IDs so they appear in `GameUserSettings.ini`.
- Customizable environment variables for server name, map, admin password and more.

## Usage

1. Import `egg-dark-and-light.json` into your Pelican panel.
2. Configure the environment variables to match your desired server settings.
   - `SESSION_NAME` – server name
   - `SERVER_MAP` – map to load (`DNL_ALL` or `theshard`)
   - `MAX_PLAYERS` – player limit
   - Set clustering variables (`ACTIVATE_CLUSTER`, `CLUSTERID`, `CLUSTER_DIR_OVERRIDE`) if you want cross‑server travel.
   - Fill `MOD_LIST` with mod IDs (comma separated). Remember to upload mod files via SFTP.
3. Start the server. The startup script writes `GameUserSettings.ini` with your values and handles cluster directory checks.

## Notes on Mods

The server does not automatically download Steam Workshop mods. You must upload them manually. Place the entire mod folder **and** its `.mod` file under `DNL/Content/Mods` (or your chosen mods directory). `MOD_LIST` only writes the mod IDs into the configuration so that Dark and Light loads them at runtime.

Enjoy your Dark and Light server with Pelican!