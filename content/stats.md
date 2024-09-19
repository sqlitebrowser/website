---
title: Statistics
date: "2019-04-08T22:43:15+11:00"
---

**Note** - *The data behind these graphs (created using [Redash](https://redash.io)) automatically updates every hour.*

# Monthly downloads

These Monthly Download stats begin in August 2018, when we moved our primary
download location from GitHub to our own infrastructure.

<iframe src="https://redash.sqlitebrowser.org/embed/query/68/visualization/112?api_key=E0dTQNaUQLHB75FNTChf13K132VrsrC0TWffi3EL" width="100%" height="580"></iframe>

GitHub does make download stats available through their API, and it would be
useful to add the historical (and ongoing) downloads from GitHub to this too.

There's about 1/2 million downloads of our 3.12.2 release from GitHub (as of
2023-04-28), that's not counted in the graph above.

The missing chunk of download numbers (green) around the start of 2021, was
when the download servers weren't saving the download info in the backend
database properly. 🤦

The [3.12 series releases](https://sqlitebrowser.org/blog/version-3-12-0-released/)
(green) show the monthly downloads are mostly in the 140k to 180k range through
to early 2024 where they jump to around ~275k per month.

The current major release series (3.13, blue) is continuing at about the same
monthly download range of ~275k per month.


# Monthly active users - non version specific count

This "Monthly Active Users" graph just shows a simple count of how many unique
IP addresses (per month) are checking whether a newer version of DB Browser for
SQLite is available.

<iframe src="https://redash.sqlitebrowser.org/embed/query/72/visualization/120?api_key=93gA7RFSBC2QUO5UDJ4wPy3XyW4mJf6mNfzTd37l" width="100%" height="580"></iframe>

We don't have data prior to our 3.11.0 release, as we used to primarily have
our downloads on GitHub which doesn't share much information.  As we serve our
own downloads now, this information is available.

The numbers mostly start in October 2018, with our [first Alpha release
for 3.11.0](https://sqlitebrowser.org/blog/first-alpha-release-for-3-11-0/).

With the first release in the [3.11 series](https://sqlitebrowser.org/blog/version-3-11-0-released/)
in Feb 2019, we start to see meaningful numbers.


# Monthly active users - version specific count

This graph shows similar information to the one above, but this time includes
the version number.

<iframe src="https://redash.sqlitebrowser.org/embed/query/70/visualization/116?api_key=4llzi2AnTVkuuens4fWWacQt8eKlnvv6mepTTpIJ" width="100%" height="580"></iframe>

The total number of "active users" in any given month can be slightly higher
here than the graph above it, as this one includes an entry for each version of
DB Browser for SQLite launched.

For example, when someone  launches an older version of DB Browser for SQLite
it will count them for that version, and then count them again if they upgrade
to a newer version.

So, there is some potential for double counting of a user in this one.