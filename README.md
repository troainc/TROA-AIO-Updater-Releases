# TROA AIO Updater

TROA AIO Updater is a Torch plugin for server owners who want a clear, owner-controlled way to check approved TROA plugin releases before their server starts.

Current documented release: **v0.1.19**.

## What server owners see

When Torch finishes loading plugins, the updater displays a TROA welcome message, checks the selected packages, and writes a detailed `Downloads` log showing whether each package is current, downloaded, or awaiting owner approval.

If a package is downloaded, Torch displays a restart notice and restarts after the configured delay so the new package loads before the server session begins.

## Basic use

1. Obtain the approved `TROA-AIO-Updater.zip` package from the project owner.
2. Put it in Torch's `Plugins` folder without extracting it.
3. Start Torch once to generate the updater configuration.
4. Set the desired per-plugin switches to `true` or `false`.
5. Restart Torch after editing configuration.

The owner-facing package switches cover Cleaner+, Monitor+, Hangar+, Econ+, Profiler+, and NPC+ (coming soon).

## Operator controls

- `Enabled`: turns the updater itself on or off.
- `CheckOnStartup`: enables startup package checks.
- Per-plugin `Downloads` switches: authorize or block package downloads.
- `RestartAfterDownloads`: controls whether Torch restarts after a package is downloaded.
- `RestartDelaySeconds`: restart countdown; default is 10 seconds.

## Support

- Discord: `discord.gg/troainc`
- Website: <https://therealmsofasgard.com>

This public repository contains release information and operator documentation only. Source code, binary archives, and server configuration remain private.