---
layout: post
title:  "Your Post Title Here"
date:   YYYY-MM-DD HH:MM:SS -0500
categories: category1 category2
description: "Brief description of your post for RSS feeds and search results"
---

## Description

Write your post description and introduction here.

## Images

### Add Your First Image

1. Place your image in `assets/images/`
2. Reference it like this:

![Alt text describing your image]({{ "/assets/images/your-image.jpg" | relative_url }})

### Image with Caption

<figure>
  <img src="{{ '/assets/images/your-image.jpg' | relative_url }}" alt="Image description">
  <figcaption>Your caption here</figcaption>
</figure>

## Videos

### YouTube Video

Replace `VIDEO_ID` with your YouTube video ID:

<iframe width="560" height="315" 
        src="https://www.youtube.com/embed/VIDEO_ID" 
        frameborder="0" 
        allowfullscreen>
</iframe>

### Local Video File

Place video in `assets/videos/` and use:

<video width="100%" controls>
  <source src="{{ '/assets/videos/your-video.mp4' | relative_url }}" type="video/mp4">
  Your browser does not support the video tag.
</video>

## Files for Download

Place files in `assets/files/` and link to them:

[Download File Name]({{ "/assets/files/your-file.pdf" | relative_url }})

## Your Content

Add your main content here. You can use:
- **Bold text**
- *Italic text*
- [Links](https://example.com)
- Lists
- Code blocks
- And more!

