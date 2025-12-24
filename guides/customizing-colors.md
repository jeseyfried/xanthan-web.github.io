---
layout: base
title: Customizing Colors
permalink: /guides/customizing-colors/
---

# Customizing Colors

The easiest way to make your Xanthan site your own is to change the colors. No new files needed - just edit one section of the base stylesheet.

## Quick Start

1. Open `assets/css/base.css` in your editor
2. Find the `:root` section near the top (around line 14)
3. Change the color values
4. Save and refresh your browser

That's it! Your entire site updates instantly.

## Understanding the Colors

The `:root` section defines color "variables" that your whole site uses. Change one variable, and every element using that color updates.

```css
:root {
  --bg-primary: #F5EFE6;        /* Main page background */
  --text-primary: #3a1602;      /* Main text color */
  --text-secondary: #5a5a5a;    /* Lighter text (descriptions, small text) */
  --accent-color: #ea580c;      /* Links, buttons, highlights */
  --border-color: #e0d5c8;      /* Lines between sections */
  --shadow-color: rgba(0,0,0,0.1);  /* Subtle shadows */
}
```

## Common Customizations

### Dark Theme

```css
--bg-primary: #1a1a1a;
--text-primary: #e0e0e0;
--text-secondary: #a0a0a0;
--accent-color: #00ff88;
--border-color: #333;
--shadow-color: rgba(0,0,0,0.3);
```

### High Contrast

```css
--bg-primary: #ffffff;
--text-primary: #000000;
--text-secondary: #333333;
--accent-color: #0055ff;
--border-color: #000000;
```

### Warm Theme

```css
--bg-primary: #fef9f3;
--text-primary: #8b4513;
--text-secondary: #a0522d;
--accent-color: #d2691e;
--border-color: #daa520;
```

### Cool Blue Theme

```css
--bg-primary: #f0f4f8;
--text-primary: #1a3a52;
--text-secondary: #4a6fa5;
--accent-color: #0066cc;
--border-color: #c5d9f1;
```

## Color Tools

Need help picking colors? Try:
- [Coolors](https://coolors.co/) - Generate color palettes
- [Color Picker](https://htmlcolorcodes.com/) - Find hex codes
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) - Ensure text is readable

## Tips

**Keep contrast:** Dark text on light backgrounds (or vice versa) is easier to read.

**Test with real content:** Changes look different on different page types. Check your home page, blog posts, and navigation.

**Hex codes:** Colors are defined as 6-digit codes like `#ea580c`. 
- Start with `#` 
- Each pair of digits controls Red, Green, Blue
- `#ffffff` is white, `#000000` is black

**Live preview:** Many editors let you see changes as you type. If not, save your file and refresh the browser.

## Want More Control?

Once you're comfortable with colors, check out [Using Themes](/guides/using-themes/) to learn how to create a complete custom theme file with layout changes too.
