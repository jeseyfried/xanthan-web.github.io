---
title: Troubleshooting
layout: base
date: 2024-12-02
---

# Troubleshooting

Having problems? This guide covers common issues and how to fix them.

---

## Site Not Updating

**Problem:** You made changes but your site isn't updating after 5+ minutes.

**Solution:** You likely have a syntax error preventing the site from building.

1. **Check GitHub Actions:**
   - Go to your repository on GitHub
   - Click the "Actions" tab at the top
   - Look for a red ✗ (failed build)
   - Click on it to see the error message

2. **Read the error message:**
   - It will usually tell you the file causing problems
   - It will show the line number where the error occurs
   - Look for syntax issues in that file around that line

---

## Images Not Showing

**Problem:** Your image code looks correct but the image doesn't appear.

**Common causes:**

### 1. File path doesn't match actual location

Check:
- Is the image actually in `/assets/images/`?
- Does your code point to the correct folder?
- Are you using the right path format?

```liquid
{%raw%}{% include figure.html
  image-path="/assets/images/photo.jpg"   ← Must match actual location
%}{%endraw%}
```

### 2. Filename doesn't match EXACTLY

File names are case-sensitive! Check:
- `photo.jpg` ≠ `Photo.jpg` ≠ `photo.JPG`
- Extensions: `.jpg`, `.JPG`, `.jpeg`, `.png` are all different
- Spaces in filenames can cause issues (avoid them!)

**Fix:** Make sure your code matches the filename EXACTLY, including capitalization and extension.

### 3. Relative vs. Absolute paths

- **Absolute path** starts with `/`: `/assets/images/photo.jpg` (works from any page)
- **Relative path** has no `/`: `images/photo.jpg` (relative to current page location)

**Recommendation:** Always use absolute paths starting with `/` to avoid confusion.

---

## Syntax Errors in Include Blocks

**Problem:** Your component code isn't working.

### Common mistakes:

#### 1. Missing or incorrect delimiters

❌ **Wrong:**
```liquid
{%raw%}{ include figure.html %}           ← Missing %
{& include figure.html %}          ← Wrong symbol
{% include figure.html }           ← Missing %{%endraw%}
```

✅ **Correct:**
```liquid
{%raw%}{% include figure.html %}{%endraw%}
```

#### 2. Mismatched quotes

❌ **Wrong:**
```liquid
{%raw%}{% include figure.html
  caption="This is broken'        ← Mismatch " and '
  width='50%"                     ← Mismatch ' and "
%}{%endraw%}
```

✅ **Correct:**
```liquid
{%raw%}{% include figure.html
  caption="This works correctly"
  width="50%"
%}{%endraw%}
```

#### 3. Missing closing tag

❌ **Wrong:**
```liquid
{%raw%}{% include figure.html
  image-path="/assets/images/photo.jpg"{%endraw%}
```

✅ **Correct:**
```liquid
{%raw%}{% include figure.html
  image-path="/assets/images/photo.jpg"
%}                                ← Don't forget closing %}{%endraw%}
```

---

## YAML Front Matter Errors

**Problem:** Page won't build due to front matter issues.

Every page needs front matter at the very top:

✅ **Correct:**
```yaml
---
title: My Page
layout: base
date: 2024-12-02
---

# Page content starts here
```

### Common mistakes:

❌ Must start on first line (no blank lines before `---`)
❌ Must have three dashes `---` not two `--`
❌ Must close with `---` on its own line
❌ Indentation matters in YAML (use spaces, not tabs)

---

## GitHub Pages Build Failed

**Problem:** GitHub Actions shows build failure.

### Check these common issues:

1. **Invalid YAML** - Check front matter syntax
2. **Liquid syntax errors** - Missing `%}` or wrong delimiters
3. **File encoding** - Make sure files are UTF-8 encoded
4. **Unsupported plugins** - GitHub Pages only supports certain Jekyll plugins

**How to debug:**
1. Click on the failed build in Actions tab
2. Expand the "Build with Jekyll" step
3. Read the error message carefully
4. Fix the file and line number mentioned

---

## Links Not Working

**Problem:** Links to other pages return 404 errors.

### Check:

1. **File extension in URL:**
   - Link to `/about` not `/about.md`
   - Jekyll converts `.md` to `.html` automatically

2. **Correct path:**
   ```markdown
   ❌ [Link](guides/getting-started.md)
   ✅ [Link](/guides/getting-started)
   ✅ [Link](guides/getting-started)
   ```

3. **Baseurl issues:**
   - If using a project site (not username.github.io), check `_config.yml`
   - Baseurl should be `/repository-name/`

---

## Styles Not Applying

**Problem:** CSS changes aren't showing up.

1. **Hard refresh your browser:**
   - Windows/Linux: `Ctrl + Shift + R`
   - Mac: `Cmd + Shift + R`

2. **Check file location:**
   - CSS files should be in `/assets/css/`
   - Linked correctly in `_includes/page-header.html`

3. **CSS syntax errors:**
   - Missing semicolons `;`
   - Unclosed brackets `}`
   - Invalid property names

---

## Still Stuck?

### Before asking for help:

1. **Check the error message** - It usually tells you exactly what's wrong
2. **Compare your code** to working examples on the component pages
3. **Look for typos** - Most issues are small syntax errors
4. **Try removing recent changes** - Did it work before? What changed?

### Getting help:

- **[Open an issue](https://github.com/yourusername/xanthan/issues)** on GitHub with:
  - Description of the problem
  - What you've tried
  - Error messages (if any)
  - Link to your repository (if public)

- **Check existing issues** - Someone might have already solved your problem

---

## Prevention Checklist

Before committing changes:

- [ ] Check for matching quotes (`"..."` or `'...'`)
- [ ] Verify file paths match actual file locations exactly
- [ ] Ensure all include blocks have `{%raw%}{% ... %}{%endraw%}`
- [ ] Confirm YAML front matter is properly formatted
- [ ] Test locally if working on complex features (see [Working Locally](working-locally))

Most errors are caught by following this checklist!
