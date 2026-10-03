# TROA AIO Updater

TROA AIO Updater is the server-owner update manager for approved TROA Torch plugins. It checks only the plugin families you authorize and stages approved package updates before the Space Engineers server session starts.

**Current documented release:** v0.1.23
**Torch package filename:** `TROA-AIO-Updater.zip`

## What it does

- Checks the latest approved package for each enabled TROA plugin.
- Places the package in Torch's `Plugins` folder using the exact GitHub Release asset filename, including its version text.`r`n- Removes superseded ZIPs for the same managed plugin before restart, preventing duplicate plugin loading.
- Uses one `TROA-AIO-Updater.state.json` file in the `Plugins` folder to record confirmed package versions.
- Does not create a separate `.troa-aio-release` file beside each package ZIP.
- Leaves a package untouched when its owner switch is off.
- Stages newly downloaded packages before the server session starts.
- Restarts Torch after actual downloads so the new plugins load cleanly.

## Managed TROA plugins

| Plugin | Owner control | Purpose |
| --- | --- | --- |
| Overseer+ | On / Off | Administration and server operations |
| Cleaner+ | On / Off | Cleanup, grid management, and maintenance |
| Monitor+ | On / Off | Monitoring, alerts, and server visibility |
| Hangar+ | On / Off | Grid storage and hangar management |
| GridVault+ | On / Off | Grid preservation, backup, and recovery |
| Econ+ | On / Off | Economy systems and expansion |
| Profiler+ | On / Off | Performance profiling and diagnostics |
| NPC+ | Coming soon | Not checked until its public release is ready |

## Install and first run

1. Obtain the approved `TROA-AIO-Updater.zip` package from TROA.
2. Copy the ZIP directly into Torch's `Plugins` folder. Do not extract it.
3. Start Torch once so the updater creates its owner settings.
4. Stop Torch and choose which managed plugin downloads you authorize.
5. Start Torch again and watch the `Downloads` entries in the Torch log.

## Choosing what may download

Every listed plugin has its own owner switch.

- **On:** The updater checks that plugin and may stage its newest approved package.
- **Off:** The updater skips that plugin. Its existing package is not downloaded, replaced, or removed.

This lets you roll out one plugin at a time, keep a known-good package version, or maintain different TROA plugin combinations on different servers.

## What to expect in the Torch log

After Torch loads plugins, the updater prints its TROA welcome message and then a package queue, for example:

```text
Downloads: TROA-AIO-Updater | Download queue: 7 enabled package(s).
Downloads: TROA-AIO-Updater | [1/7] Checking latest package: Overseer+
Downloads: TROA-AIO-Updater | Downloading Overseer+: <release asset name>.zip
Downloads: TROA-AIO-Updater | Download complete: Overseer+ (... bytes).
Staged overseer-plus <release tag>; restart Torch to load it.
```

If no newer package is needed, the updater reports that the installed package is current. If one or more packages are staged, Torch shows this red notice and then performs its configured restart countdown:

```text
NOTICE - DOWNLOADS DETECTED. SERVER WILL RESTART TO LOAD NEW PLUGINS.
```

Let that restart complete before treating a staged package as active.

## Package state file

The updater writes one file named `TROA-AIO-Updater.state.json` in the Torch `Plugins` folder. It records the managed plugin ID, installed ZIP filename, release asset name, release tag, confirmation time, and the prior package metadata for each managed entry.

This file prevents unnecessary repeat downloads and restart loops. It is rewritten with indentation on startup so owners can read it. Older per-package `.troa-aio-release` marker files and updater-created `.zip.previous` copies are automatically removed; the active plugin ZIPs remain untouched.

## Safe operating routine

1. Back up your Torch `Plugins` folder before enabling a new plugin family.
2. Enable only the plugin packages you intend to manage.
3. Start Torch and let the updater complete the entire `Downloads` queue.
4. If the restart notice appears, allow the automatic restart to finish.
5. On the next startup, confirm each enabled plugin reports current before opening the server to players.

## Troubleshooting

| What you see | What to do |
| --- | --- |
| No updater messages | Confirm the updater ZIP is in Torch's `Plugins` folder and the updater/startup checks are enabled. |
| A plugin was not checked | Confirm that plugin's owner switch is on, then restart Torch. |
| A plugin is already current | No action is needed; the central state file confirms the installed package. |
| Restart notice appears | One or more packages were staged. Allow Torch's countdown and restart to finish. |
| Old marker files are visible | Start Torch with v0.1.21 or later; the updater removes its obsolete per-package markers. |
| A plugin fails after restart | Keep the relevant Torch log lines, confirm its ZIP is still in `Plugins`, and contact TROA support. |

## Support and links

- Discord: [discord.gg/troainc](https://discord.gg/troainc)
- Website: [The Realms of Asgard](https://therealmsofasgard.com)
- Release history: [RELEASES.md](RELEASES.md)
- Operator checklist: [HOWTO.md](HOWTO.md)
- Roadmap: [ROADMAP.md](ROADMAP.md)

## Public repository boundary

This repository contains public release information and server-owner documentation only. Source code, compiled packages, private configuration, release infrastructure, and server-specific information remain private.
## Documentation

See [`docs/README.md`](docs/README.md) for the owner setup path and links to update controls, safe operation, and troubleshooting.
