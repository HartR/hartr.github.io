# Hart's Notebook

Minimal GitHub Pages site with a home page, blog, photo album, and CV link.

## Add a blog post

Create a Markdown file in `_posts/` named like:

```text
YYYY-MM-DD-title.md
```

Use this front matter:

```yaml
---
layout: post
title: "Post Title"
description: "One-sentence summary."
date: YYYY-MM-DD
---
```

## Add photos

Upload images to:

```text
assets/photos/
```

Supported extensions are `.jpg`, `.jpeg`, `.png`, `.gif`, and `.webp`. The Photo Album page lists them automatically after GitHub Pages rebuilds the site.

## CV

The public CV link points to `assets/cv.pdf`. The source is `resume.tex`, and the existing GitHub Action can rebuild the PDF manually.
