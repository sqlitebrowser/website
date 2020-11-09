---
title: Version 3.11.2 released
date: '2019-04-04'
slug: version-3-11-2-released
categories: []
tags:
  - 3.11.x
---

**This is a minor bug fix release in the 3.11.x series**

## Bug fixes and enhancements since 3.11.1

* Enable 'Edit Database Cell' when view is editable ([#1756](https://github.com/sqlitebrowser/sqlitebrowser/issues/1756))
* DB browser crashes when I try to attach additional database to current one ([#1758](https://github.com/sqlitebrowser/sqlitebrowser/issues/1758))
* CASE-SENSITIVITY: Error importing data from SQL file: cannot start a transaction within a transaction ([#1764](https://github.com/sqlitebrowser/sqlitebrowser/issues/1764))
* Cell edit window considers binary data to be text/numeric if first byte is in ascii range ([#1772](https://github.com/sqlitebrowser/sqlitebrowser/issues/1772))
* Crashes when browsing a empty view with view editing enabled ([#1774](https://github.com/sqlitebrowser/sqlitebrowser/issues/1774))
* Trying to save after successfull import fails ([#1777](https://github.com/sqlitebrowser/sqlitebrowser/issues/1777))
* Attach encrypted database results in Out of Memory Error ([#1799](https://github.com/sqlitebrowser/sqlitebrowser/issues/1799))
* File is not a database ([#1814](https://github.com/sqlitebrowser/sqlitebrowser/issues/1814))
* Can't remove password from an encrypted database any more ([#1829](https://github.com/sqlitebrowser/sqlitebrowser/issues/1829))
* grammar: Fix keywords as table name and keywords as column name ([1a59c8cbda47684dfc0b55283fc6fdb396adc832](https://github.com/sqlitebrowser/sqlitebrowser/commit/1a59c8cbda47684dfc0b55283fc6fdb396adc832))
* Updated translation strings
  * Korean ([#1600](https://github.com/sqlitebrowser/sqlitebrowser/issues/1600))
  * Brazilian Portuguese ([#1830](https://github.com/sqlitebrowser/sqlitebrowser/issues/1830))
  * Italian ([#1833](https://github.com/sqlitebrowser/sqlitebrowser/issues/1833))
  * German ([e2ad5459d569801f9a635391f774e81ca1009e85](https://github.com/sqlitebrowser/sqlitebrowser/commit/e2ad5459d569801f9a635391f774e81ca1009e85))
* Include SQLite 3.27.2 instead of SQLite 3.27.1
* Include [SQLCipher 4.1.0](https://discuss.zetetic.net/t/sqlcipher-4-1-0-release/3490) instead of 4.0.1
  
## Downloads

* [DB.Browser.for.SQLite-3.11.2-win32.msi](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.2-win32.msi) - Standard (MSI) installer for Win32 and WinXP
* [DB.Browser.for.SQLite-3.11.2-win32.zip](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.2-win32.zip) - .zip (no installer) for Win32 and WinXP
* [DB.Browser.for.SQLite-3.11.2-win64.msi](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.2-win64.msi) - Standard (MSI) installer for Win64
* [DB.Browser.for.SQLite-3.11.2-win64.zip](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.2-win64.zip) - .zip (no installer) for Win64
* [DB.Browser.for.SQLite-3.11.2.dmg](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.2.dmg) - For macOS


### SHA256SUMS
* DB.Browser.for.SQLite-3.11.2-win32.msi
  * 0a660c8eefdfbb8be6cf8be2abe223b0149ce8723cc1c19a36b88198be071abe
* DB.Browser.for.SQLite-3.11.2-win32.zip
  * bdfcd05bf1890a3336a1091c6e9740d582167494d0010da061f9effab2243b9e
* DB.Browser.for.SQLite-3.11.2-win64.msi
  * 9db9d0c69c1372f09ef54599e3f87af3e28057a20c2bd6f59787d1cf16edb742
* DB.Browser.for.SQLite-3.11.2-win64.zip
  * c6117e9d75bde6e0a6cbf51ee2356daa0ce41ca2dd3a6f3d1c221a36104531a0
* DB.Browser.for.SQLite-3.11.2.dmg
  * 022536d420dca87285864a4a948b699d01430721b511722bcf9c8713ab946776