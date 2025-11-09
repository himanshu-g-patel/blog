# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based personal blog using the Minimal Mistakes remote theme. The blog is deployed automatically to GitHub Pages via GitHub Actions workflow on every push to main.

**Site Configuration:**
- Base URL: https://himanshu-g-patel.github.io/blog
- Theme: Minimal Mistakes (dark skin)
- Ruby version: 3.2.0
- Markdown processor: Kramdown

## Development Commands

### Local Development
```bash
# Start local Jekyll server with drafts and live reload
make server
# Or manually:
bundle exec jekyll serve --incremental --watch --drafts
```

**Important:** Changes to `_config.yml` require a server restart. The `--incremental` flag does not pick up config changes.

### Content Management
```bash
# Create a new draft post (will prompt for slug)
make draft

# View tag usage statistics across all posts
make tags

# Count words in all posts
make words

# View git diff with word-level changes
make diff
```

### Build & Deploy
```bash
# Build site for production
bundle exec jekyll build --baseurl "/blog"

# Install/update dependencies
bundle install
```

The site auto-deploys to GitHub Pages when pushing to `main`. The GitHub Actions workflow builds and deploys automatically (see `.github/workflows/jekyll.yml`).

## Architecture & Structure

### Directory Layout
- `_posts/` - Published blog posts (format: YYYY-MM-DD-title.md)
- `_drafts/` - Draft posts (not published, viewable with `--drafts` flag)
- `_data/navigation.yml` - Site navigation menu configuration
- `_includes/` - Custom template includes
- `_site/` - Generated site output (git-ignored)
- `images/` - Blog images and assets

### Content Structure

**Post Front Matter** (see `post_template.md`):
```yaml
---
title: Post Title
tags: tag1 tag2
toc: true                    # Enable table of contents
header:
  overlay_image: /images/header-XXX
  overlay_color: "#000"
  overlay_filter: "0.5"
excerpt: "Post summary"
---
```

**Default Post Settings** (_config.yml:45-56):
- Layout: single
- Author profile: enabled
- Comments, sharing, related posts: disabled
- TOC label: "On this page"

### Theme Configuration

The site uses the Minimal Mistakes remote theme with heavy customization in `_config.yml`:
- Remote theme loaded via `jekyll-remote-theme` plugin
- Custom pagination settings (v2): 10 posts per page
- Site metadata (author, social links) configured in `_config.yml:30-39`
- Navigation menu defined in `_data/navigation.yml`

### Key Plugins
- `jekyll-feed` - RSS feed generation
- `jekyll-paginate-v2` - Advanced pagination
- `jekyll-remote-theme` - Remote theme support
- `jekyll-redirect-from` - URL redirection support
- `jekyll-sitemap` - Sitemap generation
- `jekyll-include-cache` - Performance optimization

## Content Creation Workflow

1. Create draft: `make draft` (enters slug when prompted)
2. Edit draft in `_drafts/`
3. Test locally: `make server` (includes drafts)
4. Move to `_posts/` with date prefix: `YYYY-MM-DD-slug.md`
5. Commit and push to `main` for auto-deployment

## Important Notes

- Post filenames in `_posts/` MUST follow the `YYYY-MM-DD-title.md` format
- Images referenced in posts should be in `/images/` directory
- The `baseurl: "/blog"` is critical for proper asset and link resolution
- Custom navigation pages (about.md, manager.md, reading-list.md, quotes.md) are in the root directory
