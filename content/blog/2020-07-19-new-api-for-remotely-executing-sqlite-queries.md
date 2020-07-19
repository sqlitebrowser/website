---
title: New API for remotely executing SQLite queries
author: Justin Clift
date: '2020-07-19'
slug: new-api-for-remotely-executing-sqlite-queries
categories: []
tags:
  - dbhub.io
---

For anyone wanting to run SQL queries against their uploaded databases, there's now an API server: https://api.dbhub.io

As a starting point, there's just one API call (`/v1/query`), and it only runs SELECT queries (eg read only database).  That should be useful enough for many things though.

### Query parameters

Query parameters are passed via POST only, and all results are in a fairly verbose JSON format.

* `apikey` - Your API key. These can be generated in your [Settings page](https://dbhub.io/pref), when logged in to DBHub.io.
* `dbowner` - The owner of the database to query
* `dbname` - The name of the database
* `sql` - The SQL query, base64 encoded


### Example

Lets say you want to run this query:

```
SELECT table1.Name, table2.value
FROM table1 JOIN table2
USING (id)
ORDER BY table1.id;
```         

On this database: [dbhub.io/justinclift/Join Testing.sqlite](https://dbhub.io/justinclift/Join%20Testing.sqlite)

We'll use [`curl`](https://curl.haxx.se) for this example, but you can use any tool or programming language which supports POST parameters.  Most do.

Using curl:

```
$ curl -F apikey="YOUR_API_KEY_HERE" \
       -F dbowner="justinclift" \
       -F dbname="Join Testing.sqlite" \
       -F sql="U0VMRUNUIHRhYmxlMS5OYW1lLCB0YWJsZTIudmFsdWUKRlJPTSB0YWJsZTEgSk9JTiB0YWJsZTIKVVNJTkcgKGlkKQpPUkRFUiBCWSB0YWJsZTEuaWQ7" \
       https://api.dbhub.io/v1/query
```

The results will be returned in a fairly verbose JSON format which includes data type information for each field, the field name, and the value for that field:

```
[[{"Name":"Name","Type":3,"Value":"Foo"} ... (shortened for clarity)
```

We think that's a good enough starting point, but if you'd like to use this and we're missing something, or something isn't working for you, please [let us know via GitHub Issues](https://github.com/sqlitebrowser/dbhub.io/issues). :smile: