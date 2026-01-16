---
layout: xanthan
title: Editing in GitHub
author: Fred Gibbs
date: 2019-10-03
---

# Editing in GitHub

This guide shows you how to edit your site entirely through GitHub's web interface (so no software to install). This approach is perfect for experimenting or class assignments where you're focused on a single page or two and a few images. For most student projects and straightforward edits, it works fine. You'll make changes, commit them, wait a minute or two, and see your updates live on your website.

**When you might want something else:** If you're building a site with lots of pages or are making frequent updates, check out the [Working Locally](editing-locally) guide. 


## Editing a Page
Let's make a simple change to your homepage:

1. Click on the `index.md` file
2. Click the pencil icon ("Edit this file")
3. Make a change to the text (e.g., change a word or add a sentence)
4. Scroll to the bottom and click the green "Commit changes" button
5. Wait 1–2 minutes, then refresh your website to see the change live

**Pro tip:** If something goes wrong, you can always come back and fix it. There's no "undo" button, but you can just edit the file again.


## Add a New Page

**Why copy a header?** Every page needs that label at the top. By copying from an existing page, you get the format right automatically.

1. Find a page similar to what you want to create
2. Click to open it, then click the pencil icon to edit
3. Select and copy the header (the `---` box at the very top, including the hyphens)
4. Click the back button to go back
5. Click "Add file" → "Create new file"
6. Type your filename with `.md` at the end (e.g., `my-new-page.md`)
7. Paste the header you copied at the very top
8. Add your content below the header
9. Click "Commit new file"

**Next step:** You'll need to add this new page to your navigation menu so visitors can find it. Keep reading below.

---

## Edit the Navigation Menu
The navigation file is where all menu links live. Instead of editing the code that makes the navbar, you just edit the data file and your changes appear everywhere.

1. Click the `_data` folder
2. Click `top-nav.yml` (this is your menu file)
3. Click the pencil icon to edit
4. Look at the existing links—they follow a pattern. Your new link should look similar.
   - Each link needs a `title:` (what people see in the menu) and a `url:` (where it links to)
   - Lines starting with spaces should be indented the same way as similar lines above/below
5. Add your new link by copying the pattern of existing ones
6. Click "Commit changes"

**Pattern to follow:**
```yaml
- title: "My New Page"
  url: "/my-new-page"
```

If you make a mistake, the menu might break. Check our [Troubleshooting](troubleshooting.md) guide if your menu looks weird.

## Moving Files into Folders

**When you might do this:** If you want to organize pages into folders (e.g., put all your portfolio pieces in a `portfolio/` folder).

GitHub's interface makes this a bit tricky, but here's how:

1. Go into edit mode for the file you want to move
2. At the top of the edit box, click on the filename line
3. The full path shows where the file lives. You can edit it to move the file.
   - Example: Change `my-page.md` to `portfolio/my-page.md` and GitHub will create the folder automatically
4. Commit the change

**Note:** This is optional and can wait until you're comfortable with the basics! 