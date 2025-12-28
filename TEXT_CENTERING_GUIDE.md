# How to Center Text in Jekyll Posts

There are several ways to center text in your Jekyll posts and pages.

## Method 1: Using HTML with Inline Style (Quick & Simple)

```html
<p style="text-align: center;">This text is centered</p>
```

**Example:**
```html
<p style="text-align: center;">Welcome to my portfolio!</p>
```

## Method 2: Using HTML with CSS Class (Recommended)

I've added a `.center` class to your CSS. Use it like this:

```html
<p class="center">This text is centered</p>
```

**Example:**
```html
<div class="center">
  <h2>Project Title</h2>
  <p>Project description</p>
</div>
```

## Method 3: Center Headings

```html
<h2 style="text-align: center;">Centered Heading</h2>
```

Or with the class:
```html
<h2 class="center">Centered Heading</h2>
```

## Method 4: Center Multiple Elements

Wrap multiple elements in a div:

```html
<div style="text-align: center;">
  <h2>Title</h2>
  <p>Description</p>
  <p>More text</p>
</div>
```

Or with the class:
```html
<div class="center">
  <h2>Title</h2>
  <p>Description</p>
  <p>More text</p>
</div>
```

## Method 5: Center Lists

```html
<ul style="text-align: center; list-style-position: inside;">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

## Examples in Your Posts

### Center a Section Title
```markdown
## Electronics

<div class="center">
  <h3>Electrical Schematic</h3>
</div>
```

### Center a Paragraph
```markdown
<div class="center">
  This is important information that should be centered.
</div>
```

### Center an Image with Caption
```html
<figure class="center">
  <img src="{{ '/assets/images/example.png' | relative_url }}" alt="Example">
  <figcaption style="text-align: center;">Centered caption</figcaption>
</figure>
```

## Quick Reference

| What to Center | Code |
|----------------|------|
| Single paragraph | `<p class="center">Text</p>` |
| Heading | `<h2 class="center">Title</h2>` |
| Multiple elements | `<div class="center">...</div>` |
| Inline style | `<p style="text-align: center;">Text</p>` |

## Notes

- The `.center` class is now available in your CSS
- You can use either the class or inline styles
- Classes are reusable and cleaner
- Inline styles work immediately without CSS changes

