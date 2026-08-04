# Infantino's World Cup Tour: Animated Flight Map

An interactive animated map visualizing FIFA President Gianni Infantino's travel during the 2026 World Cup (June 11 – July 1, 2026), built from a single text-only ESPN article.

**Live demo:** [https://infanito-flight-map.netlify.app]

## What it shows

- 22 flight legs across North America
- 26,500+ miles traveled
- Animated plane following each route, with a running mileage counter
- Play/pause, restart, and speed controls (0.5x–4x)
- Real country outlines for the US, Canada, and Mexico with lat/lon grid lines

## Built with

- React 18 (via CDN, no build step)
- Tailwind CSS
- Babel Standalone (in-browser JSX compilation)
- Custom Mercator-like projection for North America

## How it was built

Built in 3 prompts with Claude, from a plain-text ESPN article to a working interactive visualization, in under 10 minutes. Flight data for the first week came directly from the article; later legs were cross-referenced against follow-up ESPN and Sporting Intelligence coverage.

## Run it locally

This is a single self-contained HTML file. No install, no build step.

1. Download `index.html`
2. Double-click to open it in any modern browser
3. Give it a few seconds on first load while Babel compiles the JSX in-browser

## Source

Data drawn from ["Where has Infantino been? FIFA president clocks up 39,000 miles on epic World Cup tour"](https://www.espn.com/soccer/story/_/id/49116383/infantino-fifa-presidents-epic-world-cup-tour), ESPN, July 2, 2026.

## About

Built by [Robert Lee](https://robertlee.io), product marketer exploring AI-native ways to turn raw information into fast, shareable visual stories.
