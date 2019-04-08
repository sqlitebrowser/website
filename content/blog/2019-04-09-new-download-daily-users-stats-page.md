---
title: New download and daily users stats page
author: Justin Clift
date: '2019-04-09'
slug: new-download-daily-users-stats-page
categories: []
tags:
  - stats
---

Today we added a new "Stats" page, showing the number of daily downloads and daily users:

&nbsp; &nbsp; https://sqlitebrowser.org/stats/

The graphs are generated using Redash, and should automatically update every 10 minutes:

&nbsp; &nbsp; https://redash.io

Being able to mouse over a particular day to get info for that day is useful, as is being able to download the data set (in various formats, but not yet SQLite :wink:).

It's running in a very low end virtual machine (eg cheap), and there's no proper caching layer yet, so it may be a bit slow to load.

Some sort of decent caching will probably be added over the next few days.