---
title: Directory
layout: xanthan
date: 2024-10-26
---

# Cards
Even a small website needs a way of organizing content and pages. Xanthan comes with a few ways to do this, and of course more can be added.


## Table of Contents
One familiar approach is to create a table of contents for your site pages, like you'd find in a book. Let's say you have a collection of pages, like student essays for a class project, for which you want to create a table of contents. We can do this automatically, as long as each page has a little metadata at the top of the file in the YML header. It looks like:

```
---
title: Seedling
author: Fred Gibbs
summary: Perfect for beginners getting comfortable with Markdown and digital essays. Basically section headings, a few images, and some pull quotes. Nothing fancy, but enough to make a visually compelling essay.
---
```

We can use this data to automatically generate links to the essays, like this: 


{% assign card_pages = site.pages | where_exp: "page", "page.path contains 'scrollstories/examples'" %}

{% include nav/card-toc.html rows = card_pages %}



It's not magic! We just need to tell Xanthan to create some links based on the metadata that's found on pages in a specified folder. In this case, it's Xanthan's `scrollstories` folder, but you'll create your own folder with a descriptive name. We use a little bit of "pseudo-code" to do this. It looks weird at first, but it makes sense once you get used to the syntax.

```
{%raw%}{% assign card_pages = site.pages | where_exp: "page", "page.path contains 'scrollstories/'" %}

{% include nav/card-toc.html rows = card_pages %}{%endraw%}
```

- First, we define a variable called `card_pages` (it could be called anything) that gathers all the metadata  from the files in the essays folder. That's what the `page.path contains 'scrollstories/'` part does. 
- Then we send that data to our include file (card-toc.html), which has the actual HTML code to generate the cards themselves. This way, we create very consistent code on our pages and if we want to change how it looks, we have to edit only one file.
- You can copy and paste this code on any page where you want to link to other pages. Just change `scrollstories` in the code to the folder where your pages are. Then you'll see the "card" links as above.


---

## Stacked cards
A little fancier than a ToC-style list, we can a generate of a stack of horizontal "cards" in the same way. In terms of gathering data to display, this works exactly like above. But it calls a different include file, which presents a stack of wide and short cards in a vertical display. 

```
{%raw%}{% assign stacked_cards = site.pages | where_exp: "page", "page.path contains 'scrollstories/'" %}

{% include nav/card-stack.html cards = stacked_cards %}{%endraw%}
```

{% assign stacked_cards = site.pages | where_exp: "page", "page.path contains 'scrollstories/'" %}
{% include nav/card-stack.html cards = stacked_cards %}


---

## Grid cards
You can see more cards at a glance if you use a grid layout with slightly smaller cards.

```
{%raw%}{% assign stories = site.pages | where_exp: "page", "page.path contains 'scrollstories/'" %}

{% include nav/card-grid.html cards = stories %}{%endraw%}
```

{% assign essays = site.pages | where_exp: "page", "page.path contains 'scrollstories/'" %}
{% include nav/card-grid.html cards = essays %}

You can easily customize how the cards appear depending on what kind of content you want to display in them. 

Happy fiddling!