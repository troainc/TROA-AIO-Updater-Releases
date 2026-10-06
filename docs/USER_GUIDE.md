# TROA AIO Updater — operator guide

The Updater is a Torch-side installer for approved TROA plugin release packages. It checks the configured plugin catalog and owner selections, downloads allowed assets, verifies package metadata/checksums where supplied, stages installation, and may request a Torch restart so the new DLLs can load. It does not decide which features a plugin provides; each installed plugin remains the owner of its own commands, configuration, and webhooks.

## Install and select updates

Install the versioned updater ZIP through Torch and start once to create its config and state file. Read the current root [README](../README.md) and [release notes](../CHANGELOG.md). Review the plugin catalog and explicitly enable only products your server uses and accepts. An owner setting of Off prevents the updater from replacing that plugin package. Keep a known-good backup of the Torch Plugins directory and server configuration before the first automated update.

## Routine update flow

1. Review available releases and confirm each selection is intentional.
2. Let the updater download and validate the exact release asset name and package contents.
3. Review logs for staged files, verification results, and skipped products.
4. Allow the requested restart only during an approved maintenance window.
5. After startup, confirm each plugin loads and inspect its own status/configuration.

The state file tracks updater operation; do not replace it with hand-created sidecar files or rename package assets. Updates should preserve server-owned config and data. The updater installs plugin binaries; it does not migrate arbitrary server worlds or guarantee that a plugin's external service is available.

## Recovery and troubleshooting

If a download or validation fails, do not force the package into Plugins. Keep the previous known-good DLLs, inspect the updater and Torch logs, verify outbound GitHub access and disk permissions, and retry after confirming the catalog release is still available. If a plugin fails after restart, use that plugin's own changelog and recovery instructions; avoid repeatedly restarting while the cause is unknown.

Give the updater only the permissions necessary to update the configured plugin directory. Keep release feeds and server credentials private where applicable. Build/package validation and a successful download do not establish live-server acceptance; verify plugin loading and behavior on the target server after each update.
