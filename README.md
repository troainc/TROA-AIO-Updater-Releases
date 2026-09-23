# TROA AIO Updater

TROA AIO Updater is the owner-facing update manager for approved TROA Torch plugins. It gives a server owner one place to decide which TROA packages may be checked and downloaded before a Space Engineers server session begins.

**Current documented release:** v0.1.19
**Torch package filename:** `TROA-AIO-Updater.zip`

## What it does

- Checks the latest release package for each TROA plugin the owner has enabled.
- Uses the release asset's own filename, so the downloaded package is identifiable in Torch's `Plugins` folder.
- Leaves a plugin alone when its download switch is off.
- Recognizes an already-installed current package and logs that no download was needed.
- Stages downloaded packages before the game server session starts.
- Restarts Torch after downloads, using the configured countdown, so newly staged plugins load cleanly.

The updater manages these plugin families:

| Plugin | Purpose |
| --- | --- |
| Cleaner+ | Cleanup, grid management, and maintenance |
| Monitor+ | Monitoring, alerts, and server visibility |
| Hangar+ | Grid storage and hangar management |
| Econ+ | Economy systems and expansion |
| Profiler+ | Performance profiling and diagnostics |
| NPC+ | Coming soon |

## Install and first run

1. Obtain the approved `TROA-AIO-Updater.zip` distribution from TROA.
2. Copy the ZIP into Torch's `Plugins` folder. Do not extract it.
3. Start Torch once. The updater creates its owner configuration on first run.
4. Stop Torch and set the plugin download switches you want to allow.
5. Start Torch again and review the updater messages in the Torch log.

The update manager itself must be enabled, and startup checks must be enabled, for automatic startup checks to run.

## Choosing what may download

Every supported TROA package has its own on/off download switch. This is an owner decision:

- **On** — the updater checks that package and may stage the newest approved release.
- **Off** — the updater does not download that package. Existing files are not removed or altered.

You can use this to roll out one package at a time, keep a known-good version in place, or defer a package while still allowing the rest of your selected TROA stack to update.

## What the Torch log means

At startup, the updater prints a TROA welcome block followed by a package scan. Typical entries look like:

```text
Downloads: TROA-AIO-Updater | Download queue: 5 enabled package(s).
Downloads: TROA-AIO-Updater | [1/5] Checking latest package: Cleaner+
Downloads: cleaner-plus is already current (...).
```

When an approved newer package is staged, the log reports its package name and completion. A red notice follows:

```text
NOTICE - DOWNLOADS DETECTED. SERVER WILL RESTART TO LOAD NEW PLUGINS.
```

Torch then displays the restart countdown. Let that restart complete before treating the new package as active.

## Safe operating routine

1. Keep a backup of the current Torch `Plugins` folder before enabling a new plugin family or changing a package version.
2. Enable only the packages you intend to manage.
3. Start Torch and watch the `Downloads` entries through the end of the scan.
4. If downloads are reported, allow the automatic restart to finish.
5. On the next startup, confirm each enabled package reports current before opening the server to players.

If you need to hold a version, turn that package's download switch off before starting Torch. The updater will not overwrite it while the switch remains off.

## Troubleshooting

| What you see | What to do |
| --- | --- |
| No updater messages | Confirm `TROA-AIO-Updater.zip` is in Torch's `Plugins` folder and the updater is enabled. |
| A package was not checked | Confirm its individual download switch is on and restart Torch. |
| A package is already current | No action is needed; the installed package matches the approved release. |
| Restart notice appears | Downloads were staged. Allow Torch's countdown and restart to finish. |
| A package does not load after restart | Keep the log, verify the package ZIP remains in the `Plugins` folder, and contact TROA support. |

## Support and links

- Discord: [discord.gg/troainc](https://discord.gg/troainc)
- Website: [The Realms of Asgard](https://therealmsofasgard.com)
- Release history: [RELEASES.md](RELEASES.md)
- Short operator checklist: [HOWTO.md](HOWTO.md)
- Planned work: [ROADMAP.md](ROADMAP.md)

## Public repository boundary

This repository intentionally contains public release notes and server-owner documentation only. Source code, compiled packages, private configuration, release infrastructure, and server-specific information are kept private.
