# Himanshu Patel's Blog

A personal blog focused on distributed systems, platform engineering, engineering leadership, and software architecture at scale.

**Live Site**: [https://himanshu-g-patel.github.io/blog](https://himanshu-g-patel.github.io/blog)

## About

This blog shares insights from 18 years of building scalable enterprise platforms, leading engineering teams, and solving complex technical challenges in fintech and enterprise SaaS. Topics include:

- Distributed systems and data infrastructure
- Platform engineering and cloud-native architecture
- Engineering leadership and team building
- Technical deep dives on Apache Calcite, Trino, Kafka, and more
- 0→1 product development experiences

## Tech Stack

- **Framework**: Jekyll (Ruby-based static site generator)
- **Theme**: [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) (dark skin)
- **Deployment**: GitHub Pages with automated deployment via GitHub Actions
- **Markdown**: Kramdown processor
- **Ruby**: 3.2.0

## Development

### Prerequisites

- Ruby 3.2.0
- Bundler

### Quick Start

```bash
# Install dependencies
bundle install

# Start local development server with drafts and live reload
make server

# Or manually
bundle exec jekyll serve --incremental --watch --drafts
```

The site will be available at `http://localhost:4000/blog`

**Note**: Changes to `_config.yml` require a server restart.

### Content Management

```bash
# Create a new draft post
make draft

# View tag usage across posts
make tags

# Count words in all posts
make words

# View git diff with word-level changes
make diff
```

### Building for Production

```bash
bundle exec jekyll build --baseurl "/blog"
```

## Project Structure

```
.
├── _posts/          # Published blog posts (YYYY-MM-DD-title.md)
├── _drafts/         # Draft posts (visible with --drafts flag)
├── _data/           # Site data (navigation, etc.)
├── _includes/       # Custom template includes
├── images/          # Blog images and assets
├── _config.yml      # Jekyll configuration
├── about.md         # About page
├── resume.pdf       # Resume
└── Makefile         # Development commands
```

## Deployment

The site automatically deploys to GitHub Pages when pushing to the `main` branch. The deployment is handled by GitHub Actions (see `.github/workflows/jekyll.yml`).

## Writing Posts

Posts should be placed in `_posts/` with the filename format: `YYYY-MM-DD-title.md`

### Post Template

```yaml
---
title: Post Title
tags: tag1 tag2
toc: true
header:
  overlay_image: /images/header-XXX
  overlay_color: "#000"
  overlay_filter: "0.5"
excerpt: "Post summary"
---

Your content here...
```

## Author

**Himanshu Patel**
Senior Engineering Manager at Workday
[LinkedIn](https://www.linkedin.com/in/himanshupatel26/) | [Email](mailto:himanshu.patel.26@gmail.com)

## License

Content is copyrighted. Code samples within blog posts may be used freely.
