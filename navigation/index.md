---
title: Navigation & Site Organization
layout: base
date: 2024-12-23
---

# Navigation & Site Organization

As your site grows beyond a few pages, you need clear ways to help visitors navigate your content. Xanthan provides multiple navigation patterns, each suited for different types of content and site structures.

This section covers the built-in navigation systems—from simple menu bars to dynamic card grids and interactive maps.

---

## Top Navigation Bar
The top navbar is the horizontal menu at the top of every page. It's your site's main navigation structure, visible on all pages.

**Key features:**
- Dropdown menus for organizing related pages
- Consistent across all pages
- Controlled by a simple YAML file (`_data/top-nav.yml`)
- No coding required—just edit text and links

**[Configure Your Top Nav →](top-nav)**

---

## Card-Based Navigation
Cards are visual navigation elements that automatically generate links to pages in a folder. Think of them as automatic directories that pull titles, authors, and summaries from your page metadata. There are several styles of cards that come with Xanthan, and of course you can create your own.

### Table of Contents Cards
Compact, text-focused cards in a grid layout
- Shows title, author, summary
- Automatic thumbnail images
- Perfect for essay collections

### Stacked Cards
Wide horizontal cards in a vertical stack
- Larger images and more prominent titles
- Good for featured content
- Emphasizes visual hierarchy

### Grid Cards
Traditional card grid layout
- Square or rectangular cards
- Balanced text and images
- Flexible columns (2, 3, or 4 across)

**When to use:** Student essay collections, project portfolios, team directories, any folder of similar pages you want to showcase.

**[Learn About Cards →](cards)**


---

## Left Sidebar Navigation
The left sidebar provides persistent navigation for all pages in a specific folder, visible while reading any page in that section.

**Key features:**
- Always visible while reading
- Automatically lists pages in a folder
- Organizes by categories using page metadata
- Shows current page location
- Ideal for course projects with multiple essays

**When to use:** Collaborative class projects, documentation sites, any collection where it's useful to have a ToC style of list links always on the screen so readers can easily jump between related pages.

**[See Left Nav Demo →](left-nav-demo)**

---

## Interactive Map
A map page automatically displays markers for any pages with geographic coordinates. Clicking a marker shows the page title and summary.

**[Explore the Map →](/map)**

**Key features:**
- Automatic marker generation from page metadata
- Custom popups with page info
- Click markers to navigate to pages
- Works with any geographic project

**How it works:** Add `geo: [latitude, longitude]` and `placename:` to any page's YAML header, and it automatically appears on the map.

---

**Mix and match!** You can use multiple navigation types together. For example, a class project might use:
- **Top nav** always visible on all site pages
- **Left sidebar** visible only on essay pages for quick navigation across essays
- **Cards** on a dedicated home or landing page
- **Map** page to show geographic distribution

