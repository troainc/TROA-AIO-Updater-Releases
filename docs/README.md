# AIO Updater documentation

TROA AIO Updater is a Torch-side package manager for approved TROA plugins. Server owners choose which plugin families it may update; it stages updates and may restart Torch after downloads so they load.

- Follow [Install and first run](../README.md#install-and-first-run).
- Review [Choosing what may download](../README.md#choosing-what-may-download), the expected [Torch log](../README.md#what-to-expect-in-the-torch-log), and [safe operating routine](../README.md#safe-operating-routine).
- Check [Troubleshooting](../README.md#troubleshooting) before changing package state.
- Read the [changelog](../CHANGELOG.md) and current release assets before upgrading.

Keep a known-good server backup and enable only the plugin updates you intend to accept. An owner switch set to Off prevents the updater from replacing that plugin package.
