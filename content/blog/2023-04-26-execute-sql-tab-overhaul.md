---
title: Execute SQL Tab Overhaul
author: Chris Locke
date: '2023-04-26'
slug: execute-sql-tab-overhaul
categories:
  - dbhub.io
tags: dbhub.io
---

The 'Execute SQL' tab has been overhauled.

![](/images/Screenshot_20230430_162502.png)

While before it was a simple textbox and a 'Run SQL' button, we've worked hard to improve it.

![](/images/Screenshot_20230430_163202.png)

"Looks like all you've done is removed the button"

![](/images/Screenshot_20230430_181502.png)

It's a bit more than that.  This command window not only shows the data, but also any feedback from SQLite, eg, any errors.
It has syntax-highlighting support so field names are more easily identifiable compared to keywords.  If there is an error, it is clearly displayed.

It also remembers the history of commands, even if you close the browser, so when you next go into that database, it'll show what you entered previously.

You can execute SQL statements by simply pressing Ctrl+Enter but also have the option of executing after just pressing Enter.  This makes running SQL very fluid and comfortable.
