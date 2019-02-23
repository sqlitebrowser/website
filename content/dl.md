---
title: Downloads
author: Justin Clift
date: []
slug: dl
categories: []
tags: []
---

## Windows

Our latest release (3.11.1) for Windows:

* [DB Browser for SQLite - Standard installer for 32-bit Windows & Windows XP](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.1-win32.msi)
* [DB Browser for SQLite - .zip (no installer) for 32-bit Windows & Windows XP](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.1-win32.zip)
* [DB Browser for SQLite - Standard installer for 64-bit Windows](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.1-win64.msi)
* [DB Browser for SQLite - .zip (no installer) for 64-bit Windows](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.1-win64.zip)
* Note - There's no PortableApp version for 3.11.1 (yet).  It'll hopefully be ready in a few days.

Previous release (3.10.1) PortableApp:

* [DB Browser for SQLite - PortableApp](https://download.sqlitebrowser.org/SQLiteDatabaseBrowserPortable_3.10.1_English.paf.exe)

**Note** - If for any reason the standard Windows release does not work
(e.g. gives an error), try a nightly build ([below](#nightly-builds)).

Nightly builds often fix bugs reported after the last release. :smile:

## macOS

Our latest release (3.11.1) for macOS:

* [DB Browser for SQLite](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.1v2.dmg)

### Homebrew

If you prefer using Homebrew for macOS, our latest release can be installed via [Homebrew Cask](https://caskroom.github.io/ "Homebrew Cask"):

    brew cask install db-browser-for-sqlite

## Nightly builds

Download nightly builds for Windows and macOS here:

* https://nightlies.sqlitebrowser.org/latest

## Linux

DB Browser for SQLite works well on Linux.

### Arch Linux

Arch Linux provides a package through pacman.

### Fedora

Install for Fedora (i386 and x86_64) by issuing the following command:

    sudo dnf install sqlitebrowser

### Debian

Note that Debian focuses more on stability rather than newest features. Therefore packages will typically contain some older version, compared to the latest release.

Update the cache using:

    sudo apt-get update

Install the package using:

    sudo apt-get install sqlitebrowser


### Ubuntu and Derivatives

#### Stable release

For Ubuntu and derivaties, [@deepsidhu1313](https://github.com/deepsidhu1313)
provides a PPA with the latest release here:

* https://launchpad.net/~linuxgndu/+archive/ubuntu/sqlitebrowser

To add this ppa just type in these commands in terminal:

    sudo add-apt-repository -y ppa:linuxgndu/sqlitebrowser

Then update the cache using:

    sudo apt-get update

Install the package using:

    sudo apt-get install sqlitebrowser

Ubuntu 14.04.X, 15.04.X, 15.10.X and 16.04.X are supported for now (until
Launchpad decides to discontinue building for any series).

Ubuntu Precise (12.04) and Utopic (14.10) are not supported:
* Precise does not have a new enough Qt package in its repository by default,
  which is a dependency
* Launchpad does not support Utopic any more, which has reached its End of
  Life

#### Nightly builds

Nightly builds are available here:

* https://launchpad.net/~linuxgndu/+archive/ubuntu/sqlitebrowser-testing

To add this ppa, type these commands into the terminal:

    sudo add-apt-repository -y ppa:linuxgndu/sqlitebrowser-testing

Then update the cache using:

    sudo apt-get update

Install the package using:

    sudo apt-get install sqlitebrowser

### Other Linux

On others, compile DB4S using the instructions
in [BUILDING.md](https://github.com/sqlitebrowser/sqlitebrowser/blob/master/BUILDING.md#build-instructions-and-requirements).

## FreeBSD

DB Browser for SQLite works well on FreeBSD, and there is a port for it (thanks
to [lbartoletti](https://github.com/lbartoletti) :smile:).  DB4S can be installed
using either this command:

    make -C /usr/ports/databases/sqlitebrowser install

or this command:

    pkg install sqlitebrowser

## Snap packages

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/sqlitebrowser)

#### Snap Nightlies

     snap install sqlitebrowser --devmode

#### Snap Stable

     snap install sqlitebrowser
