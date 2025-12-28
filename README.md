# DataGodzilla Blog

A clean, minimal Jekyll blog for clinical informatics and healthcare AI content.

![Theme Preview](docs/preview.png)

## Features

- **Clean, minimal design** — Inspired by Claude Code Commands directory
- **Card-based home page** — Blog posts displayed as interactive cards
- **Content-focused post layout** — Optimized for technical writing
- **Mermaid diagrams** — Built-in support for flowcharts and diagrams
- **Responsive design** — Works on desktop and mobile
- **Fast loading** — Single CSS file, no JavaScript frameworks
- **SEO optimized** — Meta tags, Open Graph, sitemap

## Quick Start

### Prerequisites

- Ruby 2.7+ ([Installation guide](https://www.ruby-lang.org/en/documentation/installation/))
- Bundler (`gem install bundler`)

### Installation

```bash
# Clone the repository
git clone https://github.com/datagodzilla/datagodzilla.github.io.git
cd datagodzilla.github.io

# Install dependencies
bundle install

# Start local server
bundle exec jekyll serve
```

Open `http://localhost:4000` in your browser.

### Creating Your First Post

Create a file in `_posts/` with the naming format `YYYY-MM-DD-title.md`:

```markdown
---
layout: post
title: "My First Post"
date: 2025-01-15
description: "A brief introduction to my blog"
tags: [Introduction, Hello]
mermaid: true
---

## Welcome!

This is my first blog post using the DataGodzilla theme.
```

## Configuration

Edit `_config.yml` to customize:

```yaml
title: Your Site Name
description: Your site description
author: Your Name

# Social links
github_username: yourusername
linkedin_username: yourprofile

# Navigation
navigation:
  - title: Blog
    url: /blog/
  - title: About
    url: /about/
```

## Directory Structure

```
├── _config.yml        # Site configuration
├── _layouts/          # Page templates
├── _includes/         # Reusable components
├── _posts/            # Blog posts
├── assets/
│   ├── css/           # Styles
│   └── images/        # Media files
├── index.html         # Home page
├── blog.html          # Blog archive
├── about.md           # About page
└── CLAUDE.md          # Instructions for Claude Code
```

## Writing Features

### Callouts

```html
<div class="callout callout-info">
  <div class="callout-title">📚 Note</div>
  <p>Important information here.</p>
</div>
```

### Mermaid Diagrams

```html
<div class="diagram-container">
  <pre class="mermaid">
flowchart LR
    A --> B --> C
  </pre>
</div>
```

### Stats Display

```html
<div class="stats-grid">
  <div class="stat-card">
    <div class="stat-value">100K</div>
    <div class="stat-label">Users</div>
  </div>
</div>
```

### Images with Captions

```html
<div class="image-container">
  <img src="/assets/images/posts/screenshot.png" alt="Description">
  <div class="image-caption">Caption text</div>
</div>
```

## Deployment

### GitHub Pages

1. Push to `master` branch
2. Enable GitHub Pages in repository settings
3. Site deploys automatically

### Manual Build

```bash
bundle exec jekyll build
# Output in _site/ directory
```

## Customization

### Colors

Edit CSS variables in `assets/css/main.css`:

```css
:root {
    --color-text: #1f2937;
    --color-accent: #2563eb;
    --color-bg: #ffffff;
    /* ... */
}
```

### Fonts

The theme uses:
- **Inter** — UI and headings
- **JetBrains Mono** — Code blocks

Change in `_layouts/default.html` Google Fonts link.

## Migration from Existing Blog

1. Copy your `_posts/` directory
2. Copy `assets/images/` content
3. Update frontmatter to match new format
4. Test locally before deploying

## Claude Code Integration

This project includes `CLAUDE.md` with detailed instructions for using Claude Code to maintain the blog. Claude Code can:

- Create new blog posts
- Add images and diagrams
- Update site configuration
- Fix build issues

## License

MIT License - feel free to use for your own blog!

## Credits

- Theme inspired by [Claude Code Commands](https://claudecodecommands.directory/)
- Built with [Jekyll](https://jekyllrb.com/)
- Fonts from [Google Fonts](https://fonts.google.com/)
- Diagrams powered by [Mermaid](https://mermaid.js.org/)
