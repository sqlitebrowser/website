---
title: First alpha release for 3.12.0
author: Justin Clift
date: '2020-04-15'
slug: first-alpha-release-for-3-12-0
categories:
  - db4s
tags:
  - 3.12.x
  - alpha
---
The first Windows and mac alpha builds for our next major release [are ready](https://github.com/sqlitebrowser/sqlitebrowser/releases/tag/v3.12.0-alpha1). Please try them out, and [report any weirdness](https://github.com/sqlitebrowser/sqlitebrowser/issues/new/choose).

## Downloads

* [DB.Browser.for.SQLite-3.12.0-alpha1-win32.msi](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.0-alpha1/DB.Browser.for.SQLite-3.12.0-alpha1-win32.msi) - Standard installer for 32-bit Windows
* [DB.Browser.for.SQLite-3.12.0-alpha1-win32.zip](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.0-alpha1/DB.Browser.for.SQLite-3.12.0-alpha1-win32.zip) - .zip (no installer) for 32-bit Windows
* [DB.Browser.for.SQLite-3.12.0-alpha1-win64.msi](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.0-alpha1/DB.Browser.for.SQLite-3.12.0-alpha1-win64.msi) - Standard installer for 64-bit Windows
* [DB.Browser.for.SQLite-3.12.0-alpha1-win64.zip](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.0-alpha1/DB.Browser.for.SQLite-3.12.0-alpha1-win64.zip) .zip (no installer) for 32-bit Windows
* [DB.Browser.for.SQLite-3.12.0-alpha1.dmg](https://github.com/sqlitebrowser/sqlitebrowser/releases/download/v3.12.0-alpha1/DB.Browser.for.SQLite-3.12.0-alpha1.dmg) - Standard package for macOS

**Note** - There is no Windows XP support in the 32-bit builds at the moment.  It will probably be added back in the beta releases.

## Highlights

### Better table editing
* SQLite 3.25.0 added support for renaming columns with the ```ALTER TABLE``` command (previously you had to create a new table with the renamed column, copy all data over, delete the old table, then rename the new table - even leaving out some details of the process here...). This does not only make renaming columns a lot faster, it makes it safer too because the new process is less prone to errors and also makes sure to update all references to the renamed column in your indices and triggers. Starting with this release DB4S makes as much use of this new feature as possible. This gives you the full ALTER TABLE support we offer but additionally, all the benefits just mentioned.

* Often you do not edit just one bit of your table schema. For example, when renaming a column you might want to edit its data type or default value too. Before each of these modifications would be carried out immediately which, for large tables, makes editing them very slow and tiresome. With this release DB4S keeps track of all your modifications, only applying them in one single process when clicking the OK button. This should make editing the schema of large tables a lot faster.

* We have also added a new constraint editor. This allows you to add and edit constraints for multiple columns but it is also useful for setting constraint names or just getting an overview of all constraints in the table.
![constraint_editor](/images/3.12.0-alpha1/constraint_editor.png)

### Conditional formatting
* We have added a new feature for configuring conditional formats in the Browse Data tab. With this, you can set colours, font, font size, text alignment, and more depending on the values of the cell. It works very similarly to what you might know from your spreadsheet application.

* Conditional formats are set per column and multiple formats can be configured for each column. Conditional formats can select for anything that can be filtered for, e.g. equals, does not equal, less than, more than, LIKE, etc.

* To set a conditional format you can right-click a cell or right-click a filter bar, then click 'Edit Conditional Formats...' to open the dialog. If you are currently filtering the view, you can also right-click the filter bar and click 'Use for Conditional Format' to quickly add a conditional format for the current filter condition.

* Your configured conditional formats are saved to your project files as well.
![condformat](/images/3.12.0-alpha1/conditional_formats.png)

* Additionally there is a new format toolbar which allows you to set formats arbitrarily without giving any condition. This allows you to format the table contents just like a table in your favourite spreadsheet application, e.g. for presentations or printing.
![formatting](/images/3.12.0-alpha1/format_toolbar.png)

### Better threading and cancelling support for long-running queries
* SQL queries are now running in a separate thread. This means the UI can respond while the query is running. For long-running queries, this makes a huge difference because it allows you to cancel the query anytime.
![cancel_query](/images/3.12.0-alpha1/query_cancel.png)

* SQLite does not support accessing the database from multiple threads simultaneously for all database configurations. Because we want to make sure that it is impossible to corrupt a database file, DB4S does not allow two queries or one query and another long-running process to run simultaneously. In the status bar, you are now notified of any long-running processes and you can cancel them too. But no worries: Whenever you try to start a second query, a message box will inform you and let you decide whether to cancel or wait for the other process to finish.
![statusbar](/images/3.12.0-alpha1/simultaneous_query_notifier.png)

### Multi-column sorting
* It is now possible to sort by multiple columns in the Browse Data tab. You can configure any number of sort keys. Their order will appear in the column headers.

* Simply clicking a column header resets any old sort orders and sorts by just the clicked column. To add another sort key hold the Ctrl key while clicking the column header. Holding the Ctrl key and clicking a column header which is already in the list of to columns for sorting changes the sort order of that column.

* All the columns used for sorting are stored in your project files.
![sort_order](/images/3.12.0-alpha1/project_column_store.png)

### New SQL parser with Unicode support and better coverage in general
* DB4S comes with a SQL parser which is used to analyse the tables schemas. The parser is not perfect and when failing to parse a certain table or index schema, you will not be able to use all features of DB4S on that table or index. Especially editing the schema but also to some extent modifying the contents of the table will not be possible. So even though it is not directly visible, the parser is a very important part of the application.

* This release comes with a new parser. This allows us to fix a lot of problems, for example with complex CHECK constraints, which are now working as expected. The new parser is not only more robust, but it also extracts more information out of the SQL statements which makes editing these tables a smoother experience.

* Finally, the new parser can handle Unicode characters in table and column names just like SQLite does. So if your table schema contains these characters the table will now display correctly.
![utf](/images/3.12.0-alpha1/table_column_unicode.png)

### Find dialogs everywhere
* We have added a find toolbar and a find and replace dialog to the Execute SQL editors. This means you can quickly jump to your search terms in the Execute SQL editor using the toolbar. But you can also open the more powerful dialog for more search options or replacing text. There are new toolbar icons at the top with new keyboard shortcuts.

* We have also added the find and replace dialog to all other editors. This includes the Edit Cell and the SQL log docks because these might show a lot of text which is hard to navigate without a search option.
![find](/images/3.12.0-alpha1/find_replace_dialog.png)

* Additionally, we have added a new find and a new find and replace toolbar to the Browse Data tab. This allows you to look for values or patterns in the currently browsed table without applying a filter. This is especially useful when you have already specified a filter and do not want to change that. The new replace toolbar allows you to replace values without having to switch the tab or write a SQL statement.

* Finally there is a new field 'Filter in all columns'. Type any number of words here to limit the view to only those rows which contain all these words, no matter in which column. This is super useful when looking for a certain value in a table without knowing in which column it could be.
![find_in_table](/images/3.12.0-alpha1/filter_all_columns.png)

### UI improvements everywhere
* This release includes a whole bunch of UI improvements throughout the application, too many to list them all here. Most notably maybe is the improved handling of project files. But there are also new keyboard shortcuts, cleaner window layouts, and many more details.

* There are also more ways in which you can change the window layout and the UI is more responsive to your needs.

### Proxy support
* We have added proxy support to our network code. So it is finally possible to use DB4S through a proxy, for example, your company proxy. This also changes the defaults to use the system proxy configuration instead of not using any proxy at all.

* The proxy settings affect all network code. This includes the automatic update check on Windows and macOS but also the [dbhub.io](https://dbhub.io) integration. If you have not heard of it before, dbhub.io is a cloud service which allows you to work on SQLite databases collaboratively. It is developed by the same developers as DB4S. You can check it out for free. :smile: 

* To change the proxy settings, open the Preferences dialog, go to the Remote tab, and click on the Configure button in the proxy section.
![proxy](/images/3.12.0-alpha1/proxy_settings.png)

### Better performance on slow systems
* There are some major speed improvements in this release. The improved speed when editing a table schema has already been mentioned. The new SQL parser is also vastly faster which can make opening and browsing databases with lots of tables noticeably faster. The SQL import feature is faster too.

* But other than that we have made a ton of small adjustments, each improving the performance a tiny bit. These are significant when combined, especially on older systems. This should make your overall experience a lot smoother.

## All Enhancements

* Make use of the enhanced ALTER TABLE features in SQLite 3.25.0 (5ec03baef41ea938c9b58736c998e24ffe070265)
* Allow specifying an ON CONFLICT strategy in the Import CSV dialog (#1585)
* Add option to remember last location per action type when saving and loading (#1587)
* Add conditional formats to the Browse Data tab (#1503, #1815, #1976)
* Show current database action and add a cancel button in status bar (11ace1efa6289dd3b40399f28c7dbeda2c8840e0)
* Save read-only state in the project file (#1598)
* Add support for filtering by regular expressions using the /regexp/ syntax (#1522)
* More efficient table editing. When editing the schema, do all changes in one go at the end (#1444, #1686)
* Add comment/uncomment feature to the SQL editor (#1614)
* Add option to find and replace in the selection in the SQL editor (#1618)
* Execute SQL statements in a different thread, allowing long-running queries to be cancelled (1f9101ae2a564121ba2843b68c1d7d3f8cff93ad)
* When editing a cell with a foreign-key, show a list of possible values in a dropdown list (#614, #1550)
* Many small performance improvements (#1666, 7f597d07e463ad83b924814a99713e051b496c53, e16537dd9a611054efaa7b30caa4265b83218f99, 9c0b36d7b75aa09e008cbd3fdd332a9c2a47c450, 5589bd9da44bf2056582dc366c272a468a0f5eed, a43e6a93e43d4cda1cfa735c6aec960b8c56c7ec, 66f9e6962048cddb97e9e0a7b2b2c7bd9f8088dc, a0b8b6f16a5cbedc2a67f2f99b5f27bb2e82828e, fad8a847ae5325d5bbb65fce44c697cce431ad24, 4e8eff7af0bb9ca7610da4160b41c6573261e10e, ba1270cedb0feb9522bd787a640f52f68cd5f544, 317918d7cd25000aa6f1ad444c071bfea2cd56f4, ff86e525b38774d0c4774a4bb4350b44e9782037, 1bab387b7a9eb5a1d7f3b4f40a2371522efa4d3c)
* Lots of UI reworking, allowing more flexibility, adding new shortcuts, fixing glitches, and making it more responsive. Some of the new settings are stored in the project file while the handling of project files itself is improved too (#459, #620, #788, #815, #1493, #1608, #1614, #1647, #1675, #1678, #1684, #1706, #1762, #1763, #1889, #1904, #1941, #1965, #1968, #1976, #2025, #2027, #2038, #2062, #2083, 8f32d15204d3490cde3256401afb937f984d3f7c, 7541a8205024368d9f0bdab311e5c6de6e3f8aac, 74befa368b4a0973cc46fd9149d2281a5190725e, fa3a844454e1bc52df3afacd281319eea06a635f, ad15e7aa921205ce47420dee1db5bb7622cc06dc)
* New Save Project As menu item (#1706)
* Ask the user whether to save modified SQL tabs when closing, add a new button to save changes in all open tabs, prompt to save changes in the project when closing the database or the application (#871, #1386, #1706, 71fc484c32b6f1c9beff130aa3c297b0d7285105)
* Allow custom display formats (#573, #1720)
* Add new log to the SQL log dock which prints the SQLite error log (#1754)
* New setting allowing to set a dark style using a style-sheet (#1751, #1493, #1738)
* Add support for sorting by multiple columns in the Browse Data tab and add a button to clear sort orders (#1761, #1810)
* Add support for inserting rows into views with appropriate triggers (#141)
* Improved text editor in the Edit Cell dock (45c1e2abfd9dd95c8a744c24406b09dff5502e71, #1796)
* New command-line argument for saving settings (3e92ec2b3b02bcf7b60c7836d5497a5daa4c124c)
* Show some information about the selected data when selecting cells in the Browse Data tab (4d5e84181348bf298a0e73680565db7f59db48f8, 25715bb5908527133ab8f9e7b7f4cff5ab4542b0)
* Detect changes in SQL files made by other programs (#1839)
* Add a full find dialog to all text editors (#1746)
* Add constraint editing to the Edit Table dialog (ad60a019f2382aec2e14e101c322a782437326fc, cd748d07ab51075f34961cb06ac5869c11ddfb5b, 3f60142abc0509c39eaa72d6f1b25a388cd59b68, 9d654a19ba926e2d89009063ec701753bff67194, 05e2defe331186f93a685a3f5445f00feeae420e, a9e6fe4ecb00214d75a6897e990fb97451765629)
* Include a built-in certificate which allows out-of-the-box read-only access to dbhub.io (b70e25c7866ff8f770b81d6186652d37a6d1f86f)
* Support all Unicode quote and escape characters in the Import CSV dialog (#1860, #2012)
* Add proxy support to dbhub.io functionality (#979)
* Add "Browse Table" action to the context menu of the DB Structure dock (#1943)
* Remember read-only flag for recent files list (#1913)
* Extended regular expression support in the find dialogs (#1625)
* Add duplicate tab feature to Execute SQL area (#1964)
* Prompt user for options after dropping files (#1883)
* Allow changing the collation of columns in the Edit Table dialog (#1973)
* Add global filter field to Browse Data tab (#1608, #1662)
* Support inline preview of image data in cells (#2000)
* Add move field to top/bottom buttons to Edit Table dialog (#1988)
* Add a find and replace toolbars to the Browse Data tab (#1608)
* Add a toolbar for direct formatting of columns, rows, and single cells in the Browse Data tab (#1976)
* Support custom SQLCipher cipher_plaintext_header_size (6b8fb51f049711274eee3a523a3ab3b477524218)
* Add support for parsing, browsing, and editing tables with GENERATED ALWAYS AS columns (#2107)
* Use the column type affinity for the default text alignment in the Browse Data tab (#2032)
* Resize columns according to contents (#2006)
* Allow opening of URLs or filenames from database cells and add a button to insert a link to the file into the cell (#1597)
* Allow editing of the contents of database cells in external applications (#1746, #1791)
* Add support for a secondary Y-axis to the plot area (#2026, #2131)

## All Bug fixes

* Avoid setting the database dirty with some trailing whitespace and comments (#1543)
* Use native and localised names for shortcuts in the tool-tips (#721)
* Add macOS .dylib extension to the extension selector dialog (66e332208831ee27e230303dd056c9d3bad943b4)
* Do not show more than 512 characters in DB Structure tooltips (#1659)
* Load all pending data when select all is requested (#1373)
* Make the Edit Cell Dock to update with the selected cell in SQL results (#481)
* Fix selecting columns in Browse Data tab instead of sorting them (#1717)
* Fix detection of XML data, some types of text data, and large numbers in the Edit Cell dock (3eebffd7c6ef98a22fc8603975ad25964e329e8d, 7d85d7a41bf31c686fba697d4c4107cf7eebbda5, #1846)
* Fix default collations and callbacks when creating a new database (5c727e8b702c019cdd785e50cc11ce11a520fe67)
* Lots of bug fixes in the SQL parser (e828beb76084980ef6b0778630d7fb1c72c644b6, cb694dd2c62ac1e7d1c940fa73ed0edde9a9a322, 3f7b10886041aacf60c8d5fed276e2da145044d8, 3237e9d2f5a6f7ca29942a08f85aee0f2c0eb1e0, #1950, #1969, #1990)
* Always set sort direction to ascending when sorting a different column (00bc7db5c014ad5e5cb3dd7512f83211fb9ede79)
* Fix problems with the JSON export (#1789)
* Fix problems after closing a database (#1800)
* Fix syntax highlighting to exactly match the SQLite keywords (fa66937827586a80a1037c519eddeab0cf2fdbc0)
* Fix deleting from WITHOUT ROWID table (b788e2ddc83941d60a18a7fe14c9ebd2ea1870d0)
* Fix editing data in WITHOUT ROWID tables with multiple primary key columns (#516, #1075, #1834)
* Silence some unnecessary warning messages (#1868, f877f8a10c7786976405564f18046844959e1f2b, 99c7523849ed55feb03f58c0c5cd2a88466e87b6)
* Fix licence list in dbhub.io push dialog (16768d5474de2f5fac9e53eda3e24fe4de4ed046)
* Fix loading last used settings in the Import CSV dialog (cec6b825611a5aa44a7fe09e22ccaca20ecb5510)
* Fix setting last modified date when cloning a dbhub.io database (4cf6cb7c2a1b5843257b249ed24560e49528805b)
* Fix possible crash when loading a corrupt project file (30d0b183a56e55296e19a4347548cf5907cc24e8)
* Include transaction statements in the SQL log (#1859, #1901)
* Fixes for editing cells with RTL texts (#1793, #1929)
* When updating a field try to respect the affinity data type if possible (#1592)
* Fix value in size column of dbhub.io panel for very large databases (622ef9dfc131f5054f6c3568aa880fd2089a4b08)
* Fix plotting data with NULL values by leaving gaps in the graph (#1977)
* Fix importing CSV files with quote characters and no final line break and with only one column and no final line break (#193, #1986)
* Escape filepath when attaching database (#2002)
* Fix foreign-key editor not working correctly in Edit Table dialog (#1991)
* Fix issues with resizing and with hiding a column (#1999)
* Fix editing in tables with custom display formats (6f7fb7480979604ed4b5190199fd1e0e9a18f830)
* Fix problems with greediness in the DB4S implementation of the SQLite REGEXP operator (#2040)
* Check if some column has a NOT NULL constraint in "Set to NULL" (#2021)
* Fix error indication and savepoint handling after failed statements (#2073)
* Make SQL editor in Edit Table dialog read-only (#2078)
* Fix some problems with view editing in Browse Data tab (#2091)
* Fix handling of databases with a view and a trigger with the same name (#2091)
* Never mark the DB dirty if it is read-only (#1514)
* Fix the recordset numbers in the Browse Data tab (cee3523f37bf89780e42fc65fd327c2e1ea3a752, 13742c4602397edad2717c275a373080dc32386d)
* Fix some typos and translation problems (39047109a65e325c1a2135a85a372efaa315316d, 0db3c1e04a7957dd57ee7cdc94ed14d587847464, 29db270e809980d3a36ee6c30fd30bd12a5a5cd7, 1d1afaad218dfea9d9cdcf83821b3c5b33963ebb, fe88463cbad5476ca6555759eb70dee430d89f63)
* Fix dotenv not working for databases encrypted using SQLCipher 3 (77023540ffa29fde53255650bdc4bb4db248a81d)
* Fix dotenv not working when not specifying the plaintext header size  (281cfe78dcfe77f8634c28375414595776043bdd)

## Translations

* Add Japanese translation (#2122, #2130)
* Update Russian translation (faaa2826141233fd6937fc232438c39f4819862a)
* Update Chinese translation (028242160f536b85463481ffd9b158bf6337db16)
* Update Polish translation (5503667d9806370e9a8d1b78ce22bc045b39d7d9, 22a8cc051fa3d4bf977be5bcd804c7ef4fe06aca)
* Update Portuguese translation (#2126)
* Update French translation (daedace373dfe1dcd268fe6c16dacf4b0c76d399, d8b25e0b8ec9ec94b87d48f826e130f58debe4b5)
* Update Spanish translation (721ace49820d955c3752db7b7be1216d5729d6e3)
* Update Turkish translation (#2133)
* Update Italian translation (#2136, #2141)
* Update German translation (#2137)
* Update Arabic translation (#2146)
* Update Simplified Chinese translation (#2145)

## Packaging and Building

* Antlr is removed as a dependency
* Niels Lohmann's JSON library is added as a dependency. A copy of the library is included in the source code.
* Update bundled QScintilla library to version 2.11.1 (e392e648527171e9ba3115d255cccdd8d073497a)
* Update bundled QHexEdit2 library to version 0.8.6 (d4401f9705cef1e04d0a165684b0906677ec498c)
* Update bunbled QCustomPlot library to version 2.0.1 (#2119)
* Update bundled QDarkStyleSheet to version 2.8 (3b2dec4f123fa28ee3527eed1fb49af18483e17c)
* More flexibility to override library paths (9f28851d00b0079b15b05cbbd0cdb7ad41ae24b7, b4af221ee11c6b8df47f6a7b24d5efc1221721c2, 800a8daf11837e9f0a62c10887988eb4a12441b1, a692c06637ee315c5704fda453264001fed3d47a, #1784)
* Add support for building with cmake 3.11 and later (#1361)
* cmake installation on macOS also copies the icon and desktop files (#1723)
* Add workaround for Qt bugs QTBUG-68891 and QTBUG-71020 (#1658)
* Include a new SQLite extension for encoding and decoding base64 and decoding plist data (#1716, #1804)
* Include the fileio, soundex, r-tree, and geopoly extensions (0d25d11bc1f5117aa9d57d23d517d6972c8831fc, 5bf90150fc4d11c65d48ea8a89aa614b12ac84de, 6565cdccffa8a8bca2bdf0d77b5588ab5b455408)
* Raise the maximum number of attached databases to 125 when using the bundled SQLite version (402af87bdb46d54a2bb22afed7fca59eb40e4013, b0bca100c0be0629f794b906d0292d94fd3efdf8)
* Add MIME information file (#2024)

### SHA256SUMS
* DB.Browser.for.SQLite-3.12.0-alpha1-win32.msi
  * 21c9579ac6fb2774499bd5858ce680df866991e44ad5464175e1e1f5f4907e1a
* DB.Browser.for.SQLite-3.12.0-alpha1-win32.zip
  * 6d22db2ce9f3c6797c9ac4a26c8a5964f1fe421f79e3fab48ec24049a5fb3a78
* DB.Browser.for.SQLite-3.12.0-alpha1-win64.msi
  * b2ce867723fe175cc76c3e4409abddb5b2ed46dee7f541914f4f52a70f28ac0e
* DB.Browser.for.SQLite-3.12.0-alpha1-win64.zip
  * 5dcdafae21fc4e4d4c57991e3af7ab5c74c01209f3e531e90203d28e1ba7ce3a
* DB.Browser.for.SQLite-3.12.0-alpha1.dmg
  * d0e27e909996301436c2afd562e9ca2b352e87c8b7a320e9ecf73a2c46963706
