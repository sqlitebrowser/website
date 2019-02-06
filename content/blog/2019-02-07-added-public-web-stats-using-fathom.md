---
title: Added public web stats using Fathom
author: Justin Clift
date: '2019-02-07'
slug: added-public-web-stats-using-fathom
categories: []
tags:
  - fathom
  - stats
---

Added (GDPR compliant) stats generation today for the website, using [Fathom](https://usefathom.com).  It's an Open Source project, written in Go, that aims to provide aggregated stats simply, without any user tracking.

The setup was fairly easy, though the ARM64 download for the current release (1.2.1) [doesn't seem to work with SQLite](https://github.com/usefathom/fathom/issues/218) due to an accidental setting during their build.  Hopefully fixed for the next release.

PostgreSQL is being the database database, and Nginx providing HTTPS termination.

The [stats server is public](https://stats.sqlitebrowser.org), so added a link to it from our menu bar just because.

It'll be interesting to see how the stats evolve over time. :smile: