---
layout: xanthan
title: Understanding Pages
author: Fred Gibbs
date: 2019-10-03
---

# Understanding Pages

## Anatomy of a Page
To understand the basics of how pages work, let's look at your homepage, the `index.md` file, directly on GitHub:

1. From your repository's home page on GitHub, find and click `index.md` in the file list.
2. Click the "Preview" tab (if available) to see how it renders, or click the pencil icon to view it in GitHub’s editor (we won’t change anything yet).
3. Scroll to notice the small box at the very top—this is the page label described below.

### The Page Label (YAML Header)
Every page starts with a small box that looks like this:

``` markdown
---
title: Getting Started
layout: xanthan
date: 2024-12-02
---
```

**Why this exists:** Think of it like a label on a folder. It tells GitHub Pages:
- What to call your page (`title`)
- How to style it (`layout`)
- When you created it (`date`)

Without this label, GitHub won't know your page is part of your website.

**Important:** Always keep the three hyphens `---` before and after your label, on their own lines.

The `base` layout is the standard page style used by most of your pages. Other layouts (like `scrollstory` or `left-nav`) change how the page looks.


### Writing Content with Markdown

**Why Markdown?** It's simpler than HTML. You can write plain text with a few simple symbols for formatting:
- `# Heading` becomes a big title
- `**bold**` becomes bold text
- `[link text](url)` becomes a clickable link

If you're new to Markdown, spend 5 minutes on this [Markdown tutorial](https://www.markdowntutorial.com/). If you forget syntax, check this [cheat sheet](https://www.markdownguide.org/cheat-sheet).

#### Want to Preview Before Publishing?
If you want to see what your page will look like as you write, use [Dillinger](https://dillinger.io/). Write there, preview instantly, then copy/paste your text into GitHub when you're done. Once you get comfortable with Markdown, you won't need to preview—you'll just write directly in GitHub.

---

To understand more about pages and editing, move on to the [Editing your site](editing-your-site.md) guide.
