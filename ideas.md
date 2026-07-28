# Global Flashpoints 2026 — Design Philosophy

## Design Direction: Command-Center Analytical Glassmorphism

### Design Movement
**Cyberpunk Intelligence Dashboard** — A sophisticated blend of real-time monitoring interfaces (think mission control, financial trading floors, threat-assessment centers) with contemporary glassmorphism and analytical precision. The aesthetic is *powerful and authoritative* without being cold; it conveys urgency and clarity.

### Core Principles
1. **Clarity Through Hierarchy**: Information architecture is ruthlessly prioritized—headlines, KPIs, and cause-effect flows dominate; deep dives are hidden until requested.
2. **Motion as Information**: Scroll-reveal animations, hover lifts, and chart transitions communicate state changes and guide attention without distraction.
3. **Glassmorphic Depth**: Frosted glass cards with subtle borders and soft shadows create visual layers; the dark navy background recedes, letting content float forward.
4. **Modular Consistency**: All four modules follow an identical skeleton (headline → cause-effect → KPIs → chart → stakeholders → deep dive), making the dashboard scannable and predictable.

### Color Philosophy
**Dark Navy Foundation (#0B1120)** as the command-center void, with **module-specific accent colors** that signal distinct topics:
- **Module 1 (NEET)**: Saffron/Amber (#F59E0B) — institutional authority, Indian governance
- **Module 2 (Russia-Ukraine)**: Ice Blue/Steel (#38BDF8) — geopolitical tension, frozen conflict
- **Module 3 (Trump Tariffs)**: Emerald Green (#10B981) — trade, commerce, economic policy
- **Module 4 (SaaSpocalypse)**: Violet/Purple (#A78BFA) — technology disruption, AI emergence

Accents appear in:
- Module headline badges ("Ongoing", "Escalating", "De-escalating")
- KPI card borders and glow on hover
- Chart colors (primary line/bar in accent, supporting data in muted grays)
- Cause-effect flow node highlights

### Layout Paradigm
**Vertical scroll-stack with sticky nav** — each module occupies a full viewport height (or slightly more), creating natural pause points. No centered grid; instead, modules use **asymmetric layouts**:
- Headline + status badge (left-aligned, bold)
- Cause-effect flow diagram (horizontal timeline or node-flow, spanning full width)
- KPI cards (4-column grid on desktop, 2×2 on tablet, stacked on mobile)
- Chart (full-width, right-aligned legend)
- Stakeholders (tag cloud or grid)
- Deep-dive accordion (expandable, full-width)

Hero section: **Rotating global-tension radial gauge** (0–100 "global friction score") animates on page load, setting the tone.

### Signature Elements
1. **Glassmorphic Cards**: Frosted background (`backdrop-blur-xl`), semi-transparent white border, soft shadow. On hover, the border glows with the module's accent color, and the card lifts slightly (transform: translateY).
2. **Cause-Effect Flow Diagram**: Horizontal timeline with nodes (Root Cause → Trigger → Immediate Impact → Long-term Consequence). Nodes are connected by animated lines; on hover, a node expands to show detail.
3. **Animated Radial Gauge**: The hero section's "global friction score" is a Recharts RadialBarChart that animates from 0 to its current value on load, creating a sense of real-time monitoring.

### Interaction Philosophy
- **Scroll-reveal**: Modules fade in + slide up as they enter the viewport (Framer Motion or CSS transitions).
- **Hover states**: Cards lift, borders glow, charts highlight on hover.
- **Sticky nav**: Jumps to each module; active section is highlighted with a bottom border in the module's accent color.
- **Expandable deep dives**: Smooth height animation (max-height transition) when toggled.
- **Dark/light mode toggle**: Persists across the session (React state, not localStorage per requirements).

### Animation Guidelines
- **Entrance animations** (scroll-reveal): 400–600ms ease-out, staggered by 50–80ms per element.
- **Hover interactions** (card lift, glow): 200ms ease-out.
- **Chart transitions** (data updates, tooltip): 300ms ease-in-out.
- **Accordion expand/collapse**: 250ms ease-in-out.
- **Radial gauge animation** (hero load): 1500ms ease-out.
- **Respect `prefers-reduced-motion`**: Gate all non-essential motion behind media query.

### Typography System
- **Headlines**: Bold serif or geometric sans (e.g., Playfair Display or Sora Bold) at 2.5–3.5rem for module titles, 1.5–2rem for section headers.
- **Body**: Clean sans (e.g., Inter or Sora Regular) at 0.95–1rem for descriptions and KPI labels.
- **Data**: Monospace (e.g., IBM Plex Mono) for numbers and chart labels, conveying precision.
- **Hierarchy**: Bold for KPI values, regular for labels; use color (accent or muted) to guide secondary information.

### Brand Essence
**"Real-time cause-and-effect intelligence for a fragmented 2026."** — A neutral, analytical platform for understanding interconnected global crises. Not alarmist, not dismissive; factual and empowering.

**Personality adjectives**: Authoritative, Precise, Urgent.

### Brand Voice
- **Headlines**: Direct, active, data-driven. Examples: "NEET-UG 2026: Trust Collapse in India's Testing System" / "Russia-Ukraine: Negotiations Stall as Strikes Resume"
- **CTAs & Microcopy**: Minimal, functional. "Expand deep dive", "View stakeholders", "Toggle dark mode".
- **Avoid**: Generic filler ("Welcome to our dashboard"), clickbait, editorializing.

### Wordmark & Logo
A bold, geometric symbol: a **compass rose with a cracked center**, suggesting fractured global stability. The compass points (N, S, E, W) are rendered in the four module accent colors (Saffron, Ice Blue, Emerald, Violet), and the center crack is a thin line. No text, just the symbol. Used in the sticky nav header and as the favicon.

### Signature Brand Color
**Deep Navy (#0B1120)** — the command-center void. It's the foundation; the four module accents are the *punctuation*.

---

## Design Decisions (Applied)
- **Font Pairing**: Playfair Display (Bold, headlines) + Inter (Regular, body) + IBM Plex Mono (Data).
- **Spacing Rhythm**: 8px base unit (8, 16, 24, 32, 48, 64px).
- **Shadow System**: Soft, layered shadows (`0 4px 12px rgba(0,0,0,0.15)` for cards, `0 8px 24px rgba(0,0,0,0.25)` for lifted hover).
- **Border Radius**: 12px for cards, 8px for buttons, 4px for inputs.
- **Glassmorphism Blur**: `backdrop-blur-xl` (12px) for cards, `backdrop-blur-md` (8px) for nav.
- **Dark Mode**: Default to dark theme; light mode toggle available.
- **Mobile Responsiveness**: Stack all multi-column layouts vertically on screens < 768px.
