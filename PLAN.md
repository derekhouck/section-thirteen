# Plan: Match Jekyll theme to old WordPress theme

## Goal
Customize the current Jekyll `minima` theme to visually match the original WordPress site at https://sectionthirteen.com/.

## Reference
- **Styles Source of Truth:** https://sectionthirteen.com/wp-content/themes/section-thirteen/style.css

## Key Visual Elements to Replicate
- **Logo/Header:** Centered/Left-aligned logo in the header.
- **Navigation:** Menu with "Superfan" and "Press Releases".
- **Typography:** Specific serif/sans-serif pairings and spacing.
- **Post Styling:** Metadata (date, author) and content layout.

## Progress
### Completed
- [x] **Header Structure:** Refined `_includes/header.html` for better branding/nav separation.
- [x] **Header Styling:** 
    - [x] Implemented brand color `#51C6DD` and text color `#404040`.
    - [x] Set base font sizing and line-height.
    - [x] Fixed logo alignment (centered on home, left-aligned on sub-pages).
    - [x] Removed header borders/bars.
- [x] **Layout Adjustments:** Added `.home` class to `<body>` for home-specific styling.

### Remaining
- [ ] **Typography:** Refine font pairings and weights across the site.
- [ ] **Navigation:** Finalize any mobile navigation refinements.
- [ ] **Post Styling:** Match metadata and content layout style from the WordPress site.
- [ ] **Footer:** Match footer styling and layout.
