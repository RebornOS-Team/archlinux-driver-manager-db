# Archlinux Driver Manager

A tool to detect and install drivers for hardware on Arch Linux.

[![Discord Server](https://dcbadge.vercel.app/api/server/cU5s6MPpQH?style=flat)](https://discord.gg/cU5s6MPpQH)
[![License: MPL v2.0](https://img.shields.io/badge/License-MPL--2.0-blue.svg)](https://www.mozilla.org/en-US/MPL/2.0/)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/rebornos-developers/archlinux-driver-manager-db)
[![Release](https://github.com/RebornOS-Developers/archlinux-driver-manager-db/actions/workflows/release.yml/badge.svg)](https://github.com/RebornOS-Developers/archlinux-driver-manager-db/actions/workflows/release.yml)
[![Pre-Release (Git)](https://github.com/RebornOS-Developers/archlinux-driver-manager-db/actions/workflows/pre_release.yml/badge.svg)](https://github.com/RebornOS-Developers/archlinux-driver-manager-db/actions/workflows/pre_release.yml)

> **Note**: This project should carry any RebornOS-specific configuration for `archlinux-driver-manager`. Refer to the [archlinux-driver-manager](https://github.com/RebornOS-Developers/archlinux-driver-manager) project for other non-RebornOS-specific files.

## Cloning

In order to download the source code to your local computer for testing, or for development, you can clone from the remote repository using either SSH, or HTTPS. Below are instructions on how to do so using Gitlab hosted code as remote.

### HTTPS

```bash
git clone https://github.com/RebornOS-Developers/archlinux-driver-manager-db.git 
```

OR

### SSH

```bash
git clone git@github.com:RebornOS-Developers/archlinux-driver-manager-db.git
```

## Packaging

Change to the project directory (`cd archlinux-driver-manager-db`) and run any of the below scripts:
- `sh packaging/setup.sh <MODE>`: Builds and installs a package
- `sh packaging/build-package.sh <MODE>`: Just builds a package without installing it locally
- `sh packaging/install-package.sh <MODE>`: Just installs a package locally, except if no built package is detected, a package is built.

- where `<MODE>` can be one of the below
     1. `local`: Selects *archlinux-driver-manager-db-local* from the local project that you have cloned already.
     2. `git`: Selects *archlinux-driver-manager-db-git* from the latest git commit.
     3. `stable`: Selects *archlinux-driver-manager-db* from the git tag corresponding to the [`pkgver` specified in the PKGBUILD](https://github.com/RebornOS-Developers/archlinux-driver-manager-db/blob/main/packaging/archlinux-driver-manager-db/PKGBUILD#L5). If `pkgver=0.0.1`, then the git tag `v0.0.1` is used for packaging. 
     
> **Note**: Any additional parameters passed to the above scripts are automatically sent to `makepkg` or `pacman` (whichever is applicable).
