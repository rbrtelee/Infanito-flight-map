# Infantino's World Cup Tour: Animated Flight Map

## Project Overview

Built an interactive animated map visualizing FIFA President Gianni Infantino's travels during the 2026 FIFA World Cup (June 11 – July 1, 2026). The visualization was created entirely from an ESPN news article published on July 2, 2026 that contained text-only information about his tour.

**Key Stats:**
- 22 flight legs
- 26,500+ miles traveled
- 3 prompts to Claude
- <10 minutes to completion
- Single standalone HTML file

---

## Source Material

**Article:** "Where has Infantino been? FIFA president clocks up 39,000 miles on epic World Cup tour"  
**Source:** ESPN Soccer  
**Published:** July 2, 2026  
**URL:** https://www.espn.com/soccer/story/_/id/49116383/infantino-fifa-presidents-epic-world-cup-tour

The article provided leg-by-leg flight data for the first week (June 11–18), which was then cross-referenced and extended through additional reporting to cover the full documented tour through July 1.

---

## Build Process

### Prompt 1: Initial Concept
Requested Claude to create an animated interactive map showing Infantino's flights across North America, with:
- Flight arcs between cities
- Animated plane traveling each route
- Running mileage counter
- Play/pause/restart controls
- Speed adjustment (0.5×, 1×, 2×, 4×)

### Prompt 2: Data Refinement & Atlanta Addition
Corrected missing Atlanta stop (England vs Congo DR match on July 1) and extended data through the USA vs Bosnia-Herzegovina game in San Francisco. Updated map projection to accommodate East Coast cities (Boston, Philadelphia).

### Prompt 3: Geography & Styling
Replaced stylized continent blob with actual country outlines for USA, Canada, and Mexico using simplified lat/lon coordinates. Added lat/lon grid lines for geographic context.

---

## Technical Implementation

### Architecture
- **Framework:** React 18 (via CDN)
- **Styling:** Tailwind CSS
- **Icons:** Lucide-react equivalents (hand-coded SVG)
- **Compilation:** Babel standalone (in-browser JSX compilation)
- **Map Projection:** Custom Mercator-like projection for North America
- **Animation:** requestAnimationFrame for smooth motion

### Key Components

**Flight Data:** 22 legs with from/to cities, miles, date, and match information

**City Coordinates:** 14 host cities with lat/lon positions

**Country Borders:** Simplified boundary data for USA, Canada, Mexico (~40 points each for visual clarity)

**SVG Rendering:**
- Bezier curve flight paths with quadratic bowing
- Animated plane icon following path with heading calculation
- City glow effects for visited locations
- Progressive stroke animation for active flight leg

**State Management:**
- Current leg tracking
- Animation progress (0–1 per leg)
- Play/pause state
- Playback speed multiplier
- Cumulative mileage calculation

### Animation Logic
- Each leg animates over ~2.5 seconds at 1× speed
- Plane position calculated along quadratic Bézier curve
- Completed flights shown as faded dashed lines
- Current flight shown with glowing stroke effect
- Automatic advance to next leg when progress reaches 1.0
- Loop disabled at end of tour

---

## Files Delivered

### infantino_flight_map.jsx
React component (JSX). Requires build tooling (Vite, webpack, etc.) to run. Used for development and reference.

### infantino_flight_map.html
Standalone single-file HTML artifact. Double-click to open in any modern browser. All dependencies (React, Tailwind, Babel) loaded from CDNs. No build step required. ~500 lines of embedded JSX.

---

## How to Use

### Local Playback
1. Download `infantino_flight_map.html`
2. Double-click to open in Edge, Chrome, Safari, or Firefox
3. Wait 3–5 seconds on first load (Babel compiling JSX)
4. Use Play/Pause, Restart, and Speed controls to navigate

### Share & Record
- **Loom:** Open in browser, record full screen, export video
- **Netlify Drop:** Drag HTML file to app.netlify.com/drop for instant hosting
- **LinkedIn:** Embed video with link to interactive map in caption

### Interactive Features
- **Play/Pause:** Start/stop animation
- **Restart:** Reset to leg 1
- **Speed:** 0.5×, 1×, 2×, 4× playback
- **Progress Bar:** Visual indicator of tour completion; click to jump

---

## Data Sources & Attribution

**Flight Legs 1–11 (June 11–18):** ESPN's leg-by-leg tour piece  
**Flight Legs 12–22 (June 20 – July 1):** Reconstructed from ESPN follow-up coverage, rg.org, and Sporting Intelligence reporting

**Note:** Some intermediate dates and sequences for legs 12–22 may vary slightly from original reporting due to cross-source reconciliation.

---

## Design Choices

### Visual Style
- **Dark theme** (slate-950 background): Reduces eye strain, emphasizes data
- **Amber accent** (#fbbf24): High contrast, professional
- **Country fills:** Graduated shades to distinguish boundaries
- **Grid lines:** Subtle lat/lon reference without overwhelming

### Geographic Representation
- Simplified country outlines (~40 coordinate points per country) balancing accuracy with file size and performance
- Custom projection optimized for North America
- Low-res intentional: stylized map, not survey-grade cartography

### UX Decisions
- **Auto-play on load:** Reduces friction; users can pause immediately
- **Visible progress bar:** Shows tour scope and completion
- **Speed controls:** Accommodates different preferences (Loom recording at 1.2×–2× typical)
- **No audio:** Silent-by-default respects mobile viewing habits

---

## LinkedIn Post Strategy

**Message:** Three prompts and less than 10 min with Claude to turn text-only ESPN article into interactive data visualization.

**Proof Point:** Demonstrates AI-native GTM capability — rapid ideation to polished artifact.

**Audience:** Product marketers, GTM operators, hiring managers at B2B SaaS/IoT companies.

**Delivery:** Video recording (Loom) embedded in LinkedIn post; link to interactive map in first comment for engagement.

---

## Lessons & Takeaways

1. **Data extraction from news:** Structured information (dates, cities, miles) in prose can be rapidly vectorized and visualized with minimal prompting.

2. **Iterative refinement:** Corrections (Atlanta stop) and scope extensions (East Coast cities) required only one additional prompt.

3. **Self-contained delivery:** Single HTML file with embedded dependencies eliminates deployment friction; CDN-based libraries ensure availability.

4. **Animation for narrative:** Animated path drawing + moving plane conveys *journey* better than static map; captures attention on social platforms.

5. **Credibility through specificity:** Real numbers (26,500 miles, 22 legs, 3 prompts, <10 min) outperform generic claims about AI speed.

---

## Future Enhancements (Not Implemented)

- 3D globe view option
- Filterable stops by match type or date range
- Embedded match highlights or stats
- Comparative analysis (Infantino vs other officials' travel patterns)
- Historical World Cup tour data for comparison
- Export to video or GIF format

---

## Archive

**Original ESPN Article URL:**  
https://www.espn.com/soccer/story/_/id/49116383/infantino-fifa-presidents-epic-world-cup-tour

**Project Timeline:**  
- Prompts & build: July 3, 2026 (morning)
- Video recording: July 3, 2026 (afternoon)
- LinkedIn post: July 4, 2026

**Creator:** Robert Lee  
**Contact:** robertlee.io
