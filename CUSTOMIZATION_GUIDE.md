# How to Customize Your Jekyll Portfolio Website

This guide explains the different ways you can customize your Jekyll portfolio website.

## 1. Basic Site Settings (`_config.yml`)

Edit `_config.yml` to change:
- **Site title**: Change `title: Your awesome title` to your name or portfolio title
- **Email**: Update `email: your-email@example.com` with your email
- **Description**: Update the description for SEO and social sharing
- **Social media**: Update `twitter_username` and `github_username`
- **URL**: Set your `url` if deploying to a custom domain

**Important**: After editing `_config.yml`, restart your Jekyll server (`bundle exec jekyll serve`).

## 2. Custom CSS Styling

### Option A: Using `assets/css/custom.css` (Simple)
The file `assets/css/custom.css` has been created for you. Add your custom styles there.

To use it, add this to your `_config.yml`:
```yaml
# Add to _config.yml
sass:
  style: compressed
```

Then reference it in your layout (see Option C for layout overrides).

### Option B: Using SCSS (`_sass/minima/custom-styles.scss`) (Recommended)
The file `_sass/minima/custom-styles.scss` has been created. This file automatically overrides Minima theme styles.

You can override Minima's SCSS variables:
- `$brand-color`: Main brand color
- `$brand-color-light`: Lighter shade
- `$brand-color-dark`: Darker shade
- `$base-font-family`: Font family
- `$base-font-size`: Base font size
- `$spacing-unit`: Spacing unit
- `$grey-color-light`, `$grey-color-dark`: Gray shades

## 3. Override Theme Layouts

Create a `_layouts` directory to override theme layouts:

```
_layouts/
  ├── default.html    # Override the default layout
  ├── home.html       # Override the home page layout
  ├── page.html       # Override page layouts
  └── post.html       # Override blog post layouts
```

To see what layouts are available, check the Minima theme source:
https://github.com/jekyll/minima/tree/master/_layouts

## 4. Override Theme Includes

Create an `_includes` directory to override theme includes:

```
_includes/
  ├── header.html     # Customize site header
  ├── footer.html     # Customize site footer
  └── head.html       # Add custom scripts/styles to <head>
```

## 5. Edit Content Files

- **Homepage**: Edit `index.markdown`
- **About page**: Edit `about.markdown`
- **Blog posts**: Edit files in `_posts/` directory
- **404 page**: Edit `404.html`

## 6. Add Custom Pages

Create new `.markdown` files in the root directory with front matter:

```markdown
---
layout: page
title: Contact
permalink: /contact/
---

Your contact page content here.
```

## Quick Start Examples

### Change Site Title and Description
Edit `_config.yml`:
```yaml
title: Mason's Portfolio
description: A showcase of my work and projects
```

### Change Colors
Edit `_sass/minima/custom-styles.scss`:
```scss
$brand-color: #3498db;
$brand-color-dark: #2980b9;
```

### Add Custom CSS
Edit `assets/css/custom.css`:
```css
body {
  background-color: #f5f5f5;
}

h1 {
  color: #2c3e50;
  font-weight: 700;
}
```

## Testing Your Changes

1. Start the Jekyll server: `bundle exec jekyll serve`
2. Open your browser to `http://localhost:4000`
3. Make changes to your files
4. Refresh the browser to see updates (Jekyll auto-regenerates)

## Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [Minima Theme Documentation](https://github.com/jekyll/minima)
- [Jekyll Theme Customization](https://jekyllrb.com/docs/themes/#overriding-theme-defaults)

