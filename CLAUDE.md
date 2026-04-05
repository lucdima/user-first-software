# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the website for the **User First Software** manifesto (userfirstsoftware.org) — a static, multi-language HTML site with no build system, no JavaScript, and no dependencies. Licensed under GPL-3.0.

## Architecture

- **Static HTML only**: Each page is a standalone `index.html` with inline `<style>` (no external CSS or JS).
- **Translations**: Each language lives in its own directory (`/es/`, `/de/`, `/fr/`, `/ja/`, `/zh/`, `/ru/`) containing an `index.html`. The root `index.html` is the English version.
- **Language switcher**: Duplicated in both the header and footer of every page. When adding a new language, update the switcher in **all** existing pages.
- **Favicons / PWA**: Standard favicon set plus `site.webmanifest` in the root.

## Development

No build step. Open any `index.html` directly in a browser or serve with:

```
python3 -m http.server
```

## Adding a New Language

1. Create a new directory (e.g., `/pt/`) with an `index.html`.
2. Copy the structure from an existing translation, set the correct `<html lang="...">` attribute, and translate the content.
3. Keep the inline `<style>` block identical across all pages.
4. Add a link to the new language in the `.language-switcher` div of **every** existing `index.html` (both top and bottom switcher blocks).
