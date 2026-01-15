---
title: Map
layout: xanthan
date: 2025-01-01
---

# Interactive Maps

Xanthan includes a simple way to create interactive maps that automatically display pins for any pages that include geographic coordinates. This is perfect for projects involving places, travel narratives, historical sites, or any content with a spatial dimension.

## How It Works

The map component uses [Leaflet](https://leafletjs.com/), an open-source JavaScript library for interactive maps. It automatically scans all your pages for geographic coordinates and creates clickable markers with popup information.

## Adding Geographic Data to Pages

To make a page appear on the map, add these fields to the YML header at the top of your page:

```yaml
---
title: Seedling
geo: [37.88, -81.08]
placename: New River Gorge National Park
summary: Perfect for beginners getting comfortable with Markdown and digital essays.
header-image: images/seedling-card.png
---
```

### Required Fields
- **geo**: An array with latitude and longitude coordinates `[lat, lng]`

### Optional Fields
- **placename**: The name of the location (displayed in the popup)
- **summary**: A brief description (displayed in the popup)
- **header-image**: An image to display in the popup (path relative to the page)

## Creating a Map

To add a map to any page, use this include code:

```
{%raw%}{% include nav/map.html
  height="600px"
  width="100%"
  start_coords="[39.8283, -98.5795]"
  zoom=4
%}{%endraw%}
```

### Map Parameters

All parameters are optional and have sensible defaults:

- **id**: Unique identifier if you have multiple maps on one page (default: "map")
- **height**: CSS height value (default: "700px")
- **width**: CSS width value (default: "100%")
- **start_coords**: Initial map center as `[lat, lng]` (default: `[44.967, -103.767]`)
- **zoom**: Initial zoom level, 1-18 where higher = more zoomed in (default: 4)

## Example Map

Here's a smaller map showing the example scrollstories:

{% include nav/map.html
  id="demo-map"
  height="600px"
  width="100%"
  start_coords="[39.8283, -98.5795]"
  zoom=4
%}

## Finding Coordinates

To get coordinates for your locations:

1. Open [Google Maps](https://maps.google.com)
2. Right-click on the location
3. Click the coordinates at the top of the menu to copy them
4. The format will be `lat, lng` which you can use as `[lat, lng]` in your YML

## Tips

- Use a zoom level of 4-6 for country/regional views
- Use zoom level 10-14 for city views
- Use zoom level 15-18 for street-level views
- Keep your summary text brief—popups work best with 1-2 sentences
- Make sure your header-image path is relative to the page's directory
