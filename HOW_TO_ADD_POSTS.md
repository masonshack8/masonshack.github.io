# How to Add Posts to Your Homepage

## Quick Answer

**Posts in `_posts/` are automatically displayed on your homepage!** You don't need to do anything special - just create a properly formatted post file.

## Post File Requirements

### 1. File Naming Convention

Jekyll requires posts to follow this naming format:

```
YYYY-MM-DD-title.markdown
```

**Examples:**
- ✅ `2025-12-22-my-awesome-project.markdown`
- ✅ `2025-12-23-web-development-tips.markdown`
- ❌ `FirstPost.markdown` (missing date)
- ❌ `my-post.markdown` (missing date)

### 2. Front Matter (Post Header)

Every post must have front matter at the top with a valid date:

```yaml
---
layout: post
title:  "Your Post Title"
date:   2025-12-22 12:00:00 -0500
categories: category1 category2
description: "Description of your post"
image: /assets/images/your-image.jpg
---
```

**Important:**
- The `date` must be a real date (not `YYYY-MM-DD`)
- Format: `YYYY-MM-DD HH:MM:SS -0500`
- The date in the filename should match the date in front matter

### 3. Post Content

After the front matter, add your content in Markdown:

```markdown
---
layout: post
title:  "My First Post"
date:   2025-12-22 12:00:00 -0500
categories: blog
description: "This is my first blog post"
---

Your post content goes here. You can use **Markdown** formatting.
```

## Step-by-Step: Creating a New Post

### Step 1: Create the File

Create a new file in `_posts/` with the correct naming format:

```
_posts/2025-12-22-my-new-post.markdown
```

### Step 2: Add Front Matter

Add the required front matter:

```yaml
---
layout: post
title:  "My New Post"
date:   2025-12-22 14:30:00 -0500
categories: projects
description: "Description of my new post"
---
```

### Step 3: Add Content

Write your post content below the front matter:

```markdown
## Introduction

This is my new post content...

## More Content

Add more sections as needed.
```

### Step 4: Save and View

1. Save the file
2. If Jekyll is running, it will auto-regenerate
3. Refresh your browser to see the new post on the homepage

## Why Posts Might Not Appear

### ❌ Invalid Date Format

**Problem:**
```yaml
date: YYYY-MM-DD HH:MM:SS -0500  # This is a placeholder!
```

**Solution:**
```yaml
date: 2025-12-22 12:00:00 -0500  # Use a real date
```

### ❌ Wrong Filename Format

**Problem:**
- `FirstPost.markdown` (no date)
- `my-post.markdown` (no date)

**Solution:**
- `2025-12-22-first-post.markdown` (with date)

### ❌ Missing Front Matter

**Problem:** File doesn't have `---` at the top

**Solution:** Always include front matter with at least:
```yaml
---
layout: post
title: "Title"
date: 2025-12-22 12:00:00 -0500
---
```

## Example: Complete Post File

**Filename:** `_posts/2025-12-22-getting-started.markdown`

```yaml
---
layout: post
title:  "Getting Started with Jekyll"
date:   2025-12-22 10:00:00 -0500
categories: tutorial jekyll
description: "Learn how to create your first Jekyll post"
image: /assets/images/jekyll-logo.png
---

## Introduction

Welcome to Jekyll! This is how you create a post.

## Content

Add your content here using Markdown formatting.
```

## Using the Template

You can use the template file I created:

1. Copy `_posts/TEMPLATE-post-with-media.markdown`
2. Rename it to `YYYY-MM-DD-your-title.markdown`
3. Update the front matter with your information
4. Replace `YYYY-MM-DD HH:MM:SS` with a real date

## Verifying Posts Appear

1. Check that your file is in `_posts/` directory
2. Verify the filename has the date format: `YYYY-MM-DD-title.markdown`
3. Check the front matter has a valid date
4. Restart Jekyll server if needed: `bundle exec jekyll serve`
5. Check the homepage - posts appear automatically in tile format

## Troubleshooting

**Post not showing on homepage?**
- ✅ Check filename format: `YYYY-MM-DD-title.markdown`
- ✅ Check date in front matter is valid (not `YYYY-MM-DD`)
- ✅ Make sure file is in `_posts/` directory
- ✅ Restart Jekyll server
- ✅ Clear browser cache

**Post shows but looks wrong?**
- Add a `description` field to front matter
- Add an `image` field for featured image
- Add `categories` for tags

## Summary

**You don't need to manually add posts to the homepage!** Just:
1. Create a file in `_posts/` with proper naming: `YYYY-MM-DD-title.markdown`
2. Add front matter with valid date
3. Add your content
4. Save - it appears automatically! 🎉

