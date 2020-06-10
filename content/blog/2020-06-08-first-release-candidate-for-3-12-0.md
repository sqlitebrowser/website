---
title: First release candidate for 3.12.0
author: Justin Clift
date: '2020-06-08'
slug: first-release-candidate-for-3-12-0
categories:
  - db4s
tags:
  - 3.12.x
---
This is the first (and hopefully final), release candidate for DB Browser for SQLite version 3.12.0.

## Downloads

* [DB.Browser.for.SQLite-3.12.0-rc1-win32.msi](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.0-rc1/DB.Browser.for.SQLite-3.12.0-rc1-win32.msi) - Standard installer for 32-bit Windows
* [DB.Browser.for.SQLite-3.12.0-rc1-win32.zip](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.0-rc1/DB.Browser.for.SQLite-3.12.0-rc1-win32.zip) - .zip (no installer) for 32-bit Windows
* [DB.Browser.for.SQLite-3.12.0-rc1-win64.msi](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.0-rc1/DB.Browser.for.SQLite-3.12.0-rc1-win64.msi) - Standard installer for 64-bit Windows
* [DB.Browser.for.SQLite-3.12.0-rc1-win64.zip](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.0-rc1/DB.Browser.for.SQLite-3.12.0-rc1-win64.zip) - .zip (no installer) for 64-bit Windows
* [DB.Browser.for.SQLite-3.12.0-rc1.dmg](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.0-rc1/DB.Browser.for.SQLite-3.12.0-rc1.dmg) - Standard package for macOS

## Support for pre-3.11 project file format

In v3.11, the project file format was changed to support multiple sort columns (#1593), the database read-only state and the saving of configured conditional formats, while the handling of project files itself was improved too.  While v.3.11 could read project files from previous versions, all saving of project files was done using the new project file format.

v3.12 will be the last version to support the pre-3.11 project file format - v3.13 won't be able to read the older format.

## Changes

The changes in this from the 3.12.0-alpha1 release:

* [#1968](https://github.com/sqlitebrowser/sqlitebrowser/issues/1968) - Drop close buttons on every Execute SQL tab(x).
* [#2153](https://github.com/sqlitebrowser/sqlitebrowser/pull/2153) - Show a useful icon in SQL tabs
* [#2174](https://github.com/sqlitebrowser/sqlitebrowser/pull/2174) - Open SQL tabs for modifying views and triggers
* [#2180](https://github.com/sqlitebrowser/sqlitebrowser/issues/2180) - Crash when -t option specifies missing table
* [#2184](https://github.com/sqlitebrowser/sqlitebrowser/pull/2184) - Fix logo issues
* [#2193](https://github.com/sqlitebrowser/sqlitebrowser/pull/2193) - Update German translation
* [#2195](https://github.com/sqlitebrowser/sqlitebrowser/pull/2195) - Install the AppStream file to the canonical location
* [#2207](https://github.com/sqlitebrowser/sqlitebrowser/issues/2207) - Open a set of SQL-Files
* [#2224](https://github.com/sqlitebrowser/sqlitebrowser/pull/2224) - Consistent naming of DB Browser for SQLite
* [#2233](https://github.com/sqlitebrowser/sqlitebrowser/issues/2233) - Minor: Change "Filter in all columns" => "Filter in any column"
* [#2235](https://github.com/sqlitebrowser/sqlitebrowser/pull/2235) - Avoid unchanged translation of keyboard shortcuts to work around problems
* [#2240](https://github.com/sqlitebrowser/sqlitebrowser/pull/2240) - Rearrange preferences database
* [c0cc696](https://github.com/sqlitebrowser/sqlitebrowser/commit/c0cc6968fd8b139436f7f688c02473eab3d2b4e3) -  Use port 443 for DBHub.io traffic, to be more enterprise firewall friendly
* [#2270](https://github.com/sqlitebrowser/sqlitebrowser/pull/2270) - Application icon cleanup
* [#2275](https://github.com/sqlitebrowser/sqlitebrowser/pull/2275) - Update to Windows Icon Generation script

There are a few text strings that still need an updated translation.  We'll get those done over the next few days, and as long as no serious bugs turn up we'll make the final release next weekend or so.

## SHA256SUMS
* DB.Browser.for.SQLite-3.12.0-rc1-win32.msi
  * 28bfb79c675d826d04bfca097e3626cb9304a6151a6b3f7558e1840aee183707
* DB.Browser.for.SQLite-3.12.0-rc1-win32.zip
  * 04e8aa4c9a862e82a0f6ee018fea4195f00205769cb75278908ef0fb58965297
* DB.Browser.for.SQLite-3.12.0-rc1-win64.msi
  * d0a3a64b1cd7052daf9d06b64738177d66fc5d06035e85f0a713f3c713650288
* DB.Browser.for.SQLite-3.12.0-rc1-win64.zip
  * 4210b2e78e4ab3dae11a9260f2a96711584f1186163f52983d0a010489ca4b12
* DB.Browser.for.SQLite-3.12.0-rc1.dmg
  * 474906b165f95ff1655a87bc1a6c7366636e31f9b87c5e52023f259e353bd259