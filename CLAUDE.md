# CLAUDE.md - Glammore Salon Website

## Project Overview

Static marketing website for **Glam'more Beauty Salon** (Harrisburg, PA). Single-page design built with HTML5, CSS3, vanilla JavaScript, and Tailwind CSS via CDN.

## Repository Structure

```
glammore-salon/
├── index.html    # Main single-page website (~48 KB, contains all sections)
├── style.css     # Supplementary CSS styles
└── CLAUDE.md     # This file
```

This is a two-file project. All markup, Tailwind config, custom CSS, and JavaScript live inside `index.html`. The `style.css` file provides minimal supplementary styles.

## Tech Stack

- **HTML5** - Semantic markup, single-page layout
- **Tailwind CSS** - Loaded via CDN (`https://cdn.tailwindcss.com`), no local build
- **Vanilla JavaScript** - ES6, inline in `index.html`
- **Google Fonts** - Cormorant Garamond (serif), Montserrat (sans-serif)
- **Font Awesome 6.4.0** - Icons via CDN
- **Google Maps Embed** - Contact section map
- **Unsplash** - Gallery and hero images

## No Build Tools Required

There is no `package.json`, no bundler, no Node.js dependency. To run locally:

```bash
python -m http.server 8000
# or
npx http-server
```

No build, test, or lint commands exist.

## Page Sections (Anchor IDs)

| Section    | ID          | Description                        |
|------------|-------------|------------------------------------|
| Hero       | `#home`     | Landing with CTA                   |
| Services   | `#services` | 6 service cards (cuts, color, etc) |
| About      | `#about`    | Salon story                        |
| Gallery    | `#gallery`  | 8 portfolio images                 |
| Contact    | `#contact`  | Appointment form + map             |

## Design System

### Custom Colors (Tailwind config in `index.html`)

| Token          | Hex       | Usage              |
|----------------|-----------|--------------------|
| `glam-gold`    | `#D4AF37` | Primary accent     |
| `glam-rose`    | `#E8B4B8` | Secondary accent   |
| `glam-dark`    | `#2C2C2C` | Dark text          |
| `glam-cream`   | `#FAF7F2` | Light backgrounds  |
| `glam-charcoal`| `#3A3A3A` | Charcoal text      |

### Fonts

- **Headings:** Cormorant Garamond (serif, weights 300/400/600)
- **Body:** Montserrat (sans-serif, weights 300/400/500/600)

### Custom CSS Classes

- `.glass-nav` - Frosted glass navbar
- `.text-glam-gradient` - Gold gradient text
- `.hero-pattern` - Hero background pattern
- `.service-card` - Service card styling
- `.gallery-item` - Gallery image container
- `.btn-glam` - Primary CTA button
- `.reveal` - Scroll-triggered fade-in animation

### Custom Animations

- `fade-in-up` - 0.8s entrance animation
- `float` - 6s infinite floating effect

## Naming Conventions

- **CSS classes:** kebab-case (`glass-nav`, `service-card`)
- **Color tokens:** `glam-` prefix (`glam-gold`, `glam-dark`)
- **HTML IDs:** kebab-case, descriptive (`navbar`, `menu-btn`, `mobile-menu`)
- **JavaScript:** camelCase variables, `const`/`let` only, arrow functions

## Responsive Design

Mobile-first using Tailwind breakpoints:
- **Default:** Single column
- **`md` (768px):** Two-column layouts
- **`lg` (1024px):** Three/four-column grids

## Interactive Features

- **Mobile hamburger menu** - Toggle via `#menu-btn`
- **Scroll reveal** - Elements with `.reveal` class animate on scroll
- **Smooth scrolling** - Anchor navigation
- **Contact form** - Client-side validation only (no backend)

## Key Conventions for Editing

1. **All changes go in `index.html`** unless adding new static assets
2. **Use Tailwind utility classes** for styling; avoid adding to `style.css` unless necessary
3. **Follow the existing color palette** - use `glam-*` tokens, not raw hex
4. **Keep CDN dependencies** - do not convert to a local build setup without explicit request
5. **Maintain responsive behavior** - test across breakpoints when modifying layout
6. **Images use Unsplash URLs** with size parameters (e.g., `?w=800&h=600`)
