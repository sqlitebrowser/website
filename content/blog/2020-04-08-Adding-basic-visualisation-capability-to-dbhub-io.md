---
title: Adding basic visualisation capability to dbhub.io
author: ''
date: '2020-04-08'
slug: Adding-basic-visualisation-capability-to-dbhub-io
categories: []
tags:
  - dbhub.io
---
We've begun adding the [first visualisation pieces to DBHub.io](https://dbhub.io/vis/justinclift/Marine%20Litter%20Survey%20%28Keep%20Northern%20Ireland%20Beautiful%29.sqlite), so people can display charts from their data.

eg:

<p align="center">
  <img src="/images/2020-04-08-dbhub-v1.png" alt="Screenshot of initial DBHub.io visualisation code"/>
</p>

This is only the starting point (eg a simple vertical bar chart) while we experiment, to find a good workflow that's easy for people to use + customise.

We're aiming to add several more chart types to choose from, and there being a selection of easy-to-use predefined templates as well.

Advanced users will ideally be able to input their own SQL queries for generating the data points to visualise.  That's going to take some time however.

When it's working well, this should for displaying useful visual "diffs" (aka comparisons) between different revisions of data.  Super useful for all kinds of things, including the still-in-development "Merge Request" functionality.

**[Try it out here](https://dbhub.io/vis/justinclift/Marine%20Litter%20Survey%20%28Keep%20Northern%20Ireland%20Beautiful%29.sqlite)**.

[Problem reports](https://github.com/sqlitebrowser/dbhub.io/issues), [feature requests](https://github.com/sqlitebrowser/dbhub.io/issues), (etc) are welcome. :smile:
