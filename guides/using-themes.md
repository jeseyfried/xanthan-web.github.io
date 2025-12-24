---
layout: base
title: Using Themes
permalink: /guides/using-themes/
---

# Using Themes

Xanthan makes it easy to customize your site's appearance. You can start simple by editing colors, then progress to creating complete theme variations.

## Three Ways to Customize

### 1. Quick Color Changes (Beginner)

The fastest way to customize your site is to edit the color variables in `assets/css/base.css`.

Find the `:root` section (around line 14) and change these values:

```css
:root {
  --bg-primary: #F5EFE6;        /* Page background */
  --text-primary: #3a1602;      /* Main text color */
  --text-secondary: #5a5a5a;    /* Secondary text */
  --accent-color: #ea580c;      /* Links, highlights */
  /* ... more colors ... */
}
```

**Changes take effect immediately when you save** - no new files needed.

**Best for:** Testing ideas, making small tweaks, learning how colors work together.

---

### 2. Creating a Theme (Intermediate)

When you have a cohesive set of changes you want to keep separate, create a theme file. A theme is a CSS file that overrides the base styles without modifying them.

#### How It Works

Xanthan loads CSS files in order:
1. `base.css` (all default styles and variables)
2. `typography.css`, `nav.css`, etc.
3. **Your theme file** (loaded last, so it overrides everything above)

Because CSS works in "cascade" order, later files override earlier ones.

#### Creating Your Theme

**Step 1:** Create a new file called `assets/css/my-theme.css`

**Step 2:** Add your custom variables:

```css
/* my-theme.css - My Custom Theme */

:root {
  /* Override only the colors you want to change */
  --bg-primary: #1a1a1a;
  --text-primary: #e0e0e0;
  --accent-color: #00ff88;
}
```

**Step 3:** Activate your theme in `_includes/page-header.html`:

Find the CSS link section and uncomment your theme:

```html
<!-- Your custom theme -->
<link href="{{site.baseurl}}/assets/css/my-theme.css" rel="stylesheet">
```

**Step 4:** Save and refresh - your theme is now active!

**Best for:** Creating distinct visual identities, experimenting without breaking base styles, sharing theme variations.

---

### 3. Deep Customization (Advanced)

For more than just color changes, you can override any CSS in your theme file:

```css
/* my-theme.css - Comprehensive customization */

:root {
  --bg-primary: #1a1a1a;
  --text-primary: #e0e0e0;
  --accent-color: #00ff88;
}

/* Override specific components */
h1 {
  font-size: 2.5rem;
  text-transform: uppercase;
  letter-spacing: 2px;
}

.navbar {
  background: linear-gradient(to right, #1a1a1a, #2a2a2a);
  border: none;
}
```

**Best for:** Complete redesigns, testing new layouts, teaching advanced CSS patterns.

---

## Example: The Dark Energy Theme

We've included `dark-energy.css` in the `/examples/themes/` folder as a reference. To use it:

1. Copy `examples/themes/dark-energy.css` to `assets/css/dark-energy.css`

2. In `_includes/page-header.html`, find this line:
   ```html
   <!-- <link href="{{site.baseurl}}/assets/css/dark-energy.css" rel="stylesheet"> -->
   ```

3. Uncomment it:
   ```html
   <link href="{{site.baseurl}}/assets/css/dark-energy.css" rel="stylesheet">
   ```

4. Save and refresh to see the dark theme in action

Then look at the CSS file to see how themes work - it's a good template for creating your own.

---

## Theme Best Practices

### Do:
- **Keep base.css untouched** - makes updates easier
- **Only override what you need** - smaller files, easier to maintain
- **Use variable overrides** - changes propagate throughout the site
- **Name themes clearly** - `dark-energy.css`, `high-contrast.css`, etc.
- **Document your choices** - add comments explaining the theme

### Don't:
- Copy entire selectors from base.css into your theme
- Create multiple conflicting theme files
- Mix theme changes with site content changes
- Leave unused theme files commented out (document them instead)

---

## When to Create a Theme

Create a theme file when:
- ✅ You have a complete set of coordinated changes
- ✅ You might want to switch back to the default
- ✅ You want to preserve the original styles
- ✅ You're teaching CSS (great learning tool!)
- ✅ You want to share your design with others

Use quick color changes instead when:
- ✅ You're just experimenting
- ✅ It's a one-off adjustment
- ✅ You want the change to be permanent
- ✅ You're learning how the site works

---

## Troubleshooting

**Your theme isn't showing up?**
- Check that the CSS file exists at the right path
- Make sure the `<link>` tag is uncommented in `page-header.html`
- Hard refresh your browser (Cmd+Shift+R on Mac)
- Check browser DevTools to confirm the file is loading

**Some styles still show the old way?**
- Your theme selector might be less specific - try adding `!important`
- Or create the rule in your theme file exactly as it is in base.css

**Want to switch themes?**
- Comment out your current theme `<link>` tag
- Uncomment a different one
- Or create a new theme and uncomment that instead

---

## Next Steps

- **Try it:** Create your own `my-theme.css` and experiment with colors
- **Share it:** Use themes to create site variations for different audiences
- **Learn more:** Read about [CSS Variables](/guides/css-variables/) and the [cascade](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)
