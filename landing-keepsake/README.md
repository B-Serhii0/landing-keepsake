# Keepsake — landing page

Adaptive single-page landing for the design agency **Keepsake**, built from the Figma layout
(Desktop 1280 / Tablet 768 / Mobile 375 / Mobile menu open / UI states).

**Demo:** https://YOUR-USERNAME.github.io/landing-keepsake/

## Technologies
- HTML5 (semantic: `header`, `nav`, `main`, `section`, `article`, `footer`, `form`), one `h1`, correct heading hierarchy
- CSS only — no frameworks, no UI libraries, **no JavaScript**
- Fonts from Google Fonts with `font-display: swap`: Oswald (300/400/700), Open Sans (300/400/700), Dancing Script 700, Lora (client logos and the card artwork, as in the layout)
- Inline SVG icons (SVG sprite with `<symbol>` + `<use>`)

## Decisions
- **Mobile first:** base styles are for 375px (valid from 320px), then `@media (min-width: 768px)` and `@media (min-width: 1280px)`.
- **Design tokens:** all colors, fonts, spacing and sizes live in `:root` of `css/style.css` and are overridden per breakpoint.
- **Layout:** Flexbox everywhere (header, hero, services, stats, clients, journal, footer); CSS Grid only for the works cards (1 / 2 / 3 columns, `aspect-ratio` 1 : 0.72 on mobile and 1 : 0.79 above).
- **Container:** side gutters 20 / 40 / 90px, `max-width: 1100px` content centered on wide screens; no horizontal scroll (only the chips row scrolls on mobile).
- **Mobile menu without JS:** a native checkbox laid over the burger icon + `:checked ~ nav`; the burger turns into a cross.
- **Portfolio filter without JS:** radio inputs + `:checked ~` and `data-category`.
- **Card hover:** the same overlay state is triggered by `:hover` and `:focus-within` (keyboard).
- **Newsletter form:** HTML validation (`type="email"`, required consent), error state via `:user-invalid`, success state via `:target` (the form submits to `#subscribed`).
- **Fixed header:** `position: fixed`; where supported (`animation-timeline: scroll()`) it shrinks to 64px with a shadow after scrolling.
- **Back-to-top** button (44×44) is always visible.
- **Accessibility:** visible `:focus-visible`, `aria-label` on icon links, `<label>` for form fields, error linked with `aria-describedby`, decorative images with `alt=""`, `prefers-reduced-motion` respected.
- **Performance:** journal images are WebP with `width`/`height` and `loading="lazy"`; the work-card artwork is inline SVG.

## Structure
```
landing-keepsake/
├── index.html
├── css/        reset.css, style.css
├── images/     journal-1..4.webp
└── fonts/
```
