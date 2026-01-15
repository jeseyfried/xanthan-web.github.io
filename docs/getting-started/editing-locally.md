---
layout: xanthan
title: Editing Locally
author: Fred Gibbs
date: 2019-10-03
---

# Editing Locally

GitHub lets you edit files in the browser, but it’s not designed to be a full editor. The easiest, most reliable way to work on your Xanthan-based site is to **edit the site on your computer**, then **publish changes** on GitHub.

The idea is that you make a copy of your GitHub repository on your computer, edit the files in a text editor, and then send them to GitHub to actually update the functioning website.

These instructions walk you through installing the needed tools, connecting to your repository, editing locally, and pushing changes.

---

## 1. Install the Tools

### **A. Install GitHub Desktop**

GitHub Desktop makes it easy and visual to keep your GitHub and local (meaning on your computer) repositories in sync.

1. Go to: [https://desktop.github.com](https://desktop.github.com)
2. Download and install the app.
3. Open GitHub Desktop and sign in with your GitHub account.

---

### **B. Install Visual Studio Code (VS Code)**

VS Code is your code editor.

1. Go to: [https://code.visualstudio.com](https://code.visualstudio.com)
2. Download and install it.
3. When prompted, allow VS Code to add itself to your system PATH (not required, but convenient).

---

## 2. Connect GitHub Desktop to Your Repository and Clone it

“Cloning” means making a local copy of your GitHub Pages project.

1. In GitHub Desktop, go to **File → Clone Repository…**
2. Find your site’s repository in the *GitHub.com* tab.
3. Select it and click **Clone**.
4. Choose where on your computer you want the files saved. The location doesn't matter, so choose what makes sense for your organization system.

You now have all your site files on your machine.

---

## 3. Open Your Site in VS Code

1. After cloning, GitHub Desktop shows your repository.
2. Click the button **Open in Visual Studio Code** (there’s a button right in GitHub Desktop).
3. VS Code will launch with your project folder already loaded.
4. Edit away!

You can now browse folders, edit content, add images, rename files and folders via VS Code, just like you do on your computer (and avoiding the clunky GitHub interface for these).

---


## 3.5. Prevention Checklist

Before committing changes:

- [ ] Check for matching quotes (`"..."` or `'...'`)
- [ ] Verify file paths match actual file locations exactly
- [ ] Ensure all include blocks have `{%raw%}{% ... %}{%endraw%}`
- [ ] Confirm YAML front matter is properly formatted
- [ ] Test locally if working on complex features (see [Working Locally](working-locally))

Most errors are caught by following this checklist!




## 4. Commit and Publish Your Changes

When you save a file, GitHub Desktop notices the changes automatically and helps you "push" the changes to your GitHub repository (and therefore bring it in sync with your local version).

1. Go back to **GitHub Desktop**.
2. In the left sidebar, you’ll see your changed files.
3. At the bottom-left:
   * Add a short **summary** of what you changed.
   * Optionally add a longer **description**.
4. Click **Commit to main** (or whatever your branch is called).
5. Click **Push origin** in the top-right of GitHub Desktop.
6. GitHub receives your changes, and GitHub Pages will rebuild your site automatically (usually takes ~40-60 seconds).

Your edits are now live!

If something doesn't work, head over to the [troubleshooting page](../content-design/troubleshooting)


---

## Advantages of Editing Locally 
(i.e. Why This Is Better Than Editing on GitHub)

### Proper editing tools
Github’s browser editor is very limited:

* No full Markdown preview
* No search/replace across files
* No built-in code help 

### Faster and safer
Working locally means you can:

* Save drafts without publishing
* Avoid breaking the live site accidentally


### Works without internet access
You can edit your entire site offline.
You only need internet when you *push* your changes.

### Vastly superior file management
Uploading images, moving folders, renaming files, or editing multiple files at once is dramatically easier with a real file manager like VS Code.
