# blog

Source for [www.gamare.net](https://www.gamare.net) — Sam's Thoughts.

Built with [Jekyll](https://jekyllrb.com/) and published automatically by
GitHub Actions on every push to `master` (see `.github/workflows/pages.yml`).
No local build step is required to publish — write a post, commit, push.

## Writing a post

Add a file to `_posts/` named `YYYY-MM-DD-slug.md`:

```markdown
---
title: 'Post Title'
date: '2026-08-31T09:00:00+05:30'
author: 'Sam Gamare'
excerpt: 'One or two sentences shown on the listing page.'
layout: post
permalink: /blog/2026/08/31/slug/
image: /assets/images/icons/icon-application-secrets-management.svg
tags:
    - Tag One
---

Body in markdown.
```

Push to `master` and the site rebuilds and redeploys within a couple of minutes.

## Local preview (optional)

```bash
bundle install
bundle exec jekyll serve --livereload
```
