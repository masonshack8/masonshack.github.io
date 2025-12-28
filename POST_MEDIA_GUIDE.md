# Guide: Adding Images, Videos, Files, and Descriptions to Jekyll Posts

## Post File Structure

Jekyll posts must be named: `YEAR-MONTH-DAY-title.markdown` (or `.md`)

Example: `2025-12-22-my-awesome-project.markdown`

## Front Matter (Post Header)

Every post needs front matter at the top:

```yaml
---
layout: post
title:  "Your Post Title"
date:   2025-12-22 12:00:00 -0500
categories: category1 category2
description: "This description appears in RSS feeds and search results"
---
```

## 1. Adding Images

### Step 1: Place Images in Assets Folder
Put your images in: `assets/images/`

### Step 2: Reference in Markdown

**Basic syntax:**
```markdown
![Alt text]({{ "/assets/images/your-image.jpg" | relative_url }})
```

**With caption (HTML):**
```html
<figure>
  <img src="{{ '/assets/images/your-image.jpg' | relative_url }}" alt="Description">
  <figcaption>Your caption here</figcaption>
</figure>
```

**Responsive image:**
```html
<img src="{{ '/assets/images/your-image.jpg' | relative_url }}" 
     alt="Description" 
     style="max-width: 100%; height: auto;">
```

### Supported Image Formats
- `.jpg` / `.jpeg`
- `.png`
- `.gif`
- `.svg`
- `.webp`

## 2. Adding Videos

### Option A: YouTube/Vimeo (Recommended)

**YouTube:**
```html
<iframe width="560" height="315" 
        src="https://www.youtube.com/embed/VIDEO_ID" 
        frameborder="0" 
        allowfullscreen>
</iframe>
```

Replace `VIDEO_ID` with your video's ID from the YouTube URL.

**Vimeo:**
```html
<iframe src="https://player.vimeo.com/video/VIDEO_ID" 
        width="640" height="360" 
        frameborder="0" 
        allowfullscreen>
</iframe>
```

### Option B: Local Video Files

1. Place videos in: `assets/videos/`
2. Use HTML5 video tag:

```html
<video width="100%" controls>
  <source src="{{ '/assets/videos/your-video.mp4' | relative_url }}" type="video/mp4">
  Your browser does not support the video tag.
</video>
```

**With poster (thumbnail):**
```html
<video width="100%" controls 
       poster="{{ '/assets/images/video-thumbnail.jpg' | relative_url }}">
  <source src="{{ '/assets/videos/your-video.mp4' | relative_url }}" type="video/mp4">
</video>
```

**Note:** For large videos, consider hosting on YouTube/Vimeo instead.

## 3. Adding Downloadable Files

### Step 1: Place Files in Assets Folder
Put files in: `assets/files/`

### Step 2: Create Download Links

**Basic link:**
```markdown
[Download File Name]({{ "/assets/files/your-file.pdf" | relative_url }})
```

**With download attribute:**
```html
<a href="{{ '/assets/files/your-file.pdf' | relative_url }}" download>
  📄 Download File Name
</a>
```

### Supported File Types
- PDFs: `.pdf`
- Archives: `.zip`, `.rar`, `.tar.gz`
- Documents: `.doc`, `.docx`
- Spreadsheets: `.xls`, `.xlsx`
- Any other file type

## 4. Adding Descriptions

### In Front Matter
```yaml
---
description: "This description appears in RSS feeds and search results"
---
```

### In Post Content
You can add descriptions anywhere in your post using regular text or markdown:

```markdown
## Project Description

This project demonstrates [feature]. It includes:
- Feature 1
- Feature 2
- Feature 3
```

## Complete Example Post

```markdown
---
layout: post
title:  "My Awesome Project"
date:   2025-12-22 12:00:00 -0500
categories: projects web-development
description: "A showcase of my latest web development project"
---

## Overview

This project demonstrates advanced web development techniques.

![Project Screenshot]({{ "/assets/images/project-screenshot.jpg" | relative_url }})

## Demo Video

<iframe width="560" height="315" 
        src="https://www.youtube.com/embed/dQw4w9WgXcQ" 
        frameborder="0" 
        allowfullscreen>
</iframe>

## Resources

- [Download Source Code]({{ "/assets/files/project-code.zip" | relative_url }})
- [View Documentation]({{ "/assets/files/project-docs.pdf" | relative_url }})
```

## Asset Organization Tips

```
assets/
├── images/
│   ├── posts/
│   │   └── 2025-12-22-my-post/
│   │       ├── image1.jpg
│   │       └── image2.jpg
│   └── general/
│       └── logo.png
├── videos/
│   └── demos/
│       └── project-demo.mp4
└── files/
    └── downloads/
        └── project-files.zip
```

## Best Practices

1. **Optimize Images**: Compress images before uploading (use tools like TinyPNG)
2. **Use Descriptive Names**: Name files clearly (e.g., `project-screenshot.jpg` not `img123.jpg`)
3. **Alt Text**: Always include alt text for accessibility
4. **File Sizes**: Keep files reasonable in size for faster loading
5. **Video Hosting**: For large videos, use YouTube/Vimeo instead of local files
6. **Organize**: Keep assets organized in subdirectories

## Quick Reference

| Media Type | Location | Syntax |
|------------|----------|--------|
| Image | `assets/images/` | `![alt]({{ "/assets/images/file.jpg" \| relative_url }})` |
| Video (local) | `assets/videos/` | `<video src="{{ '/assets/videos/file.mp4' \| relative_url }}">` |
| Video (YouTube) | External | `<iframe src="https://www.youtube.com/embed/ID">` |
| File | `assets/files/` | `[Link]({{ "/assets/files/file.pdf" \| relative_url }})` |

