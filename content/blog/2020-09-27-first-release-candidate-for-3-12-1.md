---
title: First release candidate for 3.12.1
author: Justin Clift
date: '2020-09-27'
slug: first-release-candidate-for-3-12-1
categories:
  - db4s
tags:
  - 3.12.x
---

This is the first, and hopefully only :wink:, release candidate for DB Browser for SQLite version 3.12.1.

## Downloads

* [DB.Browser.for.SQLite-3.12.1-rc1-win32.msi](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.1-rc1/DB.Browser.for.SQLite-3.12.1-rc1-win32.msi) - Standard installer for 32-bit Windows
* [DB.Browser.for.SQLite-3.12.1-rc1-win32.zip](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.1-rc1/DB.Browser.for.SQLite-3.12.1-rc1-win32.zip) - .zip (no installer) for 32-bit Windows
* [DB.Browser.for.SQLite-3.12.1-rc1-win64.msi](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.1-rc1/DB.Browser.for.SQLite-3.12.1-rc1-win64.msi) - Standard installer for 64-bit Windows
* [DB.Browser.for.SQLite-3.12.1-rc1-win64.zip](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.1-rc1/DB.Browser.for.SQLite-3.12.1-rc1-win64.zip) - .zip (no installer) for 64-bit Windows
* [DB.Browser.for.SQLite-3.12.1-rc1.dmg](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.1-rc1/DB.Browser.for.SQLite-3.12.1-rc1.dmg) - Standard package for macOS

The changes in this over the 3.12.0 release include:

## Enhancements
* Completely reworked interface for accessing DBHub.io
* Add .Net DateTime.Ticks to list of supported display formats ([#2378](https://github.com/sqlitebrowser/sqlitebrowser/issues/2378))
* Add more options for setting font sizes ([#2306](https://github.com/sqlitebrowser/sqlitebrowser/issues/2306))
* New predefined settings for simplified window layout ([#2307](https://github.com/sqlitebrowser/sqlitebrowser/issues/2307))

## Bug fixes
* Fix loading of project files with empty filter values ([#2288](https://github.com/sqlitebrowser/sqlitebrowser/issues/2288))
* Fix initial table view when using the -t / --table command line option ([#2113](https://github.com/sqlitebrowser/sqlitebrowser/issues/2113))
* Add status message when opening a file from the recent file list ([4dfe4f76db3667e67c112cfdd5e37a2f7f8bc6d1](https://github.com/sqlitebrowser/sqlitebrowser/commit/4dfe4f76db3667e67c112cfdd5e37a2f7f8bc6d1))
* Make sure to not show "NULL" for empty but non-NULL values in the Edit dialog ([#2204](https://github.com/sqlitebrowser/sqlitebrowser/issues/2204))
* Fix plot being drawn before all data is loaded ([#2286](https://github.com/sqlitebrowser/sqlitebrowser/issues/2286))
* Restore original default for having condition format in filter line ([f28ecc0133a2859e750fac01fccc685e2eea7508](https://github.com/sqlitebrowser/sqlitebrowser/commit/f28ecc0133a2859e750fac01fccc685e2eea7508))
* Fix default font in the format toolbar ([c4b2ffceb32c9c826268702c14b5f3c67c55c45e](https://github.com/sqlitebrowser/sqlitebrowser/commit/c4b2ffceb32c9c826268702c14b5f3c67c55c45e))
* Improve binary detection for cases starting by chance by a BOM ([#2197](https://github.com/sqlitebrowser/sqlitebrowser/issues/2197))
* Make sure the order of the statements in the SQL log is correct ([05db9014c2b7541dd21a151aa0512e5f20f47ce1](https://github.com/sqlitebrowser/sqlitebrowser/commit/05db9014c2b7541dd21a151aa0512e5f20f47ce1))
* Fix executing selected SQL text when there are multi-byte characters ([#2311](https://github.com/sqlitebrowser/sqlitebrowser/issues/2311))
* Fix executing SQL queries with compound operators ([#2316](https://github.com/sqlitebrowser/sqlitebrowser/issues/2316))
* Fix SQL import of files with BOM ([#2323](https://github.com/sqlitebrowser/sqlitebrowser/issues/2323))
* Also update schema when clicking the Refresh button in Browse Data tab ([16c3d8d13ee997d0ce15737110826c484f8c8879](https://github.com/sqlitebrowser/sqlitebrowser/commit/16c3d8d13ee997d0ce15737110826c484f8c8879))
* Select column in table results when column header is pressed ([#2343](https://github.com/sqlitebrowser/sqlitebrowser/issues/2343))
* Tweak the output wording for command line options ([#1069](https://github.com/sqlitebrowser/sqlitebrowser/issues/1069))
* Remove the default property of the cancel button in the "Fetching data..." dialog ([#2383](https://github.com/sqlitebrowser/sqlitebrowser/issues/2383))

# Building and packaging
* Fix CMake warning during compilation ([115aa00ac5f79a6d24618daa06e5402ff1a6adbb](https://github.com/sqlitebrowser/sqlitebrowser/commit/115aa00ac5f79a6d24618daa06e5402ff1a6adbb))
* snap: Add environment variables to set Qt theme ([7b5d65220557f73f2ce36ceee80f1e5ba65160c6](https://github.com/sqlitebrowser/sqlitebrowser/commit/7b5d65220557f73f2ce36ceee80f1e5ba65160c6))

# Platform specific
* No longer force Light theme on macOS when "Follow the desktop style" is chosen ([508118ffd072e8f5507e4d6beaa52be8d51d4deb](https://github.com/sqlitebrowser/sqlitebrowser/commit/508118ffd072e8f5507e4d6beaa52be8d51d4deb))
* Keep registry key consistent on Windows ([#2328](https://github.com/sqlitebrowser/sqlitebrowser/issues/2328))
* Allow use of integrated graphics card instead of high performance graphics card in macOS ([#2377](https://github.com/sqlitebrowser/sqlitebrowser/issues/2377))
* Use native path separators in Preferences dialog ([f38b829f5695bb95fbb50cb203376e3013bf2001](https://github.com/sqlitebrowser/sqlitebrowser/commit/f38b829f5695bb95fbb50cb203376e3013bf2001))
* Added message box for informative command line arguments for Windows ([#1069](https://github.com/sqlitebrowser/sqlitebrowser/issues/1069))

# Translations
* Remove all translations of key shortcuts ([0070a158617898ba4602ae04c451cec35df640fb](https://github.com/sqlitebrowser/sqlitebrowser/commit/0070a158617898ba4602ae04c451cec35df640fb))
* Update of the Korean translation ([#2329](https://github.com/sqlitebrowser/sqlitebrowser/issues/2329), [82accb2720fa06b6e2ba330338fa362c39305a3e](https://github.com/sqlitebrowser/sqlitebrowser/commit/82accb2720fa06b6e2ba330338fa362c39305a3e))
* Update of the Spanish translation ([551a420791dcfa78dd14a954f7dbea00dd5eef0e](https://github.com/sqlitebrowser/sqlitebrowser/commit/551a420791dcfa78dd14a954f7dbea00dd5eef0e))
* Update of the Japanese translation ([#2407](https://github.com/sqlitebrowser/sqlitebrowser/issues/2407))
* Update of the French translation ([2803da38b1e36fed59e8e56c13c201f445bda516](https://github.com/sqlitebrowser/sqlitebrowser/commit/2803da38b1e36fed59e8e56c13c201f445bda516))
* Update of the Arabic translation ([1dfa70c209453ab3fdce7991377fdba94bafccff](https://github.com/sqlitebrowser/sqlitebrowser/commit/1dfa70c209453ab3fdce7991377fdba94bafccff))
* Fixes in the Spanish translation ([4791b99afff1691f2770f31e33f8ac7ca5778898](https://github.com/sqlitebrowser/sqlitebrowser/commit/4791b99afff1691f2770f31e33f8ac7ca5778898), [5d85ca1a5388228af0ca092b0f51397743b46563](https://github.com/sqlitebrowser/sqlitebrowser/commit/5d85ca1a5388228af0ca092b0f51397743b46563), [454fd4a50b210c9e434bb57b54b2e4e9bf3ddd3b](https://github.com/sqlitebrowser/sqlitebrowser/commit/454fd4a50b210c9e434bb57b54b2e4e9bf3ddd3b))
* Fixes in the French translation ([90d33c6299a447ee455013adce3af79f99b22a68](https://github.com/sqlitebrowser/sqlitebrowser/commit/90d33c6299a447ee455013adce3af79f99b22a68), [03752066ac7675ca2ca2b350935b0944e0e7247f](https://github.com/sqlitebrowser/sqlitebrowser/commit/03752066ac7675ca2ca2b350935b0944e0e7247f))

## SHA256SUMS
* DB.Browser.for.SQLite-3.12.1-rc1-win32.msi
  * 403cb37170550ff761ed5a7d24bbf75461d8a7b3e841d3265b858f23fe6142f6
* DB.Browser.for.SQLite-3.12.1-rc1-win32.zip
  * c2cfa37a4a3a081fdacd6dcf704240b3019949e4bd8b3f3a5d302f4effdfe03c
* DB.Browser.for.SQLite-3.12.1-rc1-win64.msi
  * 463f0f710fa491ad49efcf00f138e4c3fe1764be8a6dd39c424f6fc242447337
* DB.Browser.for.SQLite-3.12.1-rc1-win64.zip
  * 884b69d7e463dc416d1d57e804dfbdad6c434c4c3697ee1f66b5f093e6267b43
* DB.Browser.for.SQLite-3.12.1-rc1.dmg
  * 74462728b6fd9a79a0f097f4e07d30182f9b09e1ed35ab07db448314fbc95e38