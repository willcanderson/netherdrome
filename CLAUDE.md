# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Netherdrome is a static podcast website hosted on GitHub Pages at `https://willcanderson.github.io/netherdrome/`. It consists of three hand-authored files with no build step, dependencies, or tooling.

## Files

- `index.html` — Main site page with header, platform links, and episodes list
- `style.css` — Dark-themed CSS using CSS custom properties (`--bg`, `--surface`, `--border`, `--text`, `--muted`, `--accent`)
- `feed.xml` — iTunes-compatible RSS 2.0 feed; new episodes are added as `<item>` elements inside `<channel>`

## Deployment

Pushing to `main` triggers the GitHub Actions workflow (`.github/workflows/deploy.yml`), which deploys the entire repo root to GitHub Pages.

## Adding Episodes

To add a new episode:
1. Add an `<item>` block inside `<channel>` in `feed.xml` with standard RSS + iTunes tags (`<title>`, `<description>`, `<enclosure>`, `<itunes:duration>`, `<pubDate>`, etc.)
2. Add a corresponding episode card in the `<section class="episodes">` in `index.html`, replacing or alongside the `.empty-state` paragraph
3. Update `<lastBuildDate>` in `feed.xml`
