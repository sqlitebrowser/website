---
title: Live databases can be public .. and more updates
author: Chris Locke
date: '2023-04-23'
slug: live-databases-can-be-public
categories:
  - dbhub.io
tags: dbhub.io
---

Another week, and another series of exciting updates to DBHub.io

## Live databases can now be public

The public/private setting can now be chosen when uploading
a live database, and can also be changed afterwards in the
Settings page for any database.  
Previously, live databases were private-only as we hadn't wired up the permissions.

![](/images/Screenshot_20230423_093548.png)

Now, they can be shared with other users.  By default, sharing allows for read-only access, but you can switch this to read-write access on a user-by-user basis.


## Live databases can now have associated metadata set

![](/images/Screenshot_20230430_134515.png)

As well as a one-line description, you can add a source URL (eg to reference an external source location) plus a Markdown supported full description field.  

## Live databases can be downloaded

![](/images/Screenshot_20230430_135002.png)

Live databases can now be downloaded easily through the web interface.

## Live databases now support discussions

![](/images/Screenshot_20230430_141802.png)

Useful when collaborating with others on a live database, and you
    want to discuss some aspect of it.  Markdown is supported.

## "Maximum number of rows to show" setting now operational

![](/images/Screenshot_20230430_142202.png)

The "Database View" page now honours the user's
    "Maximum number of rows to show" preference setting.  
    This is a fix, as this was recently updated, and in that update it defaulted to just showing a small number of rows, not taking into account the preference value.

## Other fixes

* The user "Settings" page is now "Preferences"  
There was a link to 'settings' for the database, and 'settings' for the user.  It seemed sensible to differentiate these.

* Raised the number of allowed columns in a table from 100 to 400  
    Previously, uploaded databases were limited to 100 columns in
    their tables.  That was causing errors for some people, so we've
    raised that to 400.  We'll keep an eye on it, and see if it
    needs to be raised further.  
    If you're using databases which hit this limit, please raise a [support issue](https://github.com/sqlitebrowser/dbhub.io/issues/new/choose) so we can increase it further.
    
## A Quick Thanks

We've noticed an increase in users trying DBHub.io.  Thank you for taking the time to have a look and trying us out.  If you encounter any problems, let us know as we work hard to make your use of our software easy and enjoyable. 
