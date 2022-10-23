---
title: Downloads
author: Justin Clift
date: []
slug: dl
categories: []
tags: []
---

([**Please** consider sponsoring us on Patreon](https://www.patreon.com/db4s) :smile:)

## Windows

Our latest release (3.12.2) for Windows:

* [DB Browser for SQLite - Standard installer for 32-bit Windows](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.12.2-win32.msi)
* [DB Browser for SQLite - .zip (no installer) for 32-bit Windows](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.12.2-win32.zip)
* [DB Browser for SQLite - Standard installer for 64-bit Windows](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.12.2-win64.msi)
* [DB Browser for SQLite - .zip (no installer) for 64-bit Windows](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.12.2-win64.zip)

### Windows PortableApp

* [DB Browser for SQLite - PortableApp](https://download.sqlitebrowser.org/SQLiteDatabaseBrowserPortable_3.12.2_English.paf.exe)


**Note** - If for any reason the standard Windows release does not work
(e.g. gives an error), try a nightly build ([below](#nightly-builds)).

Nightly builds often fix bugs reported after the last release. :smile:

## macOS

Our latest release (3.12.2) for macOS:

* [DB Browser for SQLite (Intel)](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.12.2.dmg)
* [DB Browser for SQLite (Apple Silicon)](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-arm64-3.12.2.dmg)

### Homebrew

If you prefer using Homebrew for macOS, our latest release can be installed via [Homebrew Cask](https://caskroom.github.io/ "Homebrew Cask"):

    brew install --cask db-browser-for-sqlite

## Nightly builds

Download nightly builds for Windows and macOS here:

* https://nightlies.sqlitebrowser.org/latest

## Linux

Our latest release is available as an AppImage, Snap packages, and distribution specific packages:

### AppImage

* [DB_Browser_for_SQLite-v3.12.2-x86_64.AppImage](https://download.sqlitebrowser.org/DB_Browser_for_SQLite-v3.12.2-x86_64.AppImage)

Remember to change it's permission bits to be executable before you run it. :smile:

### Snap packages

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/sqlitebrowser)

#### Snap Release build

     snap install sqlitebrowser

#### Snap Nightly builds

     snap install sqlitebrowser --devmode

Other distribution specific instructions:

### Arch Linux

Arch Linux provides an [up to date version](https://www.archlinux.org/packages/community/x86_64/sqlitebrowser/)

Install with the following command:
    
    sudo pacman -S sqlitebrowser

### Fedora

Install for Fedora (i386 and x86_64) by issuing the following command:

    sudo dnf install sqlitebrowser
    
### openSUSE

    sudo zypper install sqlitebrowser

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
