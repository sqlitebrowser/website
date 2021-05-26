---
title: Version 3.12.2 released
author: Justin Clift
date: '2021-05-18'
slug: version-3-12-2-released
categories:
  - db4s
tags:
  - 3.12.x
---

This is a minor maintenance release, primarily to update the internal certificates for
anonymous communication with the DBHub.io servers.

You **don't** need to upgrade unless you're using DBHub.io anonymously.  If you're using DBHub.io
with your own client certificate, this upgrade won't really do much either. :smile:

The changes in this over the 3.12.1 release include:

* Fix saving the list of extensions in the Preferences dialog ([bd0e1feead6bb446f8a703338aa9893bf281e5b4](https://github.com/sqlitebrowser/sqlitebrowser/commit/bd0e1feead6bb446f8a703338aa9893bf281e5b4))
* Corrected a typo in the French translation ([3bbd4ee271f98301476143749f7bf4abed052efe](https://github.com/sqlitebrowser/sqlitebrowser/commit/3bbd4ee271f98301476143749f7bf4abed052efe))
* Updated the included SQLite and SQLCipher libraries to their latest release (SQLite 3.35.5, SQLCipher 4.4.3)
* Updated the "public" certificate, used for communicating with DBHub.io anonymously ([d85953c291b5f0bb467e2c12dfa4438f997d4f28](https://github.com/sqlitebrowser/sqlitebrowser/commit/d85953c291b5f0bb467e2c12dfa4438f997d4f28))

## Downloads

* [DB.Browser.for.SQLite-3.12.2-win32.msi](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.12.2-win32.msi) - Standard (MSI) installer for Win32
* [DB.Browser.for.SQLite-3.12.2-win32.zip](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.12.2-win32.zip) - .zip (no installer) for Win32
* [DB.Browser.for.SQLite-3.12.2-win64.msi](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.12.2-win64.msi) - Standard (MSI) installer for Win64
* [DB.Browser.for.SQLite-3.12.2-win64.zip](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.12.2-win64.zip) - .zip (no installer) for Win64
* [DB.Browser.for.SQLite-3.12.2.dmg](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.12.2.dmg) - For macOS
* [SQLiteDatabaseBrowserPortable_3.12.2_English.paf.exe](https://download.sqlitebrowser.org/SQLiteDatabaseBrowserPortable_3.12.2_English.paf.exe) - PortableApp for Windows

## SHA256SUMS
* DB.Browser.for.SQLite-3.12.2-win32.msi
  * 2b87a0ca1b14f436f2dc2cbfaa380249e754c3c87c81b6648a513f75d3c73368
* DB.Browser.for.SQLite-3.12.2-win32.zip
  * 9344bcd50865663674f11c1d8297c0d2b4a4f7ced0a459c9e71e89382549454f
* DB.Browser.for.SQLite-3.12.2-win64.msi
  * 723d601f125b0d2402d9ea191e4b310345ec52f76b61e117bf49004a2ff9b8ae
* DB.Browser.for.SQLite-3.12.2-win64.zip
  * 559edc274a2823264e886159eaa36332fd5af1f2f4b86ba2a5ef485b6420ab54
* DB.Browser.for.SQLite-3.12.2.dmg
  * 546d57b6c88c2be7517759c016c0bf0313dfcc14adfcb43967f3c5d24657f366
* SQLiteDatabaseBrowserPortable_3.12.2_English.paf.exe
  * a597b791949c260e31908d00bde474cbb4b16d55120be92ee6e0d7c08be56809
  