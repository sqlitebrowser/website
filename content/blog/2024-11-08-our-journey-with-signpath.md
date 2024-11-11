---
title: Signing Windows executables - Our journey with SignPath
author: SeongTae Jeong
date: '2024-11-08'
slug: signing-windows-executables-our-journey-with-signpath
categories:
  - db4s
tags:
  - signpath
  - windows
---

# Our Journey with SignPath: Code Signing for Windows Binaries

When distributing software, code signing is essential to ensure our users can trust the software they download,
especially on an operating system like Windows that displays security warnings for unsigned software.

So for us, code signing is not just an option, but a necessity to validate software binaries, prevent tampering, and
for the convenience of our users.


## A Little Background on This Journey

It's not difficult to code sign and notarize software binaries for Apple macOS.  In fact, there's only one option.

However, for Windows binaries, there are a number of companies offering code signing services at varying costs, which
made it difficult to choose.  One of our team members learned about [SignPath](https://signpath.org),
which provides free code signing services for FOSS projects, and it seemed like a logical choice for many reasons
("free and seems legit"), so we contacted the SignPath team.


## The Challenge We Faced

Getting started with code signing wasn't difficult, as SignPath provided us with well-written documentation. However,
our existing CI/CD platform - GitHub Actions - wasn't supported by SignPath, so we needed to configure a new CI
pipeline for AppVeyor to sign and deploy our software code.

We learned that SignPath was also supporting GitHub Actions in a private beta, so we asked for access, which we
received after a few weeks.

There have been some minor bugs in the integration with GitHub Actions, but after reaching out to the SignPath team 
they were fixed within a few days.

As a result, we're now successfully deploying code-signed Windows binaries to our users using our existing GitHub
Actions.


## Personal Impressions and Reflections

We are now able to distribute code-signed Windows binaries to our users thanks to [SignPath's well-written
documentation](https://about.signpath.io/documentation/signing-code), quick response to issues, and friendly support.

We also appreciate the fact that they don't put a financial burden on FOSS projects. :D

If you're looking to get your code signed for Windows binaries, I highly recommend that you consider working with the
awesome [SignPath team](https://signpath.org/apply).

Finally, a huge thanks to [the SignPath team](https://about.signpath.io/team), and also a huge thanks to the users who
love our application. :)


## Further information

* [SignPath Code Signing for Open Source Software projects](https://signpath.org/about)
* [SignPath Code Signing for Commercial projects](https://signpath.io/code-signing)
* [Documentation for SignPath Code Signing](https://about.signpath.io/documentation/signing-code)