# About this repository

This repo contains the source for the [sqlitebrowser.org](sqlitebrowser.org)
website. It uses [CommonMark](https://en.wikipedia.org/wiki/Markdown)
(also known as Markdown) for the content. It uses Hugo (version 0.111.3)
to format the pages.
There are Dockfiles for both interactive development and final builds.

Feel free to change things around, and submit PR's as desired.

License not yet decided.  It'll probably be CC0, or maybe
the same as DB4S itself.

## Editing the site

All the site pages are contained within the `/content` directory.

Hugo creates its output for the site in the `/docs/` directory.

Hugo requires a YAML header to appear
above the (standard) Markdown for every page in the site.
The minimal header must include a `title` surrounded by two `---` lines.
Other useful header lines include:

```yaml
---
title: Some-title
author: Author-Name
date: "yyyy-mm-dd"
slug: name-to-show-in-the-URL
categories: [comma,separated,categories,"to connect pages"]
tags: [comma,separated,tags]
---
```

To create a new page, create a Markdown (`.md`) document using the header above in the proper directory. 
Name it as desired.

To create a new blog post, create a document named `yyyy-mm-dd-subject-of-post.md` in the `/content/blog` directory.
Set the proper date in the full header above.

## Running in Docker

Docker encapsulates all the necessary tools for running Hugo
into a single container
without affecting any other software on the host operating system.
This is also important because Hugo versions don't always preservee
backward compatibility.
Using Docker ensures that you and all your collaborators are always using
the same versions of the tool.

To use Docker, install it on your computer using any of the guides on the Internet.

There are two Dockerfiles in this repo: one for editing the site interactively,
and one for creating the final build.
Create them by running these commands. (This is a one-time action.)

```bash
docker build -f Dockerfile-serve -t hugo-server .
docker build -f Dockerfile-build -t hugo-build . 
```

### Interactive editing

Start the Docker server container using these commands:

```bash
cd <sqlitebrowser-website-directory>
docker run -it --rm -p 1313:1313 -v $(pwd):/home/hugo/app hugo-server
```

The container watches all the files
in the directory and re-builds as needed.
Point your browser to [http://localhost:1313](http://localhost:1313) to view changes.

As you edit files, Hugo will rebuild and display the updated pages in the browser.

To exit the Docker container, simply ^C (Ctl-C) to get back to the terminal shell.

### Build the site

After all the edits are complete, use the `hugo-build` container
to create the full site in the `docs` directory.
To do this:

```bash
cd <sqlitebrowser-website-directory>
docker run --rm -v $(pwd):/home/hugo/app hugo-build
```

Verify that the resulting files are correct with these commands and browse to [http://localhost:1313](http://localhost:1313)

```bash
cd docs
python -m http.server 1313
```
