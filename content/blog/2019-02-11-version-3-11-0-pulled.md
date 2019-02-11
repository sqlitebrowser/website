---
title: Version 3.11.0 pulled - encrypting databases non-functional
date: '2019-02-11'
slug: version-3-11-0-pulled
categories: []
tags:
  - 3.11.x
---

A serious bug has been found in the recent 3.11.0 release... newly encrypting databases doesn't work ([#1732](https://github.com/sqlitebrowser/sqlitebrowser/issues/1732)), instead displaying an error message. :frowning:

Existing databases - encrypted or not - can be opened without problem.  The problem only occurs when attempting to newly encrypt a database.

The links on our download page have been reverted back to the prior stable release (3.10.1) for now, while we look into this.

There will probably be a 3.11.1 release in the near future, with the problem solved. :smile:
