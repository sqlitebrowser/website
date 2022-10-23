---
title: Apple Silicon (M1/M2/etc) macOS package available
author: Justin Clift
date: '2022-10-24'
slug: apple-silicon-macos-package-available
categories:
  - db4s
---

We are proud to present... the Apple Silicon (arm64) version of DB Browser for SQLite
v3.12.2:

* https://download.sqlitebrowser.org/DB.Browser.for.SQLite-arm64-3.12.2.dmg
  * 0c2076e4479cb9db5c85123cfe9750641f92566694ff9f6c99906321a2c424e8 (SHA256 checksum)

If you're using one of Apple's M1 or M2 based macOS devices, then this native
Apple Silicon version of DB4S should work a bit better than our existing Intel
based download.

Additionally, our nightly builds for macOS now have both Intel and Apple Silicon
(arm64) downloads available:

Nightly builds using SQLite (no encryption):

* [DB.Browser.for.SQLite-arm64.dmg](https://nightlies.sqlitebrowser.org/latest/DB.Browser.for.SQLite-arm64.dmg)
* [DB.Browser.for.SQLite-intel.dmg](https://nightlies.sqlitebrowser.org/latest/DB.Browser.for.SQLite-intel.dmg)

Nightly builds using SQLCipher (does encryption):

* [DB.Browser.for.SQLite-sqlcipher-arm64.dmg](https://nightlies.sqlitebrowser.org/latest/DB.Browser.for.SQLite-sqlcipher-arm64.dmg)
* [DB.Browser.for.SQLite-sqlcipher-intel.dmg](https://nightlies.sqlitebrowser.org/latest/DB.Browser.for.SQLite-sqlcipher-intel.dmg)

This is thanks to our [Patreon supporters](https://nightlies.sqlitebrowser.org/latest/DB.Browser.for.SQLite-sqlcipher-intel.dmg) (for the M1 Mac Mini), and our many Community members providing insight,
instructions, and all around assistance getting things working on Apple Silicon. :smile:
