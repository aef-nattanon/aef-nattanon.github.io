# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a static HTML personal portfolio website for Nattanon (aef-nattanon.github.io), hosted on GitHub Pages. It is written primarily in Thai and requires no build step — files are served directly.

## Development

Since this is a static site with no build tooling, open `index.html` directly in a browser or use any static file server:

```bash
# Python (no install needed)
python -m http.server 8080

# Node.js
npx serve .
```

There are no tests, linters, or package managers configured.

## Architecture

### Page Structure

- `index.html` — Main single-page portfolio with anchor-based sections: `#home`, `#about`, `#service`, `#experience`, `#education`, `#quotes`, `#contact`
- `projects/freelanc.html` — Subpage listing freelance projects; uses `../` relative paths for assets
- `react-spotify-clone/` — Pre-built React app dist (not source); served as a hosted demo at `/react-spotify-clone/`
- `web_model/` — TensorFlow.js model shards (`model.json` + 7 binary `.bin` files) for an in-browser ML model demo

### CSS/JS Stack

- **Bootstrap 3** (`css/bootstrap.min.css`, `js/bootstrap.min.js`) — grid and components
- **Font Awesome** (`css/font-awesome.min.css`, `fonts/`) — icons
- **animate.css** — entrance animations
- **WOW.js** (`js/wow.min.js`) — triggers animate.css on scroll; initialized with `new WOW({ mobile: false }).init()`
- **jQuery Parallax** (`js/jquery.parallax.js`) — parallax background effects per section
- **Smooth Scroll** (`js/smoothscroll.js`)
- **Custom styles** (`css/templatemo-style.css`) — all site-specific styles; contains responsive breakpoints at 580px, 767px, and 1024px
- **Custom JS** (`js/custom.js`) — preloader fadeout, dynamic age calculation (DOB: 1993/12/06), navbar scroll behavior, parallax init, smooth scroll init

### Background Images

Section backgrounds are defined in `css/templatemo-style.css` using `background: url('../images/...')`. The home section uses `images/home-img-2.png` (switched from `home-img.jpeg`, the old reference is commented out).

### Color Palette

| Variable | Hex |
|---|---|
| Orange (experience/service/contact bg) | `#E9724C` |
| Yellow (education bg, accent) | `#E3AE57` |
| Dark | `#161616` |
