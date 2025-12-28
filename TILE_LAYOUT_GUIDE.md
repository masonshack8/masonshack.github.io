# Square Tile Layout Guide

Your Jekyll site now displays posts in a beautiful square tile grid layout!

## How It Works

Posts are automatically displayed as square tiles on your homepage. Each tile shows:
- Featured image (if provided)
- Post title
- Description
- Date
- Categories

## Adding Featured Images to Posts

To add a featured image that appears in the tile, add an `image` field to your post's front matter:

```yaml
---
layout: post
title:  "My Awesome Project"
date:   2025-12-22 12:00:00 -0500
categories: projects web-development
description: "A showcase of my latest web development project"
image: /assets/images/Step_300mm.png
---
```

### Image Requirements

- **Recommended size**: 600x600px or larger (square images work best)
- **Format**: JPG, PNG, or WebP
- **Location**: Place images in `assets/images/` directory
- **Path**: Use `/assets/images/your-image.jpg` in the front matter

### Example Post with Image

```yaml
---
layout: post
title:  "My Portfolio Project"
date:   2025-12-22 12:00:00 -0500
categories: portfolio design
description: "A beautiful portfolio website built with modern web technologies"
image: /assets/images/portfolio-thumbnail.jpg
---
```

## Without Featured Image

If you don't add an `image` field, the tile will show a placeholder with an icon. The tile will still look great!

## Customizing the Tiles

### Change Tile Colors

Edit `assets/css/custom.css` and modify:

```css
.post-tile-placeholder {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}
```

Change the gradient colors to match your brand.

### Change Tile Size

Modify the grid in `assets/css/custom.css`:

```css
.post-tiles {
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  /* Change 300px to adjust minimum tile width */
}
```

### Change Hover Effect

Modify the hover transform:

```css
.post-tile:hover {
  transform: translateY(-5px); /* Change -5px to adjust lift amount */
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.15);
}
```

## Responsive Design

The tile layout is fully responsive:
- **Desktop**: 3-4 tiles per row (depending on screen size)
- **Tablet**: 2 tiles per row
- **Mobile**: 1 tile per row

## Tips

1. **Use square images** (1:1 aspect ratio) for best results
2. **Optimize images** before uploading to keep your site fast
3. **Add descriptions** to your posts - they appear in the tiles
4. **Use categories** - they appear as tags on each tile
5. **Keep titles short** - they look better in the tiles

## Example: Complete Post Setup

```yaml
---
layout: post
title:  "E-Commerce Platform"
date:   2025-12-22 12:00:00 -0500
categories: web-development e-commerce
description: "A full-stack e-commerce platform with payment integration and admin dashboard"
image: /assets/images/ecommerce-thumbnail.jpg
---

Your post content here...
```

This will create a beautiful tile with:
- Your thumbnail image
- Title: "E-Commerce Platform"
- Description: "A full-stack e-commerce platform..."
- Date: Dec 22, 2025
- Categories: web-development, e-commerce

## Troubleshooting

**Image not showing?**
- Check the path in front matter starts with `/assets/images/`
- Make sure the image file exists
- Verify the image filename matches exactly (case-sensitive)

**Tiles look weird?**
- Make sure `_layouts/home.html` exists
- Check that `assets/css/custom.css` is loaded (it should be automatic)
- Clear your browser cache

**Want to go back to list view?**
- Delete or rename `_layouts/home.html` to restore the default layout

