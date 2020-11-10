---
title: Version 3.12.1 released
author: Justin Clift
date: '2020-11-09'
slug: version-3-12-1-released
categories:
  - db4s
tags:
  - 3.12.x
---

This is the first bug fix release for our 3.12.x series.

There aren't any "super critical **must upgrade**" bugs fixed, so updating isn't urgent. :smile:

## Downloads

* [DB.Browser.for.SQLite-3.12.1-win32-v2.msi](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.1/DB.Browser.for.SQLite-3.12.1-win32-v2.msi) - Standard (MSI) installer for Win32 and WinXP
* [DB.Browser.for.SQLite-3.12.1-win32.zip](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.1/DB.Browser.for.SQLite-3.12.1-win32.zip) - .zip (no installer) for Win32 and WinXP
* [DB.Browser.for.SQLite-3.12.1-win64-v2.msi](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.1/DB.Browser.for.SQLite-3.12.1-win64-v2.msi) - Standard (MSI) installer for Win64
* [DB.Browser.for.SQLite-3.12.1-win64.zip](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.1/DB.Browser.for.SQLite-3.12.1-win64.zip) - .zip (no installer) for Win64
* [DB.Browser.for.SQLite-3.12.1-v2.dmg](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.1/DB.Browser.for.SQLite-3.12.1-v2.dmg) - For macOS


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
* Fix not being saved and not applied when modifying database cells in Windows external program ([f2d8f79752f4a20b749c03f3313d9555484a0d71](https://github.com/sqlitebrowser/sqlitebrowser/commit/f2d8f79752f4a20b749c03f3313d9555484a0d71))
* Fix incorrect display of SQL calltips containing non-US-ASCII characters ([9f7851b4d6f31c21a98acf2a01872de654d960af](https://github.com/sqlitebrowser/sqlitebrowser/commit/9f7851b4d6f31c21a98acf2a01872de654d960af))
* Fix to 'Window Layout' options work properly ([#2435](https://github.com/sqlitebrowser/sqlitebrowser/issues/2435))

# Building and packaging
* Fix CMake warning during compilation ([115aa00ac5f79a6d24618daa06e5402ff1a6adbb](https://github.com/sqlitebrowser/sqlitebrowser/commit/115aa00ac5f79a6d24618daa06e5402ff1a6adbb))
* snap: Add environment variables to set Qt theme ([7b5d65220557f73f2ce36ceee80f1e5ba65160c6](https://github.com/sqlitebrowser/sqlitebrowser/commit/7b5d65220557f73f2ce36ceee80f1e5ba65160c6))
* Updated to OpenSSL 1.1.1h for the Windows and macOS builds

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
* Update of the German translation ([#2415](https://github.com/sqlitebrowser/sqlitebrowser/issues/2415))
* Update of the Italian translation ([#2419](https://github.com/sqlitebrowser/sqlitebrowser/issues/2419))
* Update of the Portuguese translation ([#2418](https://github.com/sqlitebrowser/sqlitebrowser/issues/2418))
* Update of the Chinese translation ([#2421](https://github.com/sqlitebrowser/sqlitebrowser/issues/2421))
* Add of the Dutch translation ([#2424](https://github.com/sqlitebrowser/sqlitebrowser/issues/2424))

## SHA256SUMS
* DB.Browser.for.SQLite-3.12.1-win32-v2.msi
  * 6fb72e41cf867e34d1fffdd5b544dc317fbbd25e3c4e56986d62de0c0e46da06
* DB.Browser.for.SQLite-3.12.1-win32.zip
  * c12223a20c4b6e08d086e0d1f54ab0cba9b11b83698ed94f0bdf7728ac67e2f3
* DB.Browser.for.SQLite-3.12.1-win64-v2.msi
  * 512f68ff998564b6a297ee0910563bd97808ce292bf09a840f097faea9be577e
* DB.Browser.for.SQLite-3.12.1-win64.zip
  * 3dd4ccb07f5aabe86b8b12a2544169f9dc15c371f1655ce4072da5a0bd2d2ae3
* DB.Browser.for.SQLite-3.12.1-v2.dmg
  * 45c8789dc77461299a0aeb9eaae2d089086e76eebae31b45b7a0ee48c1c9e898