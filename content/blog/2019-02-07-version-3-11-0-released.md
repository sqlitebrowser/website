---
title: Version 3.11.0 released
date: '2019-02-07'
slug: version-3-11-0-released
categories: []
tags:
  - 3.11.x
---

## Highlights

* DBHub.io improvements
* CSV import: speed, memory usage, usability, type detection and new default rules
* Attach databases
* Menu options for filtering
* JSON and XML editors
* Improvements to the plot UI
* Better copy & paste support
* Dark theme support
* Multi-threaded loading of data
* Default quotes changed to double quotes
* Add Record dialog
* Printing support
* The math extensions for SQLite are included in the windows and macOS installers
  * @SilvioGrosso has kindly created [a video showing how to load the math extensions](https://www.youtube.com/watch?v=UDqowNoFJIo) on windows
  
## Downloads

* [DB.Browser.for.SQLite-3.11.0-win32.msi](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.0-win32.msi) - Standard (MSI) installer for Win32 and WinXP
* [DB.Browser.for.SQLite-3.11.0-win32.zip](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.0-win32.zip) - .zip (no installer) for Win32 and WinXP
* [DB.Browser.for.SQLite-3.11.0-win64.msi](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.0-win64.msi) - Standard (MSI) installer for Win64
* [DB.Browser.for.SQLite-3.11.0-win64.zip](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.0-win64.zip) - .zip (no installer) for Win64
* [DB.Browser.for.SQLite-3.11.0.dmg](https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.0.dmg) - For macOS

### SHA256SUMS
* DB.Browser.for.SQLite-3.11.0-win32.msi
    * d1e28bb123ab758b476f1d1f86be5f9b0c4f4e55a72f9d6e29cfc7924adf44bb
* DB.Browser.for.SQLite-3.11.0-win32.zip
    * f86a16c871394df8ae4d4f80536f2f784a3b250455642f65d352fed56384ef3a
* DB.Browser.for.SQLite-3.11.0-win64.msi
    * 83c8847d0f86354c53b30407fa4af96c9674711bf92c8705e2e4f33897fc9cdd
* DB.Browser.for.SQLite-3.11.0-win64.zip
    * 24390192ec1c48a7399d79001b69aef2f24fc8bd943128028dd0d6116e507d48
* DB.Browser.for.SQLite-3.11.0.dmg
    * 80d66a492ca3ed1f544d3dfea940c222059e9763280491a1d4cac8fb701e5720

### Important Notes

* This release includes SQLCipher 4.0.1, providing even stronger encryption than the previous release.
    * To open a database encrypted with a previous release, make sure to choose the "SQLCipher 3 defaults" in the dialog which asks for the encryption passphrase.
* Our project file format has changed, to make it easier to modify with external tools.
    * Older format files are loaded fine, but all saving of project files is done using the new project file format.

### Notes on the windows installers

We've moved to providing MSI based installers, instead of the previous .exe ones. These new installers include both SQLite and SQLCipher (for optional encryption):

    DB.Browser.for.SQLite-3.11.0-win32.msi
    DB.Browser.for.SQLite-3.11.0-win64.msi

These MSI based installers will automatically detect the previous release of DB4S (3.10.1) and remove it before upgrading.  If you're using an older version of DB4S than that, you'll need to manually remove it first before the upgrade.

Additionally, there's now a .zip version of each. That's useful for people needing to run DB Browser for SQLite without installing it first.

    DB.Browser.for.SQLite-3.11.0-win32.zip
    DB.Browser.for.SQLite-3.11.0-win64.zip

If you're not sure which one to get, try the .msi version first. :smile:

### Note on the macOS installer

The macOS installation now includes the SQLite math extensions (`math.dylib`), located in the `Contents/Extensions/` folder inside `DB Browser for SQLite.app`.

* To use it, you'll need to either manually load it (`Tools` → `Load Extension`), or tell DB4S to automatically load it every time (`Preferences` → `Extensions`).

* macOS doesn't easily allow going inside `.app` folders in file selection dialogs.  To navigate to the correct folder you'll probably need to press <kbd>Shift (⇧)</kbd>+<kbd>Command (⌘)</kbd>+<kbd>g</kbd> when the file selection dialog is open, then give it the path of `/Applications/DB Browser for SQLite.app/Contents/Extensions`.

---

# Change Log

## Enhancements

* Add menu option for attaching database and allow usage of attached databases throughout the entire UI ([532fcd3](https://github.com/sqlitebrowser/sqlitebrowser/commit/532fcd3f6b713e89f7739f25de09c353c61bbe99), [44eb2d4](https://github.com/sqlitebrowser/sqlitebrowser/commit/44eb2d4f9922fd1a854d959602c6a2455eab0dc5), [fbaf78e](https://github.com/sqlitebrowser/sqlitebrowser/commit/fbaf78ea65bc8354d053192c90dece17ce7c8b5b), [315019d](https://github.com/sqlitebrowser/sqlitebrowser/commit/315019dd9ce028331caa1d6f8863829a8ce25e9d), [1a3e3d3](https://github.com/sqlitebrowser/sqlitebrowser/commit/1a3e3d3c40112d4dd92a6427eb84ad7fdbd4aa92), [ea1659e](https://github.com/sqlitebrowser/sqlitebrowser/commit/ea1659e1d09c6d1e3452d3dd76986ac901d637dd), [a5ca756](https://github.com/sqlitebrowser/sqlitebrowser/commit/a5ca75655c42c45c35a3f41611942328237cd39f), [7db96cd](https://github.com/sqlitebrowser/sqlitebrowser/commit/7db96cdf13ff9131b87a71ebb48517080869b061), [72d64ed](https://github.com/sqlitebrowser/sqlitebrowser/commit/72d64edbe0f3eff0e3557bdccedf75c3276bc5b8), [f01ad40](https://github.com/sqlitebrowser/sqlitebrowser/commit/f01ad409ff294cf5dea1cf035f589c1b0509b76f), [3e02420](https://github.com/sqlitebrowser/sqlitebrowser/commit/3e0242025628ffecb554f0508f1c35de1aa42c2c), [#1131](https://github.com/sqlitebrowser/sqlitebrowser/issues/1131), [#1132](https://github.com/sqlitebrowser/sqlitebrowser/issues/1132), [#1133](https://github.com/sqlitebrowser/sqlitebrowser/issues/1133))
* Make import of multiple CSV files easier to use ([#1121](https://github.com/sqlitebrowser/sqlitebrowser/issues/1121))
* Optimise the Import CSV dialog for better usability ([#1072](https://github.com/sqlitebrowser/sqlitebrowser/issues/1072))
* Improve speed of preview table for large fields in the Import CSV dialog ([#720](https://github.com/sqlitebrowser/sqlitebrowser/issues/720))
* Speed up CSV import a lot and reduce its memory usage ([6432517](https://github.com/sqlitebrowser/sqlitebrowser/commit/643251780557ffccf84a3a672a4d88e941313f97), [b7a00d3](https://github.com/sqlitebrowser/sqlitebrowser/commit/b7a00d301a2a469ba4a4b430e7b3f1b13fdc2842), [6ed8080](https://github.com/sqlitebrowser/sqlitebrowser/commit/6ed8080fdb19e4b6cfadbb67d336bc6ce828d74c), [0eb1f65](https://github.com/sqlitebrowser/sqlitebrowser/commit/0eb1f6579815ee1148323ce928d24eab9f0f8002), [659f38e](https://github.com/sqlitebrowser/sqlitebrowser/commit/659f38ebefc8f1d245b30fe279d318c26c2b84a2), [ed9fda2](https://github.com/sqlitebrowser/sqlitebrowser/commit/ed9fda28ea6b54bf86bf78ceaaae3256f3dec3e5))
* All sorts of improvements for tracking dbhub.io databases and pushing them back to the cloud ([8a540a2](https://github.com/sqlitebrowser/sqlitebrowser/commit/8a540a27457e4ce44be5cd6b695537e5ba1da433), [fef884a](https://github.com/sqlitebrowser/sqlitebrowser/commit/fef884a4e1e88e4899d3a49169ba2bbb77d3bd5c), [f18064f](https://github.com/sqlitebrowser/sqlitebrowser/commit/f18064f0aecb306cde860bde79b10cdfaf6550d2), [b2ddcdd](https://github.com/sqlitebrowser/sqlitebrowser/commit/b2ddcdd470e16134d978d9afb5d00231b2caa079), [f926a67](https://github.com/sqlitebrowser/sqlitebrowser/commit/f926a67dba4d8277041fcb74f27674c83c804752), [8c0e4bf](https://github.com/sqlitebrowser/sqlitebrowser/commit/8c0e4bfdaaef17d93c888d3f97e5e9383fcd7bd5), [c692ae0](https://github.com/sqlitebrowser/sqlitebrowser/commit/c692ae0de52e281cbc3115fece930578f10051a0), [64b3341](https://github.com/sqlitebrowser/sqlitebrowser/commit/64b33413fbd289cceb2837b700bca621326ac615), [d738597](https://github.com/sqlitebrowser/sqlitebrowser/commit/d73859736dc741ab72f2bbc4a0f6fae2b2e57b38), [24ee209](https://github.com/sqlitebrowser/sqlitebrowser/commit/24ee209befa24d0ac6c1499f3f327c252a545cea), [a1855d8](https://github.com/sqlitebrowser/sqlitebrowser/commit/a1855d8f7525a1afa91a70256e6c892557dbb198), [eff92c2](https://github.com/sqlitebrowser/sqlitebrowser/commit/eff92c2818138bcac3e507ba81081c544b735962), [#1136](https://github.com/sqlitebrowser/sqlitebrowser/issues/1136))
* Move button for saving Execute SQL results to the toolbar ([#1122](https://github.com/sqlitebrowser/sqlitebrowser/issues/1122))
* Rearrange display format list for better usability ([31e499d](https://github.com/sqlitebrowser/sqlitebrowser/commit/31e499d9fa282fc67138647668a24e3b18df09a8))
* Add menu option to hide selected columns (and unhide them) in the Browse Data view ([#1135](https://github.com/sqlitebrowser/sqlitebrowser/issues/1135)), [d4e228d](https://github.com/sqlitebrowser/sqlitebrowser/commit/d4e228d4b588721029e875fe288828b7880144fe))
* Add automatic type detection to the CSV import ([#1003](https://github.com/sqlitebrowser/sqlitebrowser/issues/1003)), [#1382](https://github.com/sqlitebrowser/sqlitebrowser/issues/1382))
* Improve splitters in Execute SQL tab ([#380](https://github.com/sqlitebrowser/sqlitebrowser/issues/380))
* New menu options for using a value as a filter in the Browse Data tab, and support all filter operators for strings ([#1182](https://github.com/sqlitebrowser/sqlitebrowser/issues/1182), [#1463](https://github.com/sqlitebrowser/sqlitebrowser/issues/1463))
* Allow renaming SQL tabs by double clicking their title ([#1186](https://github.com/sqlitebrowser/sqlitebrowser/issues/1186))
* Add support for filtering for empty strings in the Browse Data tab ([#1189](https://github.com/sqlitebrowser/sqlitebrowser/issues/1189))
* Add a new menu option for also copying the headers to the clipboard ([#1058](https://github.com/sqlitebrowser/sqlitebrowser/issues/1058))
* Add a search bar (Ctrl+F) to Execute SQL editors ([#191](https://github.com/sqlitebrowser/sqlitebrowser/issues/191))
* Add a find and replace dialog (Ctrl+H) to all SQL editors ([#191](https://github.com/sqlitebrowser/sqlitebrowser/issues/191))
* It's now possible to select points in a plot and the corresponding rows in the table will be selected ([e8e5671](https://github.com/sqlitebrowser/sqlitebrowser/commit/e8e5671588ce378fdde9607346060474b84144f7))
* Show number of records to delete in the Delete Record button caption ([5fbf5ca](https://github.com/sqlitebrowser/sqlitebrowser/commit/5fbf5ca1b28373323591f05a339f18b58e9c283c))
* Add new display formats ([46ec019](https://github.com/sqlitebrowser/sqlitebrowser/commit/46ec0197193ad127103f7d8408895e7c4f76fc67), [#1213](https://github.com/sqlitebrowser/sqlitebrowser/issues/1213), [#1467](https://github.com/sqlitebrowser/sqlitebrowser/issues/1467))
* Add special editor for JSON data in the Edit Cell dialog ([#1173](https://github.com/sqlitebrowser/sqlitebrowser/issues/1173))
* Add special editor for XML data in the Edit Cell dialog ([#1253](https://github.com/sqlitebrowser/sqlitebrowser/issues/1253))
* Use HTML when copying table data to the clipboard. This way less data is lost when pasting to spreadsheet applications ([e60e9ff](https://github.com/sqlitebrowser/sqlitebrowser/commit/e60e9ffc758f26aa7d9833552bb5d3e1d3d566b3))
* Some improvements to the plot UI including zooming, dragging and copying the plot to the clipboard ([ade5627](https://github.com/sqlitebrowser/sqlitebrowser/commit/ade562769a06e4f010f15e88ddba2946747f6528), [#1245](https://github.com/sqlitebrowser/sqlitebrowser/issues/1245), [cef1e90](https://github.com/sqlitebrowser/sqlitebrowser/commit/cef1e9020be975ad675d02f542b77747d778f8d0), [#950](https://github.com/sqlitebrowser/sqlitebrowser/issues/950), [#1258](https://github.com/sqlitebrowser/sqlitebrowser/issues/1258), [e34d360](https://github.com/sqlitebrowser/sqlitebrowser/commit/e34d36085df827999935ab0c94cf44ef2bd08736), [#838](https://github.com/sqlitebrowser/sqlitebrowser/issues/838), [#1271](https://github.com/sqlitebrowser/sqlitebrowser/issues/1271), [b2fbf45](https://github.com/sqlitebrowser/sqlitebrowser/commit/b2fbf450121a395fc83c8a331c5742f446adfa6e), [#1310](https://github.com/sqlitebrowser/sqlitebrowser/issues/1310), [c4109e6](https://github.com/sqlitebrowser/sqlitebrowser/commit/c4109e6a10058c228940688d1fee38da0bab4c7b))
* Some minor improvements to the Execute SQL UI ([87e1b9b](https://github.com/sqlitebrowser/sqlitebrowser/commit/87e1b9bc7c51b86fca2c3192929500fd457022eb), [6d44c6d](https://github.com/sqlitebrowser/sqlitebrowser/commit/6d44c6d412d39e9c84e0d4d3cc543bdb17fb26fb))
* Allow pasting a value into multiple cells at once ([0d7ca9b](https://github.com/sqlitebrowser/sqlitebrowser/commit/0d7ca9b5bec0c83b88787fc333f3b61652dcacaf))
* Allow changing the font of the result view in the Execute SQL tab ([#1240](https://github.com/sqlitebrowser/sqlitebrowser/issues/1240))
* Add a new button to the Browse Data tab to create a view from the current settings ([#1246](https://github.com/sqlitebrowser/sqlitebrowser/issues/1246))
* Add two new toolbar for Extra actions and for Project actions and add some more icons to the existing toolbars and menus ([#331](https://github.com/sqlitebrowser/sqlitebrowser/issues/331))
* Allow configuration of BLOB text and style for the Browse Data tab ([#1263](https://github.com/sqlitebrowser/sqlitebrowser/issues/1263))
* Add a new dialog for managing database file extensions ([#659](https://github.com/sqlitebrowser/sqlitebrowser/issues/659))
* Add possibility to drag and drop fields from the DB Schema dock to the SQL text editors ([#119](https://github.com/sqlitebrowser/sqlitebrowser/issues/119), [#1250](https://github.com/sqlitebrowser/sqlitebrowser/issues/1250))
* Add a Delete Record(s) option to the context menu of the table rows in the Browse Data tab([#1283](https://github.com/sqlitebrowser/sqlitebrowser/issues/1283))
* Add a new --read-only command line option ([#1265](https://github.com/sqlitebrowser/sqlitebrowser/issues/1265))
* Allow duplicating multiple records at once ([#1090](https://github.com/sqlitebrowser/sqlitebrowser/issues/1090))
* Auto complete SQL keywords in upper case and add an option for it in the Preferences dialog ([#1238](https://github.com/sqlitebrowser/sqlitebrowser/issues/1238), [#1287](https://github.com/sqlitebrowser/sqlitebrowser/issues/1287))
* Respect the ORDER BY clause when plotting a table view ([#821](https://github.com/sqlitebrowser/sqlitebrowser/issues/821), [#838](https://github.com/sqlitebrowser/sqlitebrowser/issues/838))
* Also auto complete column names when they are not preceded by their table name ([#1242](https://github.com/sqlitebrowser/sqlitebrowser/issues/1242))
* Add bar charts to the plot dock ([#1302](https://github.com/sqlitebrowser/sqlitebrowser/issues/1302))
* Allow adding a legend to the plot ([#1302](https://github.com/sqlitebrowser/sqlitebrowser/issues/1302))
* Add "What's This" popups in some more places ([52ae85d](https://github.com/sqlitebrowser/sqlitebrowser/commit/52ae85dd28ac8a21e5db67db02e551e059917821), [2c9cf75](https://github.com/sqlitebrowser/sqlitebrowser/commit/2c9cf75419feea889d2a86f0b7549d8acacab0c2))
* Avoid any hard coded colours and query system colours wherever possible. In practice this adds support for dark themes ([#1324](https://github.com/sqlitebrowser/sqlitebrowser/issues/1324))
* Add new option for setting the line wrap in editors ([#1173](https://github.com/sqlitebrowser/sqlitebrowser/issues/1173))
* When clicking the Report Bug menu item some system information are included automatically ([#1386](https://github.com/sqlitebrowser/sqlitebrowser/issues/1386))
* When an entire row is selected and you press the Delete key, the row is now deleted ([#1391](https://github.com/sqlitebrowser/sqlitebrowser/issues/1391))
* Change the rules for the CSV import and add a couple of options to override them ([#1395](https://github.com/sqlitebrowser/sqlitebrowser/issues/1395))
* Add a new menu item to export the current table view with all its settings to a CSV file ([#1402](https://github.com/sqlitebrowser/sqlitebrowser/issues/1402))
* Add support for deleting rows from views with editing unlocked ([#141](https://github.com/sqlitebrowser/sqlitebrowser/issues/141))
* Add menu option to copy selection in table view as SQL statements ([#1422](https://github.com/sqlitebrowser/sqlitebrowser/issues/1422))
* Move loading of table records into a separate thread for better UI responsiveness ([#1394](https://github.com/sqlitebrowser/sqlitebrowser/issues/1394))
* Change the quotes for SQL identifiers from grave to double quotes and add an option to the Preferences dialog for it ([#1436](https://github.com/sqlitebrowser/sqlitebrowser/issues/1436))
* Change Open Database toolbar action to open a popup menu with an extra option to open a database in read-only mode ([#1432](https://github.com/sqlitebrowser/sqlitebrowser/issues/1432))
* Comments containing filename, line number and results of the executed statements are added to the "User" part of the SQL log dock ([#1448](https://github.com/sqlitebrowser/sqlitebrowser/issues/1448))
* Look for a dotenv file with a stored password when trying to open an encrypted database ([#1404](https://github.com/sqlitebrowser/sqlitebrowser/issues/1404))
* Make the Unlock View Editing dialog easier to use ([241372e](https://github.com/sqlitebrowser/sqlitebrowser/commit/241372e6eb33e6522e9a4a7dd4869df2fff066e3))
* Add support for creating and editing in-memory databases ([#335](https://github.com/sqlitebrowser/sqlitebrowser/issues/335), [#1492](https://github.com/sqlitebrowser/sqlitebrowser/issues/1492))
* Menu restructured, Tools menu added ([#1434](https://github.com/sqlitebrowser/sqlitebrowser/issues/1434))
* Add case_sensitive_like pragma to the Edit Pragmas tab and save it to the project file ([#1494](https://github.com/sqlitebrowser/sqlitebrowser/issues/1494), [c9d651c](https://github.com/sqlitebrowser/sqlitebrowser/commit/c9d651c7b2cc0cba548ef71b3feef8bfd34322e6))
* When adding an empty row fails open a new Add Record dialog instead in the Browse Data tab. Also make the new dialog available by a new button ([#530](https://github.com/sqlitebrowser/sqlitebrowser/issues/530), [#1477](https://github.com/sqlitebrowser/sqlitebrowser/issues/1477))
* Store the values of all pragmas which aren't stored in the database in the project files ([#1518](https://github.com/sqlitebrowser/sqlitebrowser/issues/1518))
* Add schema names to the auto completion list of names and allow completion of schema.table.field ([#1433](https://github.com/sqlitebrowser/sqlitebrowser/issues/1433))
* Some new configuration options for the drag and drop of item names from the DB Schema dock ([#1433](https://github.com/sqlitebrowser/sqlitebrowser/issues/1433), [#1534](https://github.com/sqlitebrowser/sqlitebrowser/issues/1534))
* Preselect file format filter depending on the current data type when exporting cell contents to a file ([#1535](https://github.com/sqlitebrowser/sqlitebrowser/issues/1535))
* Allow saving the hex editor contents when exporting binary cell contents to a file and allow copying the same data to the clipboard ([#1438](https://github.com/sqlitebrowser/sqlitebrowser/issues/1438), [#1485](https://github.com/sqlitebrowser/sqlitebrowser/issues/1485))
* Add printing support to text and hex editors, plots, Database Structure tab, Browse Data tab and Execute SQL tabs ([#1525](https://github.com/sqlitebrowser/sqlitebrowser/issues/1525))
* Add some new menu items for optimising and checking the integrity of the database ([#1435](https://github.com/sqlitebrowser/sqlitebrowser/issues/1435))
* Save attached databases in the project file ([#1532](https://github.com/sqlitebrowser/sqlitebrowser/issues/1532))
* Add basic support for window functions ([7e23214](https://github.com/sqlitebrowser/sqlitebrowser/commit/7e23214e61829485993ce1910ec95233de21dcaa), [517743f](https://github.com/sqlitebrowser/sqlitebrowser/commit/517743ff3fa65ae3447c6520f16f1cf613b0053d))
* Add an optional auto completion popup to the Browse Data tab which shows up when editing a cell ([e1101ae](https://github.com/sqlitebrowser/sqlitebrowser/commit/e1101ae6905130dd4d7becf323303a4ae804d99f), [04f27cc](https://github.com/sqlitebrowser/sqlitebrowser/commit/04f27ccf4ba301b9d092fcd33341968d54283c5d), [88d1cbc](https://github.com/sqlitebrowser/sqlitebrowser/commit/88d1cbc29df359f1f7987d97b649923b7a762d57), [b4b933c](https://github.com/sqlitebrowser/sqlitebrowser/commit/b4b933c158ca59cd0d6d9e529f4e58b9304712da))
* Some polishing of the main window UI ([#420](https://github.com/sqlitebrowser/sqlitebrowser/issues/420), [f42b614](https://github.com/sqlitebrowser/sqlitebrowser/commit/f42b614084d75c3669983af561a4fe9c5f2cf13a))
* Automatically preselect correct editor depending on the detected data type in the Edit Cell dialog ([#1537](https://github.com/sqlitebrowser/sqlitebrowser/issues/1537))
* Change project file format to support multiple sort columns ([#1593](https://github.com/sqlitebrowser/sqlitebrowser/issues/1593))
* The SQL function `load_extension()` is only enabled when explicitly requested by the user in a new setting ([#1558](https://github.com/sqlitebrowser/sqlitebrowser/issues/1558)
* Command line option for running with some setting set to a given value  ([#1588](https://github.com/sqlitebrowser/sqlitebrowser/issues/1588))

## Bug fixes

* Avoid extra spaces when formatting SQL statements ([18bcbf1](https://github.com/sqlitebrowser/sqlitebrowser/commit/18bcbf138f3f351e21eaf2db108f89e558943c45))
* Fix dbhub.io bugs ([4dc5286](https://github.com/sqlitebrowser/sqlitebrowser/commit/4dc52865962414b2754c5a6db6ad68c0958f0eb0))
* Fix detection of image data in Edit Cell dialog ([#1138](https://github.com/sqlitebrowser/sqlitebrowser/issues/1138), [#1159](https://github.com/sqlitebrowser/sqlitebrowser/issues/1159))
* Fix Vacuum dialog ([c616b39](https://github.com/sqlitebrowser/sqlitebrowser/commit/c616b3947806411cd1e7d20ca936b5f1dfae35bd))
* Allow selecting text in Edit Cell dialog even if database is read only ([#1123](https://github.com/sqlitebrowser/sqlitebrowser/issues/1123), [#1461](https://github.com/sqlitebrowser/sqlitebrowser/issues/1461))
* Clear filters in Browse Data tab when table structure changes ([#1020](https://github.com/sqlitebrowser/sqlitebrowser/issues/1020))
* Add support for parsing multiple foreign keys in column constraints ([677d360](https://github.com/sqlitebrowser/sqlitebrowser/commit/677d36074afe7add7b54984a93fba97b8349f061))
* Fix memory leaks ([28446a4](https://github.com/sqlitebrowser/sqlitebrowser/commit/28446a4f0cba71122e37788e46171c2fd3fab448))
* Fix input of custom data types in Edit Table dialog so it doesn't require you to hit Enter ([#1147](https://github.com/sqlitebrowser/sqlitebrowser/issues/1147))
* Don't query foreign key pragma all the time in Edit Table dialog ([#1130](https://github.com/sqlitebrowser/sqlitebrowser/issues/1130))
* Avoid unnecessary queries in Browse Data tab ([#1108](https://github.com/sqlitebrowser/sqlitebrowser/issues/1108), [#1187](https://github.com/sqlitebrowser/sqlitebrowser/issues/1187))
* Support UTF16 strings in the default collation in DB4S ([#1172](https://github.com/sqlitebrowser/sqlitebrowser/issues/1172))
* Never override the built-in collations ([#1172](https://github.com/sqlitebrowser/sqlitebrowser/issues/1172))
* Fix problems when opening a database by drag and drop ([9cff69f](https://github.com/sqlitebrowser/sqlitebrowser/commit/9cff69f534d614b9643c7e871ca07d1bca8de5fb), [#1236](https://github.com/sqlitebrowser/sqlitebrowser/issues/1236))
* Fix crash when trying to edit the display format of a view column ([9fd4ebe](https://github.com/sqlitebrowser/sqlitebrowser/commit/9fd4ebe0e0ba6bc48509d4d8b9a27205c60d81a1))
* Better error and changes detection in Execute SQL tab ([#1181](https://github.com/sqlitebrowser/sqlitebrowser/issues/1181), [#1185](https://github.com/sqlitebrowser/sqlitebrowser/issues/1185))
* Fix parsing of SQL statements on systems with some locales like Turkish ([#1194](https://github.com/sqlitebrowser/sqlitebrowser/issues/1194))
* Fix some high DPI issues ([#1184](https://github.com/sqlitebrowser/sqlitebrowser/issues/1184))
* Improve BLOB detection in Browse Data tab ([9b30940](https://github.com/sqlitebrowser/sqlitebrowser/commit/9b309402db3e9ecfb27207b2c4c0689310372a2b))
* Fix changing table name to a name that only differs in case ([#1200](https://github.com/sqlitebrowser/sqlitebrowser/issues/1200))
* Fix progress dialog of CSV import for very large files ([#1212](https://github.com/sqlitebrowser/sqlitebrowser/issues/1212))
* Select current display format when opening the Custom Display Format dialog ([#1202](https://github.com/sqlitebrowser/sqlitebrowser/issues/1202))
* Only display the horizontal scrollbar in the SQL editor when it's necessary ([d8aeae1](https://github.com/sqlitebrowser/sqlitebrowser/commit/d8aeae1a6ff0f4d721b4a806b01a9e77ae3f27f1))
* Show keyboard shortcuts in some places where they were missing ([9ce4b23](https://github.com/sqlitebrowser/sqlitebrowser/commit/9ce4b232ba17493d9064c0a3dd963f26d5405215))
* Fix restoring previous settings in the Export SQL dialog ([ccb1fd4](https://github.com/sqlitebrowser/sqlitebrowser/commit/ccb1fd4ca86cbcd367379356948e23c1047921f0))
* Never use quotes when copying data from the table view to the text clipboard ([#1244](https://github.com/sqlitebrowser/sqlitebrowser/issues/1244))
* Fix crash when clicking Save SQL file button when no SQL tab is opened ([#1248](https://github.com/sqlitebrowser/sqlitebrowser/issues/1248))
* Fix pasting table data from spreadsheet applications which put an extra line break at the end of the text ([#1244](https://github.com/sqlitebrowser/sqlitebrowser/issues/1244))
* Fix pasting when actually no data is in the clipboard ([9db70e0](https://github.com/sqlitebrowser/sqlitebrowser/commit/9db70e07503ffe3ff021087a70b6c32c9bc68c24))
* Copying and pasting between different tables and copying binary data in the Browse Data tab is now always lossless ([47b0749](https://github.com/sqlitebrowser/sqlitebrowser/commit/47b07490de85b1d354a92a468ccadcb2cea0dffe), [#1257](https://github.com/sqlitebrowser/sqlitebrowser/issues/1257))
* Fix copying binary data ([316860a](https://github.com/sqlitebrowser/sqlitebrowser/commit/316860a7091bfe0f7de43e78cf6c03b0f9d7387d))
* Don't ignore possible error messages when duplicating a record ([#1255](https://github.com/sqlitebrowser/sqlitebrowser/issues/1255))
* Don't truncate data at 32768 characters when editing it in directly in the table widget ([#1281](https://github.com/sqlitebrowser/sqlitebrowser/issues/1281))
* Fix binary data detection in table views ([#1279](https://github.com/sqlitebrowser/sqlitebrowser/issues/1279), [27c6579](https://github.com/sqlitebrowser/sqlitebrowser/commit/27c657902e354b11fb5778cc09518a95d37d3698), [c9c848e](https://github.com/sqlitebrowser/sqlitebrowser/commit/c9c848e99555f816aa183e7dad426e3151e0f51d), [feda408](https://github.com/sqlitebrowser/sqlitebrowser/commit/feda408161ae98fee69bfd46a91c607bbc40921d))
* Allow unsetting the encoding of a table ([#1279](https://github.com/sqlitebrowser/sqlitebrowser/issues/1279))
* Fix drag and drop of tables from the Schema tab ([117af5a](https://github.com/sqlitebrowser/sqlitebrowser/commit/117af5aeeb146860f080584c82876f71ac227ff1))
* Fix style of web links in UI ([#1286](https://github.com/sqlitebrowser/sqlitebrowser/issues/1286))
* Fix execution of some SQL statements with comments and/or line breaks in them ([#1270](https://github.com/sqlitebrowser/sqlitebrowser/issues/1270), [#1334](https://github.com/sqlitebrowser/sqlitebrowser/issues/1334))
* Add support for tables with ON CONFLICT clauses for their primary key ([743e798](https://github.com/sqlitebrowser/sqlitebrowser/commit/743e7985c2dc5b6c65ac0ff46abba33a443f26ba))
* Fix crash when pressing Tab at the last cell of a view ([#1289](https://github.com/sqlitebrowser/sqlitebrowser/issues/1289))
* Fix crash when trying to add an index to a database without any tables ([#1293](https://github.com/sqlitebrowser/sqlitebrowser/issues/1293))
* Fix problems after drag & drop of tables onto the structure view ([#1288](https://github.com/sqlitebrowser/sqlitebrowser/issues/1288))
* Copy original statement when clicking the Copy Create Statement menu option ([#1300](https://github.com/sqlitebrowser/sqlitebrowser/issues/1300))
* Fix updating and deleting from tables without rowid if the primary key value contains a "'" character ([#1332](https://github.com/sqlitebrowser/sqlitebrowser/issues/1332))
* Don't show "Show Rowid" menu option for tables without rowid ([#1332](https://github.com/sqlitebrowser/sqlitebrowser/issues/1332))
* Our project file format is now text only. This helps if you want to edit it in a text editor ([#1306](https://github.com/sqlitebrowser/sqlitebrowser/issues/1306))
* Don't commit the current transaction when trying to change the defer_foreign_keys PRAGMA ([aebfc51](https://github.com/sqlitebrowser/sqlitebrowser/commit/aebfc5151ec1c2e0cb2c5a01a81a4e53f682f7c7))
* Fix error messages when importing SQL files ([431c671](https://github.com/sqlitebrowser/sqlitebrowser/commit/431c67138ba22445f42a6d95a638fd90284a442b))
* Show icons in Export SQL dialog ([28baba8](https://github.com/sqlitebrowser/sqlitebrowser/commit/28baba8ec88beb54bb7ff642dc1ad0c95e7c9486))
* Only allow exporting tables in Export SQL dialog ([b384027](https://github.com/sqlitebrowser/sqlitebrowser/commit/b384027378aa7d72ad420568543080cd6e15ea1e))
* Tweak order of statements in exported SQL file for less import problems ([b6c0560](https://github.com/sqlitebrowser/sqlitebrowser/commit/b6c05609dc496e1aedd8f9a9c98cf667bdab1a08))
* Fix text of toolbar actions for deleting and modifying objects other than tables ([13d9f98](https://github.com/sqlitebrowser/sqlitebrowser/commit/13d9f98aabeb66d6d466f301a139ec2b975482bf))
* Remember "primary key" of a view unlocked for editing when changing to another object and back ([ea25618](https://github.com/sqlitebrowser/sqlitebrowser/commit/ea25618f22db324e10b6dac90d01b8ca947fe103))
* Only allow powers of two for page size in Cipher Settings dialog and Edit Pragma tab ([#1405](https://github.com/sqlitebrowser/sqlitebrowser/issues/1405), [8a07f0e](https://github.com/sqlitebrowser/sqlitebrowser/commit/8a07f0e6556dd9e0b1e369a897db7a05f33085a8))
* Make sure the insert and delete record buttons are only enabled if they can be used ([115d1f1](https://github.com/sqlitebrowser/sqlitebrowser/commit/115d1f185a28bf0858ec1799a1c53cd4ee1aa4fb))
* Suggest correct file extensions when export content of a cell to a file ([885f4f7](https://github.com/sqlitebrowser/sqlitebrowser/commit/885f4f7847a46d85f45501ff67bde089830e81f6))
* Make sure to reset results view even when a query didn't return any rows ([#1437](https://github.com/sqlitebrowser/sqlitebrowser/issues/1437))
* Auto suggest encodings in Select Encoding dialog ([588363b](https://github.com/sqlitebrowser/sqlitebrowser/commit/588363b7f6fe70a32986e5d48781980eb6876d5b))
* Fix parsing of some complex SQL expressions in CREATE statements and fix parsing of CHECK constraints ([#1454](https://github.com/sqlitebrowser/sqlitebrowser/issues/1454), [c150d1a](https://github.com/sqlitebrowser/sqlitebrowser/commit/c150d1a7664eb02c669e609ee0b01d9c93ad3336))
* Fix multiple SQL statements in Execute SQL tab being split up at the wrong position ([#1470](https://github.com/sqlitebrowser/sqlitebrowser/issues/1470))
* Don't allow editing the SQL preview in the Create Index dialog ([7a9f310](https://github.com/sqlitebrowser/sqlitebrowser/commit/7a9f310778b9be6cc0b7d503df73ca461fa95083))
* When jumping to a row referenced to by a foreign key by using Ctrl+Shift+Click, perform an exact search instead of a LIKE search ([d50a27a](https://github.com/sqlitebrowser/sqlitebrowser/commit/d50a27ab6e47002cbf09d45529e7c21ea390a7c5))
* Fix crash when browsing a table, then deleting it in another tab and then switching back to the Browse Data tab ([2701223](https://github.com/sqlitebrowser/sqlitebrowser/commit/2701223aac892d167ff4726b6c71e35d5cf77c43))
* Fix string quotes in Custom Display Format dialog ([b6f47f9](https://github.com/sqlitebrowser/sqlitebrowser/commit/b6f47f91de284f715493bd41e1ec130e6878d800))
* Prevent possible data loss when editing table with foreign keys enabled and ON DELETE CASCADE references ([#1481](https://github.com/sqlitebrowser/sqlitebrowser/issues/1481))
* Fix view when loading a project file while being in the Edit Pragma tab ([a23c0a0](https://github.com/sqlitebrowser/sqlitebrowser/commit/a23c0a0852ba0b59d3c9fea5f40add845a1307d8))
* Avoid confusion about the SQLCipher version in the About dialog ([#1474](https://github.com/sqlitebrowser/sqlitebrowser/issues/1474))
* Don't remove a record from the table view temporarily when deleting it has failed ([#1511](https://github.com/sqlitebrowser/sqlitebrowser/issues/1511))
* Show better error messages when importing SQL files ([#1519](https://github.com/sqlitebrowser/sqlitebrowser/issues/1519))
* Defer foreign keys when importing SQL files to avoid import issues for some files ([#1519](https://github.com/sqlitebrowser/sqlitebrowser/issues/1519))
* Fix editing of auto_vacuum pragma via the UI ([#1518](https://github.com/sqlitebrowser/sqlitebrowser/issues/1518))
* Fix initial loading of databases which depend on extension functions to be present ([f3e6aec](https://github.com/sqlitebrowser/sqlitebrowser/commit/f3e6aec57d4b7c1c7fbad54be75902db13e5bfcd))
* Fix cursor after SQL import finished ([#1526](https://github.com/sqlitebrowser/sqlitebrowser/issues/1526))
* Fix completion of quoted identifiers in SQL editor ([#1433](https://github.com/sqlitebrowser/sqlitebrowser/issues/1433))
* Fix positioning of cursor in Execute SQL tab when there is an error near a multi-byte character ([99c53a4](https://github.com/sqlitebrowser/sqlitebrowser/commit/99c53a436e82ead40504189c9cac3e141d4b718a))
* Fix some possible crashes when loading an invalid project file ([717ff07](https://github.com/sqlitebrowser/sqlitebrowser/commit/717ff075b52b64603338e0629710bac3e55c41d6))
* Fix auto completion of keyword ROWID ([78ae2c3](https://github.com/sqlitebrowser/sqlitebrowser/commit/78ae2c3e0938fc9b2841a45754c4f4ded0dc642b))
* Better error messages when editing the definition of a table fails ([#1547](https://github.com/sqlitebrowser/sqlitebrowser/issues/1547))
* Fix auto completion not working in some cases until you refresh the database ([#1549](https://github.com/sqlitebrowser/sqlitebrowser/issues/1549))
* Avoid unnecessary queries in the Browse Data tab in some cases ([c78c03b](https://github.com/sqlitebrowser/sqlitebrowser/commit/c78c03bf0b040b58977ba1ebbd284ea69531b939))
* Fix inserting, deleting and editing of rows in WITHOUT ROWID tables with a primary key of TEXT type ([#1559](https://github.com/sqlitebrowser/sqlitebrowser/issues/1559))
* Better error handling in import CSV dialog ([#1590](https://github.com/sqlitebrowser/sqlitebrowser/issues/1590))
* Fix possible resource leaks ([#1691](https://github.com/sqlitebrowser/sqlitebrowser/issues/1691))

## Platform specific

### Windows

* Use MSI installers ([#1400](https://github.com/sqlitebrowser/sqlitebrowser/issues/1400))
* Make sure the image plugins are loaded properly ([#1188](https://github.com/sqlitebrowser/sqlitebrowser/issues/1188), [9016bf6](https://github.com/sqlitebrowser/sqlitebrowser/commit/9016bf6dc741143834c29ac8febd3ef4c4f43b7f))
* Also install license files ([12ee94c](https://github.com/sqlitebrowser/sqlitebrowser/commit/12ee94cee9880ea5f1ce938baec147b999027296))
* Add version info to Windows executables ([#1387](https://github.com/sqlitebrowser/sqlitebrowser/issues/1387))
* Fix line breaks in SQL export ([#1502](https://github.com/sqlitebrowser/sqlitebrowser/issues/1502))

### macOS

* Work around a Qt bug which causes high pings for Wifi connections ([#1209](https://github.com/sqlitebrowser/sqlitebrowser/issues/1209))
* Add a workaround to improve rendering performance on 4k/5k resolutions ([#1233](https://github.com/sqlitebrowser/sqlitebrowser/issues/1233))
* Add .sqlite, .db3 and .sqlite3 to the list of file associations ([28f6c6e](https://github.com/sqlitebrowser/sqlitebrowser/commit/28f6c6e6c1777949acf5bc455707ecdfa43ad298), [3008747](https://github.com/sqlitebrowser/sqlitebrowser/commit/3008747ada0293d682fa1a9e04852013b8d19ff2))
* Fix shortcut name for following a foreign key ([#1539](https://github.com/sqlitebrowser/sqlitebrowser/issues/1539))

### Linux

* Make install paths configurable for qmake build ([#1443](https://github.com/sqlitebrowser/sqlitebrowser/issues/1443))

### Gnome

* Fix problem with switching the workspace on Gnome ([#934](https://github.com/sqlitebrowser/sqlitebrowser/issues/934))

## Translations

* Fix call tips in SQL editor for languages with non-Latin scripts ([#1107](https://github.com/sqlitebrowser/sqlitebrowser/issues/1107), [#1206](https://github.com/sqlitebrowser/sqlitebrowser/issues/1206))
* Never translate the name of the pragmas in the Edit Pragma tab ([9a30e6c](https://github.com/sqlitebrowser/sqlitebrowser/commit/9a30e6cbb0b60ad7b98e5bbcc49f9f4a404ab30b))
* Spanish translation updated ([#1190](https://github.com/sqlitebrowser/sqlitebrowser/issues/1190), [2b6f0d7](https://github.com/sqlitebrowser/sqlitebrowser/commit/2b6f0d73781bf34f1e44eed3b7a0f7c985eea1a3), [aa82b52](https://github.com/sqlitebrowser/sqlitebrowser/commit/aa82b52d5cdcb8511c7eb80112732e5d5f2a32d8), [636136a](https://github.com/sqlitebrowser/sqlitebrowser/commit/636136a775f9480ec49e1cec3cae583aecde2e2e))
* German translation updated ([09e170f](https://github.com/sqlitebrowser/sqlitebrowser/commit/09e170f75dff94761918767c644d2a16c7b4f0e5))
* Korean translation updated ([8c85ff9](https://github.com/sqlitebrowser/sqlitebrowser/commit/8c85ff9157bfb154772eae46ec30787f2fff2c65))
* Polish translation added ([#1456](https://github.com/sqlitebrowser/sqlitebrowser/issues/1456))
* French translation updated ([b7dbfc8](https://github.com/sqlitebrowser/sqlitebrowser/commit/b7dbfc84c949f685d6e0478d33f8aeb040028697))
* Italian translation added ([#1705](https://github.com/sqlitebrowser/sqlitebrowser/issues/1705))
* Czech translation updated ([#1710](https://github.com/sqlitebrowser/sqlitebrowser/issues/1710))
* Portuguese translation updated ([#1707](https://github.com/sqlitebrowser/sqlitebrowser/issues/1707))
* Simplified Chinese translation updated ([#1594](https://github.com/sqlitebrowser/sqlitebrowser/issues/1594))
* Russian translation updated ([#1581](https://github.com/sqlitebrowser/sqlitebrowser/issues/1581))
* Arabic translation updated ([170fb69](https://github.com/sqlitebrowser/sqlitebrowser/commit/170fb69b438f4fa00fc637bbb78e752f9888d034))

## Packaging and Building

* Fix code to work with Qt 5.10 and later ([e6a4326](https://github.com/sqlitebrowser/sqlitebrowser/commit/e6a4326e9bc1d48d027278171e8ab335c1f91e82), [189b750](https://github.com/sqlitebrowser/sqlitebrowser/commit/189b750a009b71bc7de021647309d0b0d8c40232), [39302f5](https://github.com/sqlitebrowser/sqlitebrowser/commit/39302f5b6061cf687a81984406e20070d60b4563), [72506fb](https://github.com/sqlitebrowser/sqlitebrowser/commit/72506fb90211f4a9034b29975190a254ceb396eb), [#1475](https://github.com/sqlitebrowser/sqlitebrowser/issues/1475))
* Update the bundled qcustomplot librar to version 2.0.0
* Silence some cmake warnings ([#635](https://github.com/sqlitebrowser/sqlitebrowser/issues/635), [#1143](https://github.com/sqlitebrowser/sqlitebrowser/issues/1143))
* Show the build date of the nightly builds in the About dialog ([0bc430b](https://github.com/sqlitebrowser/sqlitebrowser/commit/0bc430bfad1c9517d0dde0095cc91bbc821f15c6))
* Restored Qt 5.2 compatibility ([#1298](https://github.com/sqlitebrowser/sqlitebrowser/issues/1298))