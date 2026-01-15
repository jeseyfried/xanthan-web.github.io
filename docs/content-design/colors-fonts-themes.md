---
layout: xanthan
title: Customizing Your Site
---

# Basic Customization
This guide shows you how to customize Xanthan's appearance, from quick color changes to creating a complete custom theme. Choose the level that fits your needs.

## Quick Start: Changing Colors
The fastest way to personalize your site is to change colors in `assets/css/base.css`.

### Understanding Color Variables
The `:root` section defines color "variables" that your whole site uses. Change one variable, and every element using that color updates automatically:

```css
:root {
  /* Named colors - your palette */
  --sage: #6b8e7f;
  --warm-white: #f5f3f0;
  --golden-clay: #b8956a;

  /* Semantic variables - what colors are used for */
  --bg-page: var(--warm-white);
  --text-body: var(--sage-dark);
  --accent-primary: var(--sage);
}
```

### Two-Tier Color System

Xanthan uses a two-tier system for easy customization:

1. **Named colors** - Your actual color palette (e.g., `--sage: #6b8e7f`)
2. **Semantic variables** - What those colors are used for (e.g., `--bg-page: var(--sage)`)

To change colors:
- **Quick changes:** Just change what a semantic variable points to
- **Complete redesign:** Define new named colors, then update semantic variables

### Example: Quick Color Swap

Change the page background from warm white to light blue:

```css
:root {
  /* Add your new color */
  --light-blue: #e3f2fd;

  /* Update the semantic variable */
  --bg-page: var(--light-blue);  /* was var(--warm-white) */
}
```

### Example Palettes

#### Dark Theme
```css
--navy: #1a1a1a;
--cream: #e0e0e0;
--teal: #00ff88;

--bg-page: var(--navy);
--text-body: var(--cream);
--accent-primary: var(--teal);
```

#### High Contrast
```css
--pure-white: #ffffff;
--pure-black: #000000;
--bright-blue: #0055ff;

--bg-page: var(--pure-white);
--text-body: var(--pure-black);
--accent-primary: var(--bright-blue);
```

---

## Level 2: Typography Adjustments

Beyond colors, you might want to adjust fonts, sizes, or spacing.

### Changing Fonts

In `base.css`, update the font variables:

```css
:root {
  --font-heading: 'Your Heading Font', sans-serif;
  --font-body: 'Your Body Font', sans-serif;
  --font-mono: 'Your Code Font', monospace;
}
```

**Remember:** Add the font import at the top of `base.css`:

```css
@import url('https://fonts.googleapis.com/css2?family=Your+Font&display=swap');
```

### Adjusting Sizes

In `assets/css/typography.css`, adjust heading sizes:

```css
h1 {
  font-size: 2.5rem;  /* Larger headings */
}

p {
  font-size: 1.2rem;   /* Bigger body text */
  line-height: 1.8;    /* More line spacing */
}
```

### Changing Spacing

In `base.css`, adjust spacing variables:

```css
:root {
  --spacing-sm: 1.5rem;   /* More space */
  --spacing-md: 2rem;
  --spacing-lg: 3rem;
}
```

---

## Level 3: Creating a Theme File
If you just want to tweak a few colors or fonts, it's easiest to just edit the base CSS files (like base.css or typography.css). But you might want to develop a coherent look that is completely different and your own. At that point, it's best to create a new CSS file. This approach:

- Keeps all changes organized in one file
- Lets you switch themes easily by commenting/uncommenting one line
- Preserves the original base.css for reference
- Makes sharing or troubleshooting your design simple (just one file)


### How It Works
CSS files load in order, and later files override earlier ones:

1. `base.css` (defaults)
2. `typography.css`, `nav.css`, `cards.css` (component styles)
3. **Your theme file** (overrides)

Your theme file only needs what you're changing - everything else is inherited.

---

### Option A: Simple Theme (Colors & Fonts Only)

**Best for:** First-time theme creators who just want different colors/fonts

Xanthan includes `simple-theme.css` as a teaching example. It shows you how to:
- Define your color palette
- Map colors to semantic variables
- Optionally change fonts

**To use it:**

1. Copy `assets/css/simple-theme.css` to `my-theme.css`
2. Edit the color values in the `:root` section
3. Activate in `_includes/page-header.html`:
   ```html
   <link href="{{site.baseurl}}/assets/css/my-theme.css" rel="stylesheet">
   ```

**Example from simple-theme.css:**

```css
:root {
  /* Your color palette */
  --ocean-blue: #2c5f7c;
  --cloud-white: #f7f9fb;
  --pearl: #e8eef2;

  /* Map to semantic variables */
  --bg-page: var(--cloud-white);
  --accent-primary: var(--ocean-blue);
  --text-body: var(--charcoal);
}
```

The file includes detailed comments explaining each variable. Perfect for learning!

---

### Option B: Advanced Theme (Full Customization)

**Best for:** Experienced users who want to change visual styles beyond colors

For complete control, you can override individual element styles. Study `dark-energy.css` to see how. It demonstrates:
- Color variable overrides
- Typography customization (sizes, transforms, weights)
- Navigation styling (custom underlines)
- Component theming (cards, buttons, pullquotes)

**To use dark-energy.css:**

1. In `_includes/page-header.html`, uncomment:
   ```html
   <link href="{{site.baseurl}}/assets/css/dark-energy.css" rel="stylesheet">
   ```
2. Save and refresh

**To create your own advanced theme:**

Copy dark-energy.css as a starting point and modify the element overrides to match your design vision.

---

### Other Included Themes

**Terra Cotta** (`terra-cotta.css`) - The original Xanthan aesthetic with warm, earthy colors. A simple theme (variables only) showing the original design.

Activate any theme by uncommenting its link in `_includes/page-header.html`.

### Theme Best Practices

- **Override only what you need** - smaller files are easier to maintain
- **Use the two-tier color system** - named colors + semantic variables
- **Add comments** - explain your design decisions
- **Test thoroughly** - check all page types with your theme
- **Keep base.css untouched** - preserve it as a reference

---

## Color Selection Tools

- [Coolors](https://coolors.co/) - Generate color palettes
- [Adobe Color](https://color.adobe.com/) - Color wheel and palette tools
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) - Ensure text readability

---

## Tips for Success

**Contrast matters:** Ensure text is readable against backgrounds. Use contrast checkers.

**Test with real content:** View changes across different page types - home, blog posts, guides.

**Start small:** Begin with colors, then add typography, then visual effects.

**Use browser DevTools:** Inspect elements to see which CSS rules apply and experiment with changes before editing files.

**Hex codes:** Colors use 6-digit codes like `#6b8e7f`:
- Start with `#`
- First two digits: Red (00-FF)
- Middle two digits: Green (00-FF)
- Last two digits: Blue (00-FF)
- `#ffffff` = white, `#000000` = black

---

## Troubleshooting

**Colors didn't change:**
- Clear browser cache (Cmd+Shift+R on Mac, Ctrl+Shift+R on Windows)
- Check that you saved `base.css`
- Verify the variable name matches exactly

**Theme not showing:**
- Check the CSS file path in `page-header.html`
- Make sure the `<link>` tag is uncommented
- Confirm the file exists in `assets/css/`

**Some elements unchanged:**
- Your selector might need to be more specific
- Try adding `!important` to the property: `color: var(--teal) !important;`
- Check if another CSS file is overriding your changes

**Want to switch themes:**
- Comment out your current theme's `<link>` tag with `<!--` and `-->`
- Uncomment a different theme's `<link>` tag
- Save and refresh

---

## Next Steps

Once you're comfortable with appearance customization:

- See [Typography](typography) for design principles
- See [Using Images](images) for visual content strategies
- Explore advanced CSS in `nav.css`, `cards.css`, and `typography.css`
