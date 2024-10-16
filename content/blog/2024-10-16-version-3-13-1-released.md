---
title: Version 3.13.1 released
author:
  - SeongTae Jeong
  - Justin Clift
date: '2024-10-16'
slug: version-3-13-1-released
categories:
  - db4s
tags:
  - 3.13.x
---

This is a new release with several improvements to the v3.13.0 release from three months ago. :rocket:

As a special mention, SQLean has a new `time` extension! Check out the following link for more information: https://github.com/nalgeon/sqlean/blob/main/docs/time.md

Thanks to everyone for being part of our Community!

Related Discussion: [TBD]

# Downloads

* [DB.Browser.for.SQLite-v3.13.1-win32.msi](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-v3.13.1-win32.msi) - Standard (MSI) installer for Win32
* [DB.Browser.for.SQLite-v3.13.1-win32.zip](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-v3.13.1-win32.zip) - .zip (no installer) for Win32
* [DB.Browser.for.SQLite-v3.13.1-win64.msi](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-v3.13.1-win64.msi) - Standard (MSI) installer for Win64
* [DB.Browser.for.SQLite-v3.13.1-win64.zip](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-v3.13.1-win64.zip) - .zip (no installer) for Win64
* [DB.Browser.for.SQLite-v3.13.1.dmg](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-v3.13.1.dmg) - For macOS Universal (both Apple Silicon and Intel)
* [DB.Browser.for.SQLite-v3.13.1-x86.64.AppImage](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-v3.13.1-x86.64.AppImage) - AppImage for Linux

# Changelog

### Added
- Add links to the wiki as help for many dialogs ([7af1256](https://github.com/sqlitebrowser/sqlitebrowser/commit/7af12565e77a5d88a0530a019aedd210763027b7), [b5abc86](https://github.com/sqlitebrowser/sqlitebrowser/commit/b5abc868aef3cc5ca908eb0af61e182205aa2291))

### Changed
- Change the default to install a shortcut to the Start menu when installing on Windows ([623bec6](https://github.com/sqlitebrowser/sqlitebrowser/commit/623bec64ce6e86f5b020b0370eeda86369d10157))
- Improve icon image for links in 'Help' menu ([#3693](https://github.com/sqlitebrowser/sqlitebrowser/issues/3693), [027c6a8](https://github.com/sqlitebrowser/sqlitebrowser/commit/027c6a8be8238102e1c4f483615dbd749251c2b6))
- Pragma names and values can now be translated ([#3697](https://github.com/sqlitebrowser/sqlitebrowser/pull/3697), [bf62f3a](https://github.com/sqlitebrowser/sqlitebrowser/commit/bf62f3afc4ad820c34e1be212baa6a4c24694baf), [ad00ad4](https://github.com/sqlitebrowser/sqlitebrowser/commit/ad00ad43059a28cd1a8dc81ed8c210d77b098b70))
- Remove trailing characters when copying a single cell ([#3735](https://github.com/sqlitebrowser/sqlitebrowser/issues/3735), [20f481a](https://github.com/sqlitebrowser/sqlitebrowser/commit/20f481a1887e92ab335901adbd41fdc70274f493))
- Update AppImage binary to use the latest SQLCipher library ([#3744](https://github.com/sqlitebrowser/sqlitebrowser/issues/3744), [21ba2d0](https://github.com/sqlitebrowser/sqlitebrowser/commit/21ba2d0eee164bfcacde884d5119650ba77ca8d7))
- When editing the DB cells, expanded queries with parameters are included in the SQL Log ([ac3209f](https://github.com/sqlitebrowser/sqlitebrowser/commit/ac3209f9e1e0b1386cebea9ab60c71d84632f5c1))

### Fixed
-  ExtendedTableWidget
  - Fix an issue that prevented autocomplete from working in some race conditions ([#2567](https://github.com/sqlitebrowser/sqlitebrowser/issues/2567), [#3706](https://github.com/sqlitebrowser/sqlitebrowser/issues/3706))
  - Use Tab to close autocomplete popup and move to next item ([3aff8c9](https://github.com/sqlitebrowser/sqlitebrowser/commit/3aff8c925e0761e9f4799150d9c45b76ed0b8b19))
  - Troubleshoot 'Copy as SQL' action on a cell results in string being copied ([#1952](https://github.com/sqlitebrowser/sqlitebrowser/issues/1952), [1ebe7bf](https://github.com/sqlitebrowser/sqlitebrowser/commit/1ebe7bf2505d91876da6f0bb29d597edc3834015))

- Global
  - Fix "Argument Missing" error in Korean translation ([#3635](https://github.com/sqlitebrowser/sqlitebrowser/issues/3635), [#3692](https://github.com/sqlitebrowser/sqlitebrowser/issues/3692), [cd518de](https://github.com/sqlitebrowser/sqlitebrowser/commit/cd518dee13e60d499d4c34b0b7b1ba1ddb52b26a))
  - Fix an issue that caused apps to crash on some older versions of macOS ([#3691](https://github.com/sqlitebrowser/sqlitebrowser/issues/3691))
  - Fix an issue when freezing after stopping a pragma ([#3742](https://github.com/sqlitebrowser/sqlitebrowser/pull/3742), [15a9620](https://github.com/sqlitebrowser/sqlitebrowser/commit/15a9620d11d96c62084e3702e867430bf0ec4542))
  - Fix an issue with outputting the wrong version on macOS
  - Troubleshooting poor HiDPI support on Windows ([#3684](https://github.com/sqlitebrowser/sqlitebrowser/issues/3684))
  - Troubleshoot SQL queries containing VACUUM that run incorrectly ([#3723](https://github.com/sqlitebrowser/sqlitebrowser/issues/3723), [51784aa](https://github.com/sqlitebrowser/sqlitebrowser/commit/51784aa6ce697ffdd9972744ab76cb6d873592ca))

- MainWindow
  - Fix an issue when selecting queries containing multi-byte strings ([#3731](https://github.com/sqlitebrowser/sqlitebrowser/issues/3731), [f89097c](https://github.com/sqlitebrowser/sqlitebrowser/commit/f89097c25b4984052c83d852dc161628b7f48f2b))

- TableBrowser
  - Fix a bug where the first row was not adjusted ([#3767](https://github.com/sqlitebrowser/sqlitebrowser/issues/3767), [ad690e7](https://github.com/sqlitebrowser/sqlitebrowser/commit/ad690e7c2958df5e96ccb1b73f5c1076d6ec4067))

- Other
  - Fix misleading links to Qt license information ([8361aa5](https://github.com/sqlitebrowser/sqlitebrowser/commit/8361aa58298354c5829583206458e8a11090b50e))
  - Replace 'http' with 'https' in the 'AboutDialog' and 'MainWindow' ([9832a52](https://github.com/sqlitebrowser/sqlitebrowser/commit/9832a52d95001397cc75e9780c0864672b6860c7))
  - Translation
    - German ([#3749](https://github.com/sqlitebrowser/sqlitebrowser/pull/3749), [8e38bf0](https://github.com/sqlitebrowser/sqlitebrowser/commit/8e38bf0b740cc560da563400e4d0a9bd1233a33c))
    - Indonesian ([#3756](https://github.com/sqlitebrowser/sqlitebrowser/pull/3756), [6100595](https://github.com/sqlitebrowser/sqlitebrowser/commit/6100595bc7cebfc89993f72277f7bc7bba8d2d87))
    - Japanese ([#3755](https://github.com/sqlitebrowser/sqlitebrowser/pull/3755), [e0f6aea](https://github.com/sqlitebrowser/sqlitebrowser/commit/e0f6aea00c1cf82922b7f3c7835ecfff0e7d91d5))
    - Korean ([7bbfcf9](https://github.com/sqlitebrowser/sqlitebrowser/commit/7bbfcf97af7d4e482e47bb18f3181d3ce472acd8))
    - Simplified Chinese ([#3761](https://github.com/sqlitebrowser/sqlitebrowser/pull/3761), [9eb0a5a](https://github.com/sqlitebrowser/sqlitebrowser/commit/9eb0a5af1fd0d27fb7d2ec6f2dfa666c4be6bdbf))
    - Spanish ([ac33918](https://github.com/sqlitebrowser/sqlitebrowser/commit/ac3391868dad109743fc4115be31283c34fe1852))


## Dependent library version information for each OS
|     **-**    |                     [**Qt**](https://www.qt.io/)                     |            [**SQLCipher**](https://www.zetetic.net/sqlcipher/)            |            [**SQLite**](https://sqlite.org/)            |         [**SQLean**](https://github.com/nalgeon/sqlean)         |
|:------------:|:--------------------------------------------------------------------:|:-------------------------------------------------------------------------:|:-------------------------------------------------------:|:---------------------------------------------------------------:|
| **AppImage** | [5.15.13](https://www.qt.io/blog/commercial-lts-qt-5.15.13-released) | [4.5.6](https://www.zetetic.net/blog/2024/01/17/sqlcipher-4.5.6-release/) | [3.46.1](https://www.sqlite.org/releaselog/3_46_1.html) |                          Not applicable                         |
|   **macOS**  | [5.15.13](https://www.qt.io/blog/commercial-lts-qt-5.15.13-released) | [4.6.1](https://www.zetetic.net/blog/2024/08/20/sqlcipher-4.6.1-release/) |                      Not applicable                     | [0.27.1](https://github.com/nalgeon/sqlean/releases/tag/0.27.1) |
|  **Windows** |          [5.15.2](https://www.qt.io/blog/qt-5.15.2-released)         | [4.6.1](https://www.zetetic.net/blog/2024/08/20/sqlcipher-4.6.1-release/) | [3.46.1](https://www.sqlite.org/releaselog/3_46_1.html) | [0.27.1](https://github.com/nalgeon/sqlean/releases/tag/0.27.1) |

## SHA256SUMS
- DB.Browser.for.SQLite-v3.13.1-win32.msi
  - e0b9f86d3da4d8d800e144295487e43de306c1bd27f14dccfe41e904736f25f7
- DB.Browser.for.SQLite-v3.13.1-win32.zip
  - 917ad2fa8d36e3bfa3fc85b11a34a8c18d189fbc2289f5a0d3bf41de8a288edc
- DB.Browser.for.SQLite-v3.13.1-win64.msi
  - d023d54b3a5db10c7e896089bb3dbe6e7f4bc4eaa9bbecb34ca414be5970f688
- DB.Browser.for.SQLite-v3.13.1-win64.zip
  - 22375e275ec42d96de1d3b8e9ea4ed86d2a3505c4d0ffcbd1af67aa4003e5e4d
- DB.Browser.for.SQLite-v3.13.1-x86.64.AppImage
  - d6563c5c211a73192da96e3bb11a3bf83a2f3164aa4db83482c0aecf8b751b77
- DB.Browser.for.SQLite-v3.13.1.dmg
  - a641cfbfcc2ce609f07de44a35134dab53485ecc18e6d9afa297b514d74bd75e
