# AI Agent Instructions

This document provides instructions for AI coding agents working on the Horizon Shopify theme.

## Repository Structure

This repository (`carbolance/horizon`) is a fork of the upstream Shopify theme (`Shopify/horizon`). We are customizing it for the Carbolance store.

- **Origin**: `https://github.com/carbolance/horizon` (this repo)
- **Upstream**: `https://github.com/Shopify/horizon` (official theme)

### Syncing with Upstream

When explicitly requested to sync with upstream:

1. Fetch upstream: `git fetch upstream`
2. Merge into main: `git merge upstream/main`
3. Resolve conflicts by **preferring upstream changes**
4. Re-apply Carbolance customizations after merge
5. Update `CUSTOMIZATIONS.md` if files changed

### Tracking Customizations

When you modify a file from the upstream theme, add a one-line entry to `CUSTOMIZATIONS.md` at the repository root. Format: `- \`path/to/file\` - brief description`

## Rules Location

Coding standards and guidelines are in `.cursor/rules/`. **Read the relevant rules files before making changes.**

## Rules by File Type

| Working With | Read These Rules |
|--------------|------------------|
| `.liquid` files | `liquid.mdc` |
| Sections (`sections/*.liquid`) | `sections.mdc`, `schemas.mdc` |
| Blocks (`blocks/*.liquid`) | `blocks.mdc`, `schemas.mdc` |
| Snippets (`snippets/*.liquid`) | `snippets.mdc` |
| Templates (`templates/*.liquid`) | `templates.mdc` |
| JavaScript (`assets/*.js`) | `javascript-standards.mdc`, `assets.mdc` |
| CSS (`assets/*.css`) | `css-standards.mdc`, `assets.mdc` |
| Locales (`locales/*.json`) | `locales.mdc`, `localization.mdc` |
| Theme settings | `theme-settings.mdc` |

## Accessibility Rules

When building interactive components, check the relevant accessibility guide in `.cursor/rules/`:

`accordion-accessibility.mdc`, `breadcrumb-accessibility.mdc`, `carousel-accessibility.mdc`, `cart-drawer-accessibility.mdc`, `color-contrast-accessibility.mdc`, `color-swatch-accessibility.mdc`, `combobox-accessibility.mdc`, `disclosure-accessibility.mdc`, `dropdown-navigation-accessibility.mdc`, `modal-accessibility.mdc`, `product-card-accessibility.mdc`, `product-filter-accessibility.mdc`, `sale-price-accessibility.mdc`, `slider-accessibility.mdc`, `switch-accessibility.mdc`, `tab-accessibility.mdc`, `tooltip-accessibility.mdc`

## Key Principles

### Liquid
- Use `{% liquid %}` for multiline code blocks
- Use `{% # comment %}` for inline comments
- Never invent new filters, tags, or objects
- Prefer inline Liquid over excessive variable declarations

### JavaScript
- Zero external dependencies - use native browser APIs
- Use the Component framework in `assets/component.js`
- Always use async/await over `.then()` chaining
- Use `const` over `let` unless mutation is required
- Use `for (const item of items)` over `.forEach()`

### CSS
- Never use IDs as selectors
- Avoid `!important` at all costs
- Target `0 1 0` specificity (single `.class` selector)
- Never hardcode colors - use color schemes
- Scope CSS variables to their components

### Accessibility
- Follow WCAG 2.2 AA standards
- Ensure keyboard navigation works properly
- Provide proper ARIA attributes

## Project Structure

```
horizon/
├── assets/          # JS, CSS files
├── blocks/          # Reusable block components
├── config/          # Theme configuration
├── layout/          # Theme layouts
├── locales/         # Translation files
├── sections/        # Theme sections
├── snippets/        # Reusable Liquid snippets
├── templates/       # Page templates
└── .cursor/rules/   # Coding standards (read-only reference)
```
