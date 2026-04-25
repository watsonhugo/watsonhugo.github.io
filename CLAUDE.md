# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A personal blog ("華生的珈琲館") built with Hugo and the hugo-book theme. Content is in Traditional Chinese (zh-TW), covering history, geography, and typography. Deployed to GitHub Pages at https://watsonhugo.github.io/.

## Commands

- **Dev server:** `hugo server -D` (includes drafts)
- **Build:** `hugo` (output goes to `public/`)
- **New post:** `hugo new posts/YYYY-MM-DD-slug.md` (creates draft from archetype)
- **Install theme:** `git submodule update --init --recursive` (hugo-book is a git submodule)

Hugo must be installed separately (`brew install hugo`).

## Architecture

- **hugo.toml** — All site configuration: metadata, menu structure, theme params, markup settings
- **themes/hugo-book** — Git submodule, do not edit directly
- **content/posts/** — Blog posts in Markdown with TOML/YAML front matter (`title`, `date`, `tags`, `cover`, `summary`)
- **content/about/**, **content/archives/** — Static pages using `single` and `archives` layouts
- **static/images/** — Site assets (e.g., avatar.gif)
- **layouts/**, **assets/**, **data/**, **i18n/** — Override directories (used to customize hugo-book without modifying the submodule)

## Content Conventions

- Post filenames follow `YYYY-MM-DD-slug.md` pattern
- Front matter uses YAML delimiters (`---`), includes: `title`, `date`, `lastmod`, `tags`, `cover.image`, `cover.alt`, `summary`
- Goldmark renderer is set to `unsafe = true` (raw HTML allowed in Markdown)
- `<!--more-->` marks the summary/content split point
