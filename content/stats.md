---
title: Stats
date: "2019-04-08T22:43:15+11:00"
---

**Note 1** - *These data behind these graphs (created using [Redash](https://redash.io)) automatically updates every 10 minutes.*

**Note 2** -  *The graphs are generally slow to display (~20 seconds) at present, as each contains several thousand data points, which your browser needs to process.  Optimisation will be done... at some future time.*

<p align="center">
<p>
These Daily Download stats begin in August 2018, when we moved our primary download location from GitHub to our own servers.
</p>
<p>
GitHub does make download stats available through their API, and it would be useful to add the
historical (and ongoing) downloads from GitHub to this too.  Some day. :smile:
</p>
<iframe src="https://redash.sqlitebrowser.org/embed/query/1/visualization/2?api_key=PWD8erMpWA1tSEsLsqQb4fra2B2L1sMbUbANoeh2" width="100%" height="580"></iframe>
</p>

---

This "Daily Active Users" graph just shows a simple count of how many unique IP addresses (per day) are checking whether a newer version of DB Browser for SQLite is available.

Prior to our 3.11.0 release, this check was done by querying our repository on GitHub.

Due the acquisition of GitHub by Microsoft, we've changed this version query to ask our download servers instead.

The graph begins in August of 2018, when this "where to query the latest version" change was made.  The code appeared first in our [nightly builds for windows and macOS](https://nightlies.sqlitebrowser.org/latest), and is shown in the first few weeks of graph numbers.

The numbers noticably increase in October 2018, with our [first Alpha release for 3.11.0](https://sqlitebrowser.org/blog/first-alpha-release-for-3-11-0/).

With the [3.11.0 release](https://sqlitebrowser.org/blog/version-3-11-0-released/) in Feb 2019, we again see an increase.  That release had a critical bug, so was quickly pulled (as seen in the graph above).

The [3.11.1 release](https://sqlitebrowser.org/blog/version-3-11-1-released/) roughly a week and a half later is where we start to see meaningful numbers.

<p align="center" width="90%">
<iframe src="https://redash.sqlitebrowser.org/embed/query/2/visualization/4?api_key=EpRLVMjgh99gz6gwHCpNk5e0g7hauiE5Ag0vLYUY" width="100%" height="580"></iframe>
</p>

---

This graph shows similar information to the one above, but this time includes the version number.

The total number of "active users" on any given day can be higher than the graph above (and therefore less accurate), as this one includes an entry for each version of DB Browser for SQLite launched.

So, when someone  launches an older version of DB Browser for SQLite it will count them for that version, and then count them again if they upgrade to a newer version.

<p align="center">
<iframe src="https://redash.sqlitebrowser.org/embed/query/3/visualization/6?api_key=OsbgjsQpCzslb5b8RHX0WxjiQKiasIAENkpLLIAS" width="100%" height="580"></iframe>
</p>
