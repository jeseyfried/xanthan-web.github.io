---
layout: base
title: Template Sync Strategy
date: 2025-12-23
---

# Template Sync Strategy

This document explains how Xanthan's core files are automatically synced to template repositories, keeping all templates up-to-date without manual maintenance.

## Overview

Xanthan uses GitHub Actions to automatically sync core files to template repositories whenever changes are committed to the main branch. This ensures that:

- All templates inherit bug fixes and improvements to includes, layouts, and styles
- Templates stay in sync without manual file copying
- Template maintainers only need to update template-specific content (homepage, starter pages, navigation)

## What Gets Synced (Core)

The following directories and files sync automatically to all templates:

- `_includes/` — All reusable components (figure.html, carousel.html, etc.)
- `_layouts/` — All page templates (base.html, scrollstory.html, etc.)
- `assets/` — CSS, JavaScript, and shared images
- `Gemfile` — Ruby dependencies
- `.gitignore` — Git ignore rules

## What Stays Template-Specific

These items **do not sync** and remain unique to each template:

- `index.md` — Custom homepage
- `_data/top-nav.yml` — Template-specific navigation
- `_config.yml` — Template-specific configuration (baseurl, title, description)
- Starter/example pages (e.g., academic examples, scrollstory sample)
- `README.md` — Template-specific setup instructions

## How It Works

1. Developer commits changes to xanthan's `main` branch
2. GitHub Actions workflow triggers automatically
3. For each template:
   - Checks out latest xanthan code
   - Checks out the template repository
   - Syncs core files using `rsync` with `--delete` (removes files that no longer exist in xanthan)
   - Commits changes with message `"chore: sync core files from xanthan [skip ci]"`
   - Pushes to template repository

The `[skip ci]` tag prevents cascading workflow runs on template repos.

## Setup Requirements

### Personal Access Token (PAT)

The workflow requires a GitHub token with write access to all template repositories:

1. Generate a classic PAT at https://github.com/settings/tokens with `repo` scope
2. Add it as a secret named `SYNC_TOKEN` in the xanthan repository settings
3. Ensure this token has push access to all template repos

### Template Repository Access

Each template repository must grant the `amaranth-unm` organization (or relevant user) write access.

## Adding a New Template

To sync a new template:

1. Create the template repository (e.g., `academic-template`)
2. Manually populate template-specific files:
   - Custom `index.md`
   - Custom `_data/top-nav.yml`
   - Custom `_config.yml` (adjust baseurl to `/academic-template/`)
   - Any starter example pages
3. Add a new job to `.github/workflows/sync-templates.yml`:

```yaml
sync-academic-template:
  runs-on: ubuntu-latest
  steps:
    - name: Checkout xanthan main
      uses: actions/checkout@v4
      with:
        path: xanthan-source

    - name: Checkout academic-template
      uses: actions/checkout@v4
      with:
        repository: amaranth-unm/academic-template
        token: ${{ secrets.SYNC_TOKEN }}
        path: academic-template

    - name: Sync core files to academic-template
      run: |
        rsync -av --delete xanthan-source/_includes/ academic-template/_includes/
        rsync -av --delete xanthan-source/_layouts/ academic-template/_layouts/
        rsync -av --delete xanthan-source/assets/ academic-template/assets/
        cp xanthan-source/Gemfile academic-template/Gemfile
        cp xanthan-source/.gitignore academic-template/.gitignore
        echo "✓ Synced core files to academic-template"

    - name: Commit and push if changes exist
      run: |
        cd academic-template
        if [[ -n $(git status -s) ]]; then
          git add -A
          git commit -m "chore: sync core files from xanthan [skip ci]"
          git push
          echo "✓ Changes pushed to academic-template"
        else
          echo "✓ No changes to commit"
        fi
```

4. Push changes to xanthan's `main`
5. The workflow will automatically run and sync to the new template

## Customizing Sync per Template

If a template needs to exclude certain files (e.g., scrollstory excludes some guide pages):

Modify the `rsync` command in that template's job:

```yaml
# Example: exclude scrollstories from a minimal template
rsync -av --delete --exclude='scrollstories/' \
  xanthan-source/_includes/ minimal-template/_includes/
```

## Troubleshooting

### Sync fails with "repository not found"
- Check that `SYNC_TOKEN` has access to the template repository
- Verify the repository name in the job matches exactly

### Changes not appearing in template
- Check the workflow run in the Actions tab
- Ensure `SYNC_TOKEN` has write permissions
- Look for error messages in the workflow logs

### Unintended changes synced to template
- The `--delete` flag removes files in templates that no longer exist in xanthan
- If this is unwanted, remove `--delete` from the rsync command (but risks stale files)
- Alternatively, use inclusion lists instead of deletion

## Best Practices

1. **Keep core and template-specific clearly separated** — Don't add custom CSS to `assets/css/base.css`; create a template-specific `assets/css/custom.css` instead
2. **Document template-specific settings** — Note in template README what's different (baseurl, nav structure, etc.)
3. **Test core changes** — Before pushing to main, verify changes don't break all templates
4. **Monitor sync runs** — Check Actions tab occasionally to ensure syncs are working

