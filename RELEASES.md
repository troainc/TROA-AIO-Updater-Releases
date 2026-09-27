## v0.1.21

- Adds owner-controlled Overseer+ and GridVault+ package checks.
- Consolidates package confirmation into one updater state file instead of per-package release marker files.

## v0.1.20

- Restart-loop repair: a managed package is identified by its recorded release asset rather than by a changing GitHub filename.
- If a legacy package has no marker, it is verified once; an identical package does not trigger another restart.

# Releases

## v0.1.1

- Torch startup-path repair and corrected package filename: TROA-AIO-Updater.zip.
- Private release asset updated; public repository remains documentation-only.

## v0.1.0

- Initial private distribution package for Torch.
- Public repository contains release information only; packages are published through the private project release channel.

## v0.1.19

- Final operator logging and automatic post-download restart notice release.

## v0.1.22

- Removes updater-created .zip.previous files and retains prior-release details in the single readable state file.
