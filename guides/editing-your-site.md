---
layout: base
title: Editing your site
author: Fred Gibbs
date: 2019-10-03
---

# {{page.title}}

Here are the basic process for editing a page and adding a new page. All steps start from your repository home page in GitHub.

## Editing a page
Let's make a simple change to the homepage (your `index.md` file).
- Click on the `index.md` file.
- Click on the edit icon (looks like a pencil)
- Make some change to the text.
- Hit the green Commit button near the bottom of the page.
- Wait a few minutes and refresh your webpage.

## Add a new page
Of course you'll want to add your own pages. The GitHub website does not have an easy way to duplicate files. But we can do it manually.
- Click on a file that is a similar kind of page to what you want to create. 
- Click on the `Code` icon for that page.
- Copy the YML header to your clipboard, including the two sets of `---` on the top and bottom 
- Click the `Add file` button
- Type in the filename, including a `.md` extension
- Paste your YML header on your new page
- Hit the green Commit button near the bottom of the page

---

## Edit the navigation bar
Now we need to add the new page to the navigation bar. Xanthan makes it easy to edit your nav bar through a simple data file.
- Click on the `_data` folder
- Click on `top-nav.yml`
- Click on the edit icon (looks like a pencil)
- Even if the file syntax is unfamiliar, it is straightforward. If you follow the same pattern as existing links, you can easily add, rename, or remove what comes with the template.
- In this case, you can find an existing header to list your new page under, or make it a top-level nav link.
- Hit the green Commit button near the bottom of the page

---

## Moving files
Moving files within the GitHub interface is a bit annoying; the platform is really not designed for it. 
- Go into edit mode for the file you want to move
- Click on the filename at the top of the edit pane --- this is called the file PATH, and it tells GitHub where the file should be relative to your repository root folder.
- You can make this path into whatever you want; use `/` to create new folders.
- If you in the edit textbox and you want to edit something that appears before the textbox, just put the curson on the far left of the textbox and hit backspace or delete and you'll be able to edit it. 