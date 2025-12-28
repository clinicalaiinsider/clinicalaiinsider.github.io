# CLAUDE.md - DataGodzilla Blog

This is a Jekyll-based blog for clinical informatics and healthcare AI content.

## Project Overview

- **Framework:** Jekyll 4.3+
- **Hosting:** GitHub Pages
- **Theme:** Custom minimal theme (no external gem)
- **Repository:** https://github.com/datagodzilla/datagodzilla.github.io

## Directory Structure

```
datagodzilla.github.io/
├── _config.yml           # Site configuration
├── _layouts/             # Page templates
│   ├── default.html      # Base wrapper
│   ├── home.html         # Landing page with card grid
│   ├── blog.html         # Blog archive
│   ├── post.html         # Individual blog posts
│   └── page.html         # Static pages
├── _includes/            # Reusable components
│   ├── header.html       # Site header with navigation
│   ├── footer.html       # Site footer
│   └── post-card.html    # Blog post card component
├── _posts/               # Blog posts (YYYY-MM-DD-title.md)
├── assets/
│   ├── css/main.css      # All styles (single file)
│   └── images/           # Images and media
│       └── posts/        # Post-specific images
├── index.html            # Home page
├── blog.html             # Blog archive page
├── about.md              # About page
├── projects.md           # Projects page
├── Gemfile               # Ruby dependencies
└── CLAUDE.md             # This file
```

## Common Tasks

### Creating a New Blog Post

1. Create file in `_posts/` with format: `YYYY-MM-DD-title-slug.md`
2. Add frontmatter:

```yaml
---
layout: post
title: "Your Post Title"
date: 2025-01-15
description: "Brief description for cards and SEO"
tags: [OHDSI, ATLAS, OMOP]
author: DataGodzilla
reading_time: 15
mermaid: true  # Enable if using Mermaid diagrams
---
```

3. Write content in Markdown
4. Add images to `assets/images/posts/`

### Adding Images to Posts

**Simple image:**
```markdown
![Alt text](/assets/images/posts/my-image.png)
*Caption text here*
```

**Styled image container:**
```html
<div class="image-container">
  <img src="/assets/images/posts/my-image.png" alt="Description">
  <div class="image-caption">Caption text here</div>
</div>
```

**Wide image (extends beyond content width):**
```html
<div class="image-container image-wide">
  <img src="/assets/images/posts/screenshot.png" alt="Description">
  <div class="image-caption">Caption text here</div>
</div>
```

### Adding Mermaid Diagrams

1. Ensure `mermaid: true` in post frontmatter
2. Use in content:

```html
<div class="diagram-container">
  <pre class="mermaid">
flowchart LR
    A[Start] --> B[Process]
    B --> C[End]
  </pre>
</div>
```

### Using Callout Boxes

```html
<div class="callout callout-info">
  <div class="callout-title">📚 Note Title</div>
  <p>Content here...</p>
</div>
```

Variants: `callout-info`, `callout-warning`, `callout-error`, `callout-success`

### Adding Stats/Metrics Display

```html
<div class="stats-grid">
  <div class="stat-card">
    <div class="stat-value">810M</div>
    <div class="stat-label">Patients</div>
  </div>
  <!-- More stat-cards... -->
</div>
```

### Adding Key Takeaways

```html
<div class="key-points">
  <h3>Key Takeaways</h3>
  <ol>
    <li><strong>Point one</strong> — Description</li>
    <li><strong>Point two</strong> — Description</li>
  </ol>
</div>
```

## Local Development

```bash
# Install dependencies
bundle install

# Start local server
bundle exec jekyll serve

# Build for production
bundle exec jekyll build
```

Site will be available at `http://localhost:4000`

## Deployment

The site auto-deploys via GitHub Actions when pushing to `master` branch.

Manual deployment:
```bash
git add .
git commit -m "Description of changes"
git push origin master
```

## Customization

### Changing Site Info
Edit `_config.yml`:
- `title` - Site name
- `description` - Site tagline
- `author` - Default post author
- `navigation` - Top nav links
- `features` - Home page feature cards
- `footer_*` - Footer configuration

### Modifying Styles
All CSS is in `assets/css/main.css`. Key sections:
- CSS Variables (line ~10) - Colors, fonts, spacing
- Typography (line ~300) - Post content styles
- Components - Cards, callouts, stats, etc.

### Adding New Layouts
Create file in `_layouts/` with `---\nlayout: default\n---` frontmatter.

## Content Guidelines

### Writing Style
- Clear, technical explanations
- Code examples with syntax highlighting
- Mermaid diagrams for architecture/workflows
- Screenshots with captions for UI demonstrations

### SEO
- Descriptive titles (50-60 chars)
- Meta descriptions via `description` frontmatter
- Proper heading hierarchy (h2, h3, h4)
- Alt text on all images

### Tagging
Common tags: `OHDSI`, `ATLAS`, `OMOP`, `ETL`, `NLP`, `BioBERT`, `PostgreSQL`, `Docker`, `Python`

## Troubleshooting

### Build Errors
```bash
# Clear cache
rm -rf _site .jekyll-cache

# Rebuild
bundle exec jekyll build --trace
```

### Mermaid Not Rendering
- Check `mermaid: true` in frontmatter
- Ensure diagram is wrapped in `<pre class="mermaid">` tags
- Check browser console for JS errors

### Images Not Showing
- Verify path starts with `/assets/images/`
- Check file exists and is committed to git
- Ensure filename matches exactly (case-sensitive)

## Files to Keep in Sync

When migrating content from existing blog:
1. Copy `_posts/*.md` files
2. Copy `assets/images/posts/*` images
3. Update image paths in posts if needed
4. Verify frontmatter matches new format

## Contact

Repository issues: https://github.com/datagodzilla/datagodzilla.github.io/issues
