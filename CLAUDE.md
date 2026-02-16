# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-page portfolio website for **Thidar Maung Maung**, a hydrology/environmental science doctoral researcher at Université Gustave Eiffel. This is a birthday gift project — it should feel both professionally credible for academia and personally meaningful.

## Architecture

- **Single HTML file** (`thidar_portfolio.html`): Contains all HTML, CSS (in `<style>`), and JavaScript (in `<script>`) — no build tools, no framework, no bundler.
- **`Documents/` folder**: Contains `CV_ThidarMaungMaung.pdf` (the actual PDF CV).
- **`thidar_portfolio_plan.md`**: Roadmap of planned enhancements organized by priority phases.

## Development

Open `thidar_portfolio.html` directly in a browser — no server required. For live reload during development, use any static file server (e.g., `python -m http.server` or VS Code Live Server).

## Design System

CSS custom properties defined in `:root`:

- **Color palette**: River/water theme — `--river-deep` (#0B3D3F), `--river-teal` (#1A6B6D), `--moss` (#4A7C59), `--sandstone` (#D4A574), `--cream` (#FAF6F0)
- **Typography**: `Playfair Display` (headings), `Source Sans 3` (body), `JetBrains Mono` (labels/dates)
- **Animations**: Scroll-reveal via IntersectionObserver (`.reveal` / `.visible` classes), CSS keyframes for hero entrance, water particle canvas

## Key Sections & Patterns

- **Water canvas**: A `<canvas>` element with particle animation running via `requestAnimationFrame` — provides subtle background texture
- **Nav**: Fixed nav with scroll-based glassmorphism effect (`nav.scrolled`), mobile hamburger toggle hides `nav-links` at 768px
- **Timeline**: Education displayed as alternating left/right timeline with a gradient center line; collapses to single-column on mobile (1024px breakpoint)
- **Experience cards**: Dark background section (`--river-deep`) with hover-activated gradient top border
- **CV Download**: `downloadResume()` generates an HTML CV as a Blob and triggers download — the plan calls for replacing this with the real PDF in `Documents/`

## Planned Enhancements (from `thidar_portfolio_plan.md`)

Phase 1: PDF resume download, birthday easter egg, favicon/OG tags, copy polish
Phase 2: Interactive research map (D3.js/Three.js), data visualization, micro-interactions
Phase 3: Real photography, parallax storytelling, dark mode
Phase 4: Blog/updates section, multi-language (EN/FR), Google Scholar/ORCID, accessibility

## Conventions

- All CSS uses the custom property system — never use raw color hex values
- Responsive breakpoints: 1024px (tablet), 768px (mobile)
- Animation pattern: Add `.reveal` class to elements, IntersectionObserver adds `.visible` on scroll
- Staggered animations use `.reveal-delay-1` through `.reveal-delay-4`
