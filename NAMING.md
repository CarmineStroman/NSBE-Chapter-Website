# BEM Naming Plan

## Conventions
- Blocks are standalone components: `block`
- Elements are parts of a block: `block__element` (flat, never `block__a__b`)
- Modifiers are variants: `block--modifier`
- Style with single classes only. No bare tags, no `:first-child`/`:last-of-type` hooks, no descendant chains.
- IDs are for anchors and JS hooks only, never styling.

## Class map

| Block | Current class | New name | Type |
|---|---|---|---|
| **site-nav** | bare `nav` | `site-nav` | block |
| | `nav-menu` | `site-nav__menu` | element |
| | `nav-logo` | `site-nav__logo` | element |
| | (new) text links | `site-nav__link` | element |
| | `.nav-menu > a:first-child` | `site-nav__brand` | element (replaces position selector) |
| **hero** | `hero` | `hero` | block |
| | `hero-text` | `hero__text` | element |
| | `hero-media` | `hero__media` | element |
| | `logo` | `hero__logo` | element |
| | `.hero-text h1` | `hero__title` | element |
| | `.hero-text h3` | `hero__subtitle` | element |
| | `membership-actions` | `hero__actions` | element |
| **roadmap** | `membership-roadmap` | `roadmap` | block |
| **mission** | `mission` | `mission` | block |
| **offerings** | `offerings` | `offerings` | block |
| | `offering-container` | `offerings__list` | element |
| **offering-card** | `offering-card` | `offering-card` | block |
| | `.offering-card > img` | `offering-card__image` | element |
| | `.offering-card > h3` | `offering-card__title` | element |
| | `.offering-card > p` | `offering-card__text` | element |
| **get-involved** | `get-involved` | `get-involved` | block |
| | `.get-involved h2` | `get-involved__title` | element |
| | `.get-involved p` | `get-involved__text` | element |
| | `cta-actions` | `get-involved__actions` | element |
| **button** | `button` | `button` | block |
| | `button-primary` | `button--primary` | modifier |
| | `button-secondary` | `button--secondary` | modifier |
| **site-footer** | `site-footer` | `site-footer` | block |
| | `footer-brand` | `site-footer__brand` | element |
| | `footer-logo` | `site-footer__logo` | element |
| | `footer-divider` | `site-footer__divider` | element |
| | `footer-content` | `site-footer__content` | element |
| | `footer-about` | `site-footer__about` | element |
| | `footer-links` | `site-footer__nav` | element |
| | `footer-contact` | `site-footer__contact` | element |
| | `footer-bottom` | `site-footer__bottom` | element |
| | `.site-footer h2` | `site-footer__heading` | element |
| | `.footer-about p, .footer-contact p` | `site-footer__text` | element |
| | `.footer-links a, .footer-bottom a` | `site-footer__link` | element |
| | `.footer-bottom p:first-child` | `site-footer__legal` | element |

## Why the boundaries sit where they do
- **site-nav vs. site-footer__nav:** two different navs. The bare `nav` selector forced overrides on the footer nav, so each gets its own class.
- **Footer sections are elements, not blocks:** about, links, and contact never appear outside the footer.
- **hero is one block:** the membership page reuses the structure. Add `hero--membership` only if the styles end up differing.
- **roadmap is its own block:** it sits inside the hero today but could live anywhere.
- **offering-card is separate from offerings:** the card is reusable, and the section is just a container for it.
- **button is its own block:** it's mixed into other blocks (get-involved, hero), which is fine.
