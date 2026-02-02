# AfriTODAY NEWS — Project Documentation

This repository contains a simple responsive news/blog template composed of HTML, CSS, and a small JavaScript snippet for interactivity.

## Files

- `deep.html` — Main HTML page containing site structure: header with navigation, articles grid (25 sample articles), pagination, and footer.
- `stingo.css` — Main stylesheet that provides variables, layout, responsive rules, and component styles for the site.
- `images/` — Directory for article and header images used by the HTML.

## Overview

The page is a static news/blog layout optimized for readability and mobile-first responsiveness. The CSS uses CSS variables (in `:root`) to centralize colors, spacing, typography, and transitions. The layout relies on CSS Grid for the article cards and flexbox for header/footer components.

## Key Sections

- Header and Navigation (`.site-header`, `.main-nav`) — Contains the brand, navigation links, a mobile `menu-toggle` button, and social links. The navigation adapts between horizontal menu on wider screens and a hamburger-triggered vertical menu on small screens.

- Articles Grid (`.articles-grid`) — Uses `grid-template-columns: repeat(auto-fill, minmax(320px, 1fr))` to create responsive cards that wrap naturally.

- Footer (`.site-footer`) — Grid-based footer with sections for about, categories, quick links, social links, and a footer bottom area with copyright and back-to-top link.

## CSS: `stingo.css` Highlights

- CSS Variables: Colors, spacing, typographic sizes, radii, and shadows are defined in `:root` for easy customization.
- Utility Classes: Small helpers like `.text-center`, `.mt-medium`, `.mb-large` are included for quick adjustments.
- Accessibility: A `.skip-link` is present for keyboard users, and focus-visible styles are provided for interactive elements.
- Responsive Rules: Breakpoints at `768px` (tablet) and `480px` (mobile) adjust header layout, menu behavior, grid columns, and typography.
- Motion Respect: `@media (prefers-reduced-motion: reduce)` disables transitions and animations when the user requests reduced motion.

## JavaScript Behavior (in `deep.html`)

There is a small script near the end of `deep.html` that handles two things:

1. Current year update: It finds the element with the ID `current-year` and sets its text content to the current year using `new Date().getFullYear()` so you do not need to update the copyright year manually.

2. Mobile menu management:
   - Selects `.menu-toggle` and `.nav-menu` elements.
   - When the menu toggle is clicked, it toggles the `aria-expanded` attribute on the button and toggles the `active` class on the `.nav-menu` to show/hide the mobile menu.
   - A document-level click listener closes the menu if the user clicks outside of `.main-nav` while the menu is open.

Accessibility note: The script updates `aria-expanded` so assistive technologies can detect the menu state.

## How to Run / Preview

1. Open `deep.html` in a web browser (double-click or `Open With` in your editor). No server is required for static preview.
2. For live reload while editing, use a lightweight development server (e.g., VS Code Live Server extension or `npx serve`).

## Quick Customization Tips

- Change brand colors: Edit the variables `--primary`, `--secondary`, and `--accent` in `stingo.css` under `:root`.
- Adjust spacing: Modify `--spacing-md`, `--gap-lg`, etc., to affect paddings and gaps globally.
- Add articles: Duplicate an existing `<article class="article-card">` block in `deep.html` and update its image, date, title, excerpt, and links.
- Tweak mobile menu behavior: The script is minimal and easy to extend — consider adding keyboard support for `Escape` to close the menu.

## Suggested Next Steps

- Add properly sized local images to the `images/` folder for offline preview and better performance.
- Minify `stingo.css` for production and add a small build step if you expand the project.
- Consider splitting inline JavaScript into a `main.js` file for separation of concerns.

---
