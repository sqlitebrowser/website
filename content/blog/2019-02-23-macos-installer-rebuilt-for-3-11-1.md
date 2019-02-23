---
title: macOS installer rebuilt for 3.11.1
author: ''
date: '2019-02-23'
slug: macos-installer-rebuilt-for-3-11-1
categories: []
tags:
  - 3.11.x
---
The macOS installer for 3.11.1 has been updated, so now when the application runs it does so in "light theme mode" (the Aqua look) on macOS Mojave. :smile:

&nbsp; &nbsp; https://download.sqlitebrowser.org/DB.Browser.for.SQLite-3.11.1v2.dmg

It's a workaround for anyone using Mojave in Dark mode, which Qt doesn't yet properly support.  Without this workaround, the colour pallete was unusable in important places.  eg white on white when browsing data :frowning:

[Jesse Jackson](https://github.com/jsejcksn), thank you so much for [showing us how to fix](https://github.com/sqlitebrowser/sqlitebrowser/issues/1751#issuecomment-466618493) this problem. :smile: