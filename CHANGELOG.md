## 2026-10-09 — Bifrost Plugin Panel operator guide

- Adds connection steps in the README and a detailed operator guide for opening this plugin’s workspace, permissions, settings, commands, and troubleshooting.
- Describes expected plugin-owned views only when the installed build exposes real data or safe controls. Documentation only; no runtime adapter or behavior change is claimed.

## Public operator documentation expansion - 2026-10-06

- Added a detailed user guide under docs/USER_GUIDE.md and linked it from the documentation index and root README.
- Documented current setup, feature ownership, command/config references, operational workflows, safety boundaries, and version/status limitations using the published behavior.
- Added repository-local context, contribution instructions, and a dated documentation log entry. No private source or credentials are included.

# Changelog

## 0.1.20 - 2026-09-23

- Fixed repeat downloads and automatic restart loops when a stable installed package filename differs from its GitHub release asset name.
- Added durable release identity tracking and retained previous-package rollback copies.

## 0.1.1 - 2026-09-23

- Corrected the Torch package startup-path handling.
- Approved package name: TROA-AIO-Updater.zip.

## 0.1.0 - 2026-09-23

- Initial public release record for TROA AIO Updater.
- Supports explicit owner opt-in per managed TROA plugin and next-restart update staging.

## 0.1.19 - 2026-09-23

- Documents finalized updater package scan, detailed operator log, and restart notice behavior.

## Documentation - 2026-09-23

- Expanded public-safe operator installation and configuration guide.

## Documentation refresh - 2026-09-23

- Reworked the public README and operator checklist with installation, per-plugin ownership controls, log interpretation, restart behavior, and troubleshooting.

## 0.1.21 - 2026-09-27

- Added public owner documentation for Overseer+ and GridVault+ package controls.
- Documented the consolidated Plugins-folder updater state file.

## Documentation correction - 2026-09-27

- Rebuilt the public README for v0.1.21 with the complete managed-plugin catalog, central state-file behavior, install steps, log interpretation, and troubleshooting.

## 0.1.22 - 2026-09-27

- Documented removal of physical .zip.previous files and readable central state JSON with prior-package metadata.

## 0.1.23 - 2026-09-27

- Documented exact GitHub asset-name installation and automatic removal of superseded managed ZIPs.

## Documentation update - 2026-10-03

- Added a documentation landing page for owner setup, package controls, safe operation, and troubleshooting.

## Documentation cleanup - 2026-10-06

- Fixed literal line-break artifacts in the public updater README.
- Updated roadmap items to reflect SHA-256 verification now implemented in the private candidate; public release documentation remains on v0.1.23 until an authorized package release.

