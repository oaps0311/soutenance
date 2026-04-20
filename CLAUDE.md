# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Single-page HTML slide presentation for a "soutenance" (oral thesis defense) by Oriane WOERTH about Hôtel Val-Vignes, a hotel in the Alsatian vineyard region. The entire application is one self-contained `index.html` file (~2050 lines) with no build tools, no dependencies, and no external frameworks.

## How to Run

Open `index.html` directly in a browser. No server or build step required.

## Architecture

Everything lives in `index.html`, structured as:

1. **CSS (lines ~10–1457):** Custom properties define an Alsatian vineyard color palette (`--bordeaux`, `--vert-vigne`, `--or`, `--creme`). Typography uses Google Fonts (Cormorant Garamond + Inter). Slide transitions use CSS transforms/opacity with cubic-bezier easing. Staggered entry animations via `.stagger` class.

2. **HTML (lines ~1458–1970):** 14 `<section class="slide">` elements inside a `.deck` container, each with `data-slide="N"`. Slide types include `.cover`, `.dramatic`, and `.merci` variants. Navigation bar with prev/next buttons and a progress bar at the bottom.

3. **JavaScript (lines ~1971–2046):** Vanilla JS slide engine. Navigation via arrow keys, Space, PageUp/PageDown, Home/End. Press `F` for fullscreen. Mobile swipe support. Click-to-advance (outside nav). Animation lock (`isAnimating`) prevents rapid switching.

## Key Conventions

- Language: all content and comments are in **French**
- No framework — pure HTML/CSS/JS; keep it that way
- Slides use the `.active` class for visibility; CSS handles all transition animations
- Decorative SVG elements (grape clusters, vine motifs) are inlined directly in the HTML
- Large base64-encoded images are embedded inline (this is why the file is ~2MB)
