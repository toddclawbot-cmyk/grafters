# SPEC.md — Grafters

## Concept & Vision

**Grafters** is a fictional heritage menswear brand built on one truth: no two bodies are the same, and off-the-rack never fits right. We specialize in "grafting" — taking the best parts of two garments to create one that fits *your* life. Tall and lanky? Bulky and strong? That's not a problem — that's a *combination*.

The brand voice is warm, a little self-deprecating, and deeply genuine — like an older brother who actually learned to sew. The aesthetic channels heritage Americana workwear meets modern tapered fit — think Pointerman, J.Crew, Todd Snyder. Real clothes for real bodies that come in all shapes.

## Design Language

### Aesthetic Direction
Heritage menswear catalog — warm, editorial, trustworthy. Think J.Crew fall lookbook meets vintage workwear advertisements. Elevated but approachable.

### Color Palette
- **Primary:** `#1B2A38` (deep navy charcoal — the color of well-worn denim)
- **Secondary:** `#C8A96E` (warm wheat gold — like golden thread)
- **Accent:** `#8B3A3A` (muted burgundy — a pop of personality)
- **Background:** `#F7F4EF` (warm cream — aged paper)
- **Text:** `#1A1A1A` (near-black)
- **Text Muted:** `#6B6560` (warm gray)
- **Surface:** `#FFFFFF` (white cards)

### Typography
- **Headings:** `DM Serif Display` — elegant, editorial, trustworthy
- **Body/UI:** `Instrument Sans` — modern, clean, readable
- **Accent/Labels:** `Space Mono` — subtle vintage technical feel

### Spatial System
- Base unit: 8px
- Section padding: 80px vertical, responsive down to 48px
- Card padding: 24px
- Grid: 12-column, max-width 1280px

### Motion Philosophy
- Page load: staggered fade-up (opacity 0→1, translateY 20px→0, 500ms ease-out, 80ms stagger)
- Hover on cards: subtle lift (translateY -4px, shadow expand, 200ms ease)
- Buttons: scale 0.98 on press, 100ms
- Smooth scrolling throughout

### Visual Assets
- Icons: Phosphor Icons (regular weight)
- Photography: Unsplash editorial menswear imagery
- Logo: Custom SVG wordmark — "Grafters" in DM Serif Display with a stylized needle-and-thread icon
- Decorative: Subtle stitch-pattern dividers (dashed lines)

## Layout & Structure

### Pages
1. **Home** — Hero with editorial photo, brand story, how-it-works (grafting process), featured bundles, testimonials, newsletter
2. **Shop** — Product grid with category filters (shirts, pants, bundles), sort options
3. **How It Works** — Illustrated 3-step process: Measure → Match → Graft
4. **Our Story** — The founding story (fictional), the philosophy, the tailors
5. **Cart** — Slide-out drawer
6. **Checkout** — Multi-step: info → shipping → payment (mock)

### Responsive Strategy
- Desktop: Full multi-column layouts
- Tablet: 2-column grids, stacked sections
- Mobile: Single column, hamburger nav, bottom-fixed cart button

## Features & Interactions

### Navigation
- Fixed top nav with logo, main links, cart icon with item count badge
- Mobile: hamburger → full-screen overlay menu

### Product Cards
- Image (Unsplash menswear), name, "graft type" tag (e.g., "Tall + Athletic"), price
- Hover: image subtle zoom, card lifts
- Quick "Add to Cart" on hover

### Cart Drawer
- Slide in from right
- Line items with quantity +/-, remove button
- Subtotal, "Proceed to Checkout" button
- Empty state: illustration + CTA to shop

### How It Works Section (Home)
- 3 illustrated steps with icons
- Animated on scroll into view

### Testimonials
- Rotating carousel with 3-4 testimonials from fictional customers
- Each with name, body type description, quote

### Newsletter
- Email input + subscribe button
- Success state: "You're in the graft."

## Component Inventory

### NavBar
- States: default (transparent over hero), scrolled (white bg + shadow)
- Logo left, links center, cart icon right
- Cart icon shows badge count when items present

### ProductCard
- States: default, hover (lift + shadow), loading (skeleton)
- Graft type badge: pill-shaped label

### Button
- Variants: primary (navy fill), secondary (outline), ghost
- States: default, hover, active (scale), disabled

### CartDrawer
- States: open, closed
- Empty state with SVG illustration

### TestimonialCard
- Quote, attribution with body type description

### Input
- States: default, focus (gold border), error (burgundy border + message)

## Technical Approach

- **Frontend:** React + Vite, deployed to GitHub Pages
- **Styling:** Plain CSS with CSS variables (no Tailwind)
- **State:** React useState/useContext for cart
- **Routing:** React Router v6
- **Mock backend:** All cart data in localStorage
- **Products:** Hardcoded JS product catalog (12-16 items)
- **Checkout:** Mock 3-step flow (no real payment processing)
