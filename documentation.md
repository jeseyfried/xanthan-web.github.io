---
title: Documentation
layout: base
date: 2024-12-02
---

# Xanthan Documentation

Complete guide to building websites with Xanthan. Start with Getting Started, explore components by example, or jump to specific topics.

---

## Getting Started

New to Xanthan? Start here:

- **[Getting Started](guides/getting-started)** - Create your first site in 10 minutes
- **[Understanding Folders](guides/understanding-folders)** - How the site is organized
- **[Understanding Pages](guides/understanding-pages)** - How pages work and what goes in them
- **[Editing Your Site](guides/editing-your-site)** - Making changes and adding content

---

## Learn by Example

The best way to learn is by seeing components in action with copy-paste code.

### Page Components

Visual elements you can add to any page:

- **[Typography](components/typography)** - Headings, fonts, text styles, pullquotes
- **[Images](components/images)** - Figures, carousels, before/after sliders, jumbotrons
- **[Headers](components/headers)** - Page headers with background images
- **[Backgrounds with Scrolly Boxes](components/bg-scrollbox)** - Fixed background with scrolling text
- **[Background Switching](components/bg-switch)** - Change backgrounds as you scroll
- **[Side Scrolling Text](components/side-scroll)** - Horizontal scrolling narratives

### Navigation & Layout

Different ways to organize and navigate your site:

- **[Top Navigation](navigation/top-nav)** - Horizontal menu bar
- **[Card Layouts](navigation/cards)** - Grid and stack layouts for projects/portfolios
- **[Left Sidebar Nav](navigation/left-nav-demo)** - Vertical navigation menu
- **[Left Profile Demo](navigation/left-profile-demo)** - Sidebar with profile info

### Advanced Features

- **[ScrollStories Overview](scrollstories)** - Digital narrative essays
  - [Seedling](scrollstories/seedling) - Beginner level
  - [Sapling](scrollstories/sapling) - Intermediate
  - [Forest](scrollstories/forest) - Advanced
- **[Interactive Map](map)** - StoryMap-style geographic narratives

---

## Adding Content

- **[Adding Images](guides/adding-images)** - Upload and display images
- **Media** - Working with different media types (coming soon)
- **Code Samples** - Display syntax-highlighted code (coming soon)

---

## Customization

### Colors & Styles

All colors are controlled by CSS variables in `/assets/css/base.css`. Change the entire color scheme by editing these values:

```css
:root {
  --clay: #c05131;        /* Accent color */
  --sage: #8a9a7b;        /* Secondary color */
  --brown: #6b4423;       /* Heading color */
  --bone: #F5EFE6;        /* Background color */
  /* ... more variables ... */
}
```

See [Typography](components/typography) for font customization.

### Navigation

Edit `/_data/top-nav.yml` to customize your site navigation:

```yaml
- title: "About"
  url: "/about"

- title: "Projects"
  url: "/projects"
```

### Site Configuration

Edit `_config.yml` to set site-wide settings:

```yaml
baseurl: /your-repo-name/
title: Your Site Name
description: Your site description
author: Your Name
```

---

## Technology Overview

### What is Jekyll?

Jekyll is a **static site generator**. It takes your Markdown files and converts them to HTML using templates. Benefits:

- Fast, secure websites (no databases)
- Free hosting on GitHub Pages
- Version control with Git
- Simple content editing

### What is Markdown?

Markdown is a simple writing format that converts to HTML:

```markdown
# This becomes a heading
**This is bold**
[This is a link](url)
```

See [Understanding Pages](guides/understanding-pages) for more.

### What are Includes?

Includes are reusable HTML snippets. Instead of copying code, you reference the include:

```liquid
{% include figure.html
  width="50%"
  image-path="/assets/images/photo.jpg"
%}
```

This keeps your code clean and consistent across pages.

---

## Working Locally

For advanced development, you can run Xanthan on your computer:

- **[Working Locally Guide](guides/working-locally)** - Complete setup instructions
- Test changes before publishing
- Faster iteration
- Use advanced editors and tools

---

## Troubleshooting

Having issues? Common problems and solutions:

- **[Troubleshooting Guide](guides/troubleshooting)** - Fixes for common issues
- Images not showing
- Site not building
- Layout problems
- GitHub Pages errors

---

## File Structure Reference

```
xanthan/
├── _includes/          # Reusable components (figure.html, carousel.html, etc.)
├── _layouts/           # Page templates (base.html, minimal.html, etc.)
├── _data/              # Site configuration
│   ├── top-nav.yml    # Navigation menu items
│   └── sidebar.yml    # Sidebar navigation
├── assets/
│   ├── css/           # Stylesheets
│   │   ├── base.css   # Colors, variables, core styles
│   │   ├── typography.css
│   │   ├── nav.css
│   │   └── ...
│   ├── images/        # Your images go here
│   └── js/            # JavaScript files
├── guides/            # Getting started documentation
├── components/        # Component examples and documentation
├── _config.yml        # Jekyll configuration
├── index.md           # Homepage
└── [your-pages].md    # Your content pages
```

---

## Additional Resources

- **[FAQ](faqs)** - Frequently asked questions
- **[GitHub Repository](https://github.com/yourusername/xanthan)** - Source code
- **[Jekyll Documentation](https://jekyllrb.com/)** - Official Jekyll docs
- **[Markdown Guide](https://www.markdownguide.org/)** - Learn Markdown syntax

---

## Philosophy

Xanthan is built on principles of **sustainable digital scholarship**:

### Own Your Content
Everything lives in a Git repository you control. Export, migrate, or archive anytime. No platform can take your content away.

### Learn by Doing
We don't hide complexity—we explain it. You'll learn fundamental web technologies while building something meaningful.

### Design Matters
Present your work in visually compelling ways. Good design isn't decoration; it's communication.

### Built to Last
Standard web technologies (HTML, CSS, Markdown) will work for decades. Your site won't break when a company changes its platform.

### Open by Default
All code is open source. Learn from it, modify it, share improvements. Knowledge should be accessible.

---

## Contributing

Found a typo? Want to add a component? Contributions welcome!

- Report bugs via [GitHub Issues](https://github.com/yourusername/xanthan/issues)
- Suggest features via [GitHub Discussions](https://github.com/yourusername/xanthan/discussions)
- Submit improvements via pull requests

---

## Next Steps

- **New to Xanthan?** → Start with [Getting Started](guides/getting-started)
- **Want to see examples?** → Browse [Components](components/images)
- **Ready to customize?** → Edit colors and navigation (see above)
- **Need help?** → Check [Troubleshooting](guides/troubleshooting)

Questions? Open an issue or discussion on GitHub. We're here to help!
