# About this repository

This repo contains the source for the [sqlitebrowser.org](sqlitebrowser.org)
website. It uses [CommonMark](https://en.wikipedia.org/wiki/Markdown)
(also known as Markdown) for the content. It uses Hugo (version 0.111.3)
to format the pages. ~~with
[Blogdown](https://github.com/rstudio/blogdown) to provide
the theme and general structure.~~

~~To create changes, install Blogdown and point it at a
local copy of this repository.  It should work pretty
automatically. :smile:~~

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

Docker can encapsulate all the necessary tools into a single container
without affecting any other software on the host operating system.
To use Docker, install it on your computer using any of the guides on the Internet.
Then start the Docker container using these commands:

```bash
cd <sqlitebrowser-website-directory>
docker run -it --rm -p 1313:1313 -v $(pwd):/home/hugo/app mengzyou/hugo
```

The container automatically builds the site and then watches all the files
in the directory and re-builds the site as needed.
Point your browser to [http://localhost:1313](http://localhost:1313) to view the site.

As you edit files, Hugo will rebuild the site, and display the update in the browser.

To exit the Docker container, simply ^C (Ctl-C) to get back to the terminal shell.
