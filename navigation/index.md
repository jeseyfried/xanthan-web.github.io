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

**Best for: Main site navigation, primary sections**

The top navbar is the horizontal menu at the top of every page. It's your site's main navigation structure, visible on all pages.

**[Configure Your Top Nav →](top-nav)**

**Key features:**
- Dropdown menus for organizing related pages
- Consistent across all pages
- Controlled by a simple YAML file (`_data/top-nav.yml`)
- No coding required—just edit text and links

**When to use:** Primary site sections, main categories, important pages that should always be accessible.

---

## Card-Based Navigation

**Best for: Collections of similar content (essays, projects, team members)**

Cards are visual navigation elements that automatically generate links to pages in a folder. Think of them as automatic directories that pull titles, authors, and summaries from your page metadata.

**[Learn About Cards →](cards)**

**Available card styles:**

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

---

## Left Sidebar Navigation

**Best for: Long-form content sites, documentation, multi-page projects**

The left sidebar provides persistent navigation for all pages in a specific folder, visible while reading any page in that section.

**[See Left Nav Demo →](left-nav-demo)**

**Key features:**
- Always visible while reading
- Automatically lists pages in a folder
- Organizes by categories using page metadata
- Shows current page location
- Ideal for course projects with multiple essays

**When to use:** Collaborative class projects, documentation sites, any collection where readers need to easily jump between related pages.

---

## Interactive Map

**Best for: Place-based projects, geographic narratives, field studies**

An interactive Leaflet map that automatically displays markers for any pages with geographic coordinates. Clicking a marker shows the page title and summary.

**[Explore the Map →](/map)**

**Key features:**
- Automatic marker generation from page metadata
- Custom popups with page info
- Click markers to navigate to pages
- Works with any geographic project

**When to use:** Digital history projects, field research, travel narratives, any content tied to specific locations.

**How it works:** Add `geo: [latitude, longitude]` and `placename:` to any page's YAML header, and it automatically appears on the map.

---

## Choosing the Right Navigation

Different content needs different navigation. Here's a quick decision guide:

| Content Type | Recommended Navigation |
|-------------|------------------------|
| Main site structure | Top Nav Bar |
| Essay/project collections | Cards |
| Multi-page course projects | Left Sidebar + Cards |
| Place-based research | Map + Cards |
| Documentation/guides | Left Sidebar |
| Featured content | Stacked Cards |

**Mix and match:** You can use multiple navigation types together. For example, a class project might use:
- **Top nav** for main sections
- **Left sidebar** for essay navigation
- **Cards** on a landing page
- **Map** to show geographic distribution

---

## Getting Started

1. **Start with the top nav** - Configure your main menu structure
2. **Add cards** when you have a collection of similar pages
3. **Consider a sidebar** if readers need to navigate between many related pages
4. **Add a map** if your content has geographic coordinates

Each navigation page includes detailed setup instructions and copy-paste code examples.
