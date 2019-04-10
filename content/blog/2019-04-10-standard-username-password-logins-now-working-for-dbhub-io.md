---
title: Standard username/password logins now working for DBHub.io
author: Justin Clift
date: '2019-04-10'
slug: standard-username-password-logins-now-working-for-dbhub-io
categories: []
tags:
  - dbhub.io
---

A small, but important, update about [DBHub.io](https://dbhub.io) logins. :wink:

People can now create accounts using their own username/password again, instead of needing  to login via GitHub, Google, or LinkedIn.

It used to work (ages ago), but Auth0 found a security problem with the version of NodeJS they were using, so disabled it for everyone last year.  It was fixable by changing some stuff, which has now been done.

On a related note... login (using username/password) only works if "3rd party cookies" aren't blocked in your web browser.

If your web browser does block them, you can work around the problem by adding an "Allow" rule for "https://dbhub.eu.auth0.com".