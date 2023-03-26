---
title: Live databases are now .. live!
author: Chris Locke
date: '2023-03-25'
slug: live-databases-are-now-live
categories:
  - dbhub.io
tags: dbhub.io
---

We've been working hard developing DBHub.io.
One of the most requested features is the ability to perform INSERT, UPDATE and DELETE commands on a database.  That now has an experimental implementation available via our [API](https://api.dbhub.io/), and everyone is encouraged to try it out. 

One excellent benefit of DBHub.io has always been performing queries on an SQLite database stored in the cloud.  Together with creating snapshots and full version control, it has been a benefit to many users.  However, databases were read-only.  You couldn't perform any changes on them.  Now you can.

![](/images/Screenshot_20230326_145203.png)

When you upload a database, click the 'Advanced' link to reveal the advanced options panel.

![](/images/Screenshot_20230326_150017.png)

Scroll down and you'll see an 'Experimental' panel where you can toggle between 'Standard' and 'Live' databases.
Standard is the default option where databases are read-only, but have the advantage of being version controlled.  
If you switch to Live mode, you can use our API to make database changes - insert new rows, update existing rows or delete rows.  Please note though that in this mode, databases are not version controlled.

In related news, we have also updated our Go library ([go-dbhub](https://github.com/sqlitebrowser/go-dbhub)) to access and control live databases.  You can read more about that here (... insert link to blog post 3 ...)

To view details about our API, please visit our [API page](https://api.dbhub.io/).