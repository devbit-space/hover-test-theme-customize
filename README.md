# Shopify Theme: source-hover-test

Focused theme updates for Product Detail Page (PDP) customization and a public app integration. Built on standard Shopify theme structure (`layout`, `templates`, `sections`, `snippets`, `assets`, `config`, `locales`).

## What’s Included
- PDP theme customization: layout, content blocks, and UI/UX enhancements on the product page
- Public app integration: storefront integration using app blocks/app proxy/script tags (depending on store setup)

## Key Areas Touched
- `sections/main-product.liquid`: primary PDP markup and dynamic sections
- `templates/product.json`: PDP section composition and defaults
- `snippets/*`: reusable PDP elements (price, badges, inventory, etc.)
- `assets/*.css`, `assets/*.js`: PDP-specific styles and interactions
- `config/settings_schema.json`: theme settings controlling PDP options
- `locales/*.json`: translation keys for new PDP/UI strings

## Prerequisites
- Shopify store with Theme permissions
- Shopify CLI (v3+): https://shopify.dev/docs/themes/tools/cli

## Setup & Development
```bash
# Authenticate to your store
shopify login --store your-store.myshopify.com

# Start local development (hot reload)
shopify theme dev

# Optional: run theme checks
shopify theme check
```

## Configure the Public App Integration
- If using an app block: add the block via Theme Editor to the product template and set required block settings.
- If using an app proxy: ensure the app proxy URL is configured in the app, and the theme references the proxy endpoint where needed (e.g., via fetch in `assets/*.js`).
- If using a script tag: confirm the script loads on the product page and exposes any required globals/events.

Environment variables and secrets live in the app (not this repo). No secrets are stored in the theme.

## Testing the PDP
- Open a product URL during `shopify theme dev` to verify layout, variant switching, pricing, and app UI.
- Test with multiple products (with/without variants, different media types) and across breakpoints.

## Deployment
```bash
# Push as an unpublished theme for review
shopify theme push --unpublished

# (Optional) Pull changes from a live theme
shopify theme pull
```
Publish via Shopify Admin after validation. Tag releases in Git to track production versions.

## Support
Internal maintenance. See Shopify theme docs: https://shopify.dev/docs/themes
