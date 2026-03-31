# OtterFin Community Website

Source for [otterfin.org](https://otterfin.org) — the OtterFin Community and project website.

Built with [Hugo](https://gohugo.io). No third-party theme; all templates are custom and live in `layouts/`.

## Local development

```bash
hugo server
```

Opens at [http://localhost:1313](http://localhost:1313). Hugo watches for changes and reloads automatically.

## Structure

```
content/updates/     # Blog posts, served at /updates/
layouts/             # Hugo templates
  index.html         # Home page (standalone, does not use baseof)
  _default/
    baseof.html      # Shared nav + footer for all non-home pages
    list.html        # Updates index page
    single.html      # Individual post page
static/
  css/otterfin.css   # All site CSS
  logo.svg
```

## Adding an update post

Create a file in `content/updates/` with the date prefix:

```
content/updates/20260401-my-post-title.md
```

```markdown
---
title: "My post title"
date: 2026-04-01
draft: false
---

Post content here.
```

The date prefix keeps files sorted in the directory. Hugo uses the `date` field in front matter for display — the filename prefix is for organization only.

Set `draft: false` to publish. Run `hugo server --buildDrafts` to preview drafts locally.

## Building for production

```bash
hugo
```

Output goes to `public/`. The `public/` directory is gitignored — deployment is handled separately.
