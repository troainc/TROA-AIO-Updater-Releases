# TROA AIO Updater — Operator Checklist

## Before your first run

1. Get the approved `TROA-AIO-Updater.zip` package from TROA.
2. Place the ZIP directly in Torch's `Plugins` folder; do not extract it.
3. Start Torch once, then stop it after the updater has generated its owner settings.

## Configure ownership choices

1. Turn the updater and startup checks on.
2. Turn on only the individual TROA plugin downloads you authorize.
3. Keep a plugin's switch off to preserve its existing package and skip its download check.
4. Keep automatic restart on if you want newly staged packages to load before the server session starts.

## Verify an update run

1. Start Torch and find the `Downloads: TROA-AIO-Updater` lines in the log.
2. Check the queue count and each plugin result.
3. If a package downloads, allow the restart countdown to complete.
4. After restart, confirm the enabled packages report current before allowing players to join.

## Need help?

Send the relevant Torch log lines to [discord.gg/troainc](https://discord.gg/troainc) and identify the plugin package involved.
