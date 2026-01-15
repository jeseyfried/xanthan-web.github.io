---
title: Configuring Your Top Navigation
layout: xanthan
---

# Configuring Your Top Navigation

The navigation bar at the top of every page is controlled by a single file: `_data/top-nav.yml`. This guide shows you how to customize it for your site.

---

## Finding the File

1. Go to your repository on GitHub
2. Click on the `_data/` folder
3. Click on `top-nav.yml`

---

## Understanding the Structure

The navigation file uses **YAML syntax**, which relies on indentation to show hierarchy. Here's what a basic dropdown menu looks like:

```yaml
- title: "Getting Started"
  items:
    - title: "Creating your site"
      url: "/getting-started/"
    - title: "Understanding Folders"
      url: "/getting-started/understanding-folders"
```

**What this creates:**
- A dropdown menu labeled "Getting Started"
- Two rows / links inside: "Creating your site" and "Understanding Folders"

---

## Two Types of Menu Items

### Dropdown Menus (with items)

Use this for grouping related pages together:

```yaml
- title: "Navigation"
  items:
    - title: "Overview"
      url: "/navigation/"
    - title: "Cards"
      url: "/navigation/cards"
    - title: "Left Navbar Demo"
      url: "/navigation/nav-left-demo"
```

**Key points:**
- The main `title` is what appears in the menu bar
- `items:` starts the list of links (note the colon!)
- Each item has a `title` (link text) and `url` (destination)
- **Indentation matters!** Each `- title` under `items` must be indented exactly **4 spaces**


### Direct Links (no dropdown)

Use this for standalone pages:

```yaml
- title: "FAQs"
  url: "/faqs"
```

**This creates:** A single link labeled "FAQs" that goes directly to `/faqs` (no dropdown menu)

---

## Adding Dividers

Visual separators inside dropdown menus help organize long lists:

```yaml
- title: "Content & Design"
  items:
    - title: "Typography"
      url: "/content-design/typography"
    - title: "Images"
      url: "/content-design/images"

    - divider: true

    - title: "Editing Locally"
      url: "/getting-started/editing-locally"
```

**What this creates:**
- "Working Locally" link
- A horizontal line (divider)
- "Typography" and "Images" links

**The blank lines** before and after `- divider: true` are optional but make the file easier to read.

---

## Common Tasks

### Adding a New Link to an Existing Menu

Let's add "Bibliography" to the "Getting Started" menu:

**Before:**
```yaml
- title: "Getting Started"
  items:
    - title: "Creating your site"
      url: "/getting-started/"
```

**After:**
```yaml
- title: "Getting Started"
  items:
    - title: "Creating your site"
      url: "/getting-started/"
    - title: "Bibliography"
      url: "/bibliography"
```

**Remember:** Match the indentation exactly (4 spaces for items under `items:`)


### Creating a New Dropdown Menu

Add this to your `top-nav.yml` file:

```yaml
- title: "Research"
  items:
    - title: "Projects"
      url: "/projects"
    - title: "Publications"
      url: "/publications"
    - title: "Datasets"
      url: "/datasets"
```

**Position matters:** The menu will appear in the order you list items in the file. If you want "Research" to appear third, make sure it's the third item.

### Adding a Direct Link (No Dropdown)

```yaml
- title: "About"
  url: "/about"
```

Simple! Just `title` and `url`, no `items:`.

### Removing a Menu Item

Just delete the entire section. To remove "ScrollStories":

**Delete this entire block:**
```yaml
- title: "ScrollStories"
  items:
    - title: "Overview"
      url: "/scrollstories"
    - title: "Seedling Essay"
      url: "/scrollstories/seedling"
    # ... and all other items
```

### Renaming a Menu

Just change the `title`:

**Before:**
```yaml
- title: "FAQs"
  url: "/faqs"
```

**After:**
```yaml
- title: "Help"
  url: "/faqs"
```

The link stays the same; only the display text changes.

---

## URL Guidelines

### Absolute URLs vs. Relative URLs

**For pages on your site (most common):**
```yaml
url: "/about"              # Correct - starts with /
url: "/guides/tutorial"    # Correct - starts with /
```

**For external websites:**
```yaml
url: "https://github.com/fredgibbs/xanthan"  # Full URL with https://
```

**Common mistakes:**
```yaml
url: "about"        # WRONG - missing the /
url: "about.md"     # WRONG - don't include .md
url: "about.html"   # WRONG - don't include .html
```

### Matching URLs to Files

If your file structure looks like this:
```
your-repo/
  about.md
  guides/
    tutorial.md
  projects/
    index.md
```

Your URLs should be:
```yaml
url: "/about"            # for about.md
url: "/guides/tutorial"  # for guides/tutorial.md
url: "/projects/"        # for projects/index.md
```

---

## YAML Syntax Rules

### Indentation is Critical

YAML uses spaces (not tabs) for indentation. Each level must be indented **exactly** the same amount.

**Correct:**
```yaml
- title: "Menu"
  items:
    - title: "Link"
      url: "/page"
```

**Wrong (inconsistent indentation):**
```yaml
- title: "Menu"
  items:
   - title: "Link"      # Only 3 spaces - will break!
      url: "/page"
```

### Quotation Marks

**Use quotes for titles and URLs:**
```yaml
title: "Getting Started"   # Correct
url: "/guides/tutorial"    # Correct
```

**Why?** Some special characters (like colons) can break YAML if not quoted. Quotes always work, so it's safer to use them consistently.

### Colons and Spacing

**After every colon, add a space:**
```yaml
title: "Menu"    # Correct - space after colon
items:           # Correct - space after colon
  - title:"Link" # WRONG - no space after colon
```

---

## Testing Your Changes

After editing `top-nav.yml`:

1. **Commit your changes** on GitHub
2. **Wait 1-2 minutes** for your site to rebuild
3. **Refresh your website** to see the updated navigation
4. **Check for errors** - if the navigation disappears, you likely have a syntax error

### Common Errors

**Navigation completely disappears:**
- Check indentation - every item under `items:` should be indented 4 spaces
- Make sure every `title:` and `url:` has a space after the colon
- Look for missing quotation marks

**Link doesn't work (404 error):**
- Check that the URL starts with `/`
- Verify the page file actually exists
- Make sure you didn't include `.md` or `.html` in the URL

**Menu looks weird:**
- Check that dropdown menus use `items:` with a colon
- Verify direct links use `url:` not `items:`
- Make sure you didn't mix tabs and spaces for indentation

---

## Example: A Complete Navigation File

Here's a simple, complete example you can adapt:

```yaml
- title: "About"
  url: "/about"

- title: "Research"
  items:
    - title: "Overview"
      url: "/research/"
    - title: "Current Projects"
      url: "/research/current"
    - title: "Publications"
      url: "/publications"

- title: "Teaching"
  items:
    - title: "Courses"
      url: "/teaching/courses"
    - title: "Advising"
      url: "/teaching/advising"

- title: "Contact"
  url: "/contact"
```

**This creates:**
- Direct link to "About"
- "Research" dropdown with 3 links
- "Teaching" dropdown with 2 links
- Direct link to "Contact"

---

## Advanced: Nested Folders

If your pages are organized in nested folders:

```
your-repo/
  research/
    current/
      project-1.md
      project-2.md
```

Your URL structure reflects this:
```yaml
- title: "Research"
  items:
    - title: "Project 1"
      url: "/research/current/project-1"
    - title: "Project 2"
      url: "/research/current/project-2"
```

**Remember:** The URL follows the folder path, minus the `.md` extension.

---

## Need Help?

**Navigation not working?**
1. Copy your entire `top-nav.yml` content
2. Paste it into a [YAML validator](https://www.yamllint.com/)
3. Fix any syntax errors it finds

**Still stuck?**
- Check the [Troubleshooting guide](../content-design/troubleshooting)
- Review the default `top-nav.yml` in the [Xanthan repository](https://github.com/xanthan-web/xanthan-web.github.io)
- Make sure your page files actually exist at the URLs you're linking to
