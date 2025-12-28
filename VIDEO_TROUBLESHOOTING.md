# Video Troubleshooting Guide

## Common Reasons Videos Appear Blank

### 1. **File Path Issues**
- Check that the file exists in `assets/videos/`
- Verify the filename matches exactly (case-sensitive)
- Spaces in filenames can cause issues - consider renaming files to use hyphens or underscores

### 2. **File Format Issues**
- Ensure the video is in a supported format (MP4, WebM, OGG)
- MP4 with H.264 codec is most widely supported
- The file might be corrupted - try re-encoding

### 3. **File Size**
- Very large video files may not load properly
- Consider compressing the video or hosting on YouTube/Vimeo instead

### 4. **Browser Compatibility**
- Some browsers don't support certain video formats
- Try different browsers (Chrome, Firefox, Edge)
- Check browser console (F12) for errors

### 5. **Jekyll Server Issues**
- Restart Jekyll server: `bundle exec jekyll serve`
- Clear browser cache (Ctrl+F5)
- Check if the video file is being copied to `_site/assets/videos/`

## Solutions

### Solution 1: Fix Filename with Spaces
If your video filename has spaces, rename it:
```bash
# Rename file to use hyphens instead of spaces
"Sim vs Phys.mp4" → "Sim-vs-Phys.mp4"
```

Then update your post:
```html
<video width="100%" controls>
  <source src="{{ '/assets/videos/Sim-vs-Phys.mp4' | relative_url }}" type="video/mp4">
</video>
```

### Solution 2: Use YouTube/Vimeo (Recommended for Large Videos)
Instead of hosting locally, upload to YouTube and embed:

```html
<iframe width="100%" height="315" 
        src="https://www.youtube.com/embed/VIDEO_ID" 
        frameborder="0" 
        allowfullscreen>
</iframe>
```

### Solution 3: Add Multiple Video Formats
Provide fallback formats:

```html
<video width="100%" controls>
  <source src="{{ '/assets/videos/video.mp4' | relative_url }}" type="video/mp4">
  <source src="{{ '/assets/videos/video.webm' | relative_url }}" type="video/webm">
  Your browser does not support the video tag.
</video>
```

### Solution 4: Add Poster Image
Add a thumbnail that shows before video loads:

```html
<video width="100%" controls 
       poster="{{ '/assets/images/video-thumbnail.jpg' | relative_url }}">
  <source src="{{ '/assets/videos/video.mp4' | relative_url }}" type="video/mp4">
</video>
```

## Checking if Video File is Accessible

1. **Check file exists:**
   ```bash
   ls assets/videos/
   ```

2. **Check if file is copied to _site:**
   ```bash
   ls _site/assets/videos/
   ```

3. **Try accessing directly in browser:**
   ```
   http://localhost:4000/assets/videos/Sim vs Phys.mp4
   ```

4. **Check browser console (F12):**
   - Look for 404 errors
   - Check Network tab to see if file is loading

## Best Practices

1. **Rename files** to avoid spaces: `Sim-vs-Phys.mp4` instead of `Sim vs Phys.mp4`
2. **Use lowercase** filenames: `sim-vs-phys.mp4`
3. **Keep file sizes reasonable** (< 50MB for web)
4. **Consider hosting large videos** on YouTube/Vimeo
5. **Add poster images** for better user experience

## Quick Fix for Your Current Video

Your video file is: `Sim vs Phys.mp4`

**Option A: Rename the file (Recommended)**
1. Rename `Sim vs Phys.mp4` to `Sim-vs-Phys.mp4`
2. Update your post to use the new filename

**Option B: Keep current filename**
The current code should work, but try:
- Hard refresh browser (Ctrl+F5)
- Check browser console for errors
- Verify file is in `_site/assets/videos/` after Jekyll builds

