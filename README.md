# TROA AIO Updater

Release information for the TROA AIO Updater Torch plugin. The current approved package is TROA-AIO-Updater.zip (v0.1.1).

The updater lets server owners opt in to individual TROA plugin release downloads using its local configuration. It checks approved GitHub Release assets at startup and stages updates for the next Torch restart.

Implementation source, server configuration, and distribution binaries are maintained in the private release repository. This repository intentionally contains only public-safe release documentation.

## Installation

Obtain the approved release package from the project owner, place it in Torch's `Plugins` folder, and restart Torch. Configure the generated `TROA AIO Updater.cfg` before enabling any managed plugin.

## Current release behavior

The updater checks owner-enabled TROA packages as Torch completes plugin loading. Its detailed console log identifies each package check and highlights when downloaded packages require a restart. The release package and implementation remain private.
