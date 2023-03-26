---
title: Live databases are now .. live
author: Chris Locke
date: '2023-03-25'
slug: live-databases-are-now-live
categories:
  - dbhub.io
tags: dbhub.io
---

We've been working hard on the development of DBHub.io and one of the most asked features we've just added is the ability to perform insert, update and delete commands on a database.

One excellent benefit of DBHub.io has always been performing queries on an SQLite database stored in the cloud.  Together with creating snapshots and full version control, it has been a benefit to many users.  However, databases were read-only.  You couldn't perform any changes on them.
But now you can.

![](/images/Screenshot_20230326_145203.png)

When you upload a database, click the 'Advanced' link to reveal the advanced options panel.

![](/images/Screenshot_20230326_150017.png)

Scroll down and you'll see an 'Experimental' panel where you can toggle between 'Standard' and 'Live' databases.
Standard is the default option where databases are read-only, but have the advantage of being version controlled.  You can create a 'commit' and have a different version of the database.  To perform changes, you can download to a database application like DB Browser for SQLite, make the changes, then upload the new database.
If you switch to Live mode, you can use our API to make database changes - insert new rows, update existing rows or delete rows.  Please note though that in this mode, databases are not version controlled.

In related news, we have also updated our Go library (go-dbhub) to access and control live databases.  You can read more about that here (... insert link to blog post 3 ...)

To view details about our API, please visit our [API page](https://api.dbhub.io/).