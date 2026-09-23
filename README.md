# TROA AIO Updater

Release information for the TROA AIO Updater Torch plugin.

The updater lets server owners opt in to individual TROA plugin release downloads using its local configuration. It checks approved GitHub Release assets at startup and stages updates for the next Torch restart.

Implementation source, server configuration, and distribution binaries are maintained in the private release repository. This repository intentionally contains only public-safe release documentation.

## Installation

Obtain the approved release package from the project owner, place it in Torch's `Plugins` folder, and restart Torch. Configure the generated `TROA AIO Updater.cfg` before enabling any managed plugin.
