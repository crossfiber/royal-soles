# Royal Soles — Preliminary Build Notes

**Client:** Royal Soles (IG: @royalsoless) · **Agency:** Cross Designs
**Status:** Concept prototype v0.2, for client review, pre-Shopify implementation

## v0.2 changes (Cross feedback)
- Opening view is the general inventory. The Drop is its own tab with the countdown.
- Stripped glass blur, pills, emojis, glow shadows. Flat, solid, hairline grid.
- Fonts per font bible: Archivo italic headline + Barlow body.
- Every listing carries a condition grade since stock is used pairs.
- Placeholder SVGs stay until real per-pair photos exist. No stock photos, ever:
  used shoes means each individual pair must be shot (4 angles) before listing.

## What this is
A single-file, app-style storefront prototype (`index.html`). Open it on a phone —
it's built mobile-first with a bottom tab bar so it feels like a native app
(GOAT/StockX pattern). All product data is placeholder.

## UX patterns borrowed from GOAT / StockX
- **Bottom tab navigation** (Home / Browse / Search / Bag) — app feel, thumb-reachable
- **Image-heavy product cards** (GOAT) over data-dense listings (StockX)
- **Drop hero with live countdown** to Friday 7PM — creates urgency, drives the weekly cadence
- **Evergreen "Vault" catalog** alongside drops, per client requirement
- **Size-first product sheet** — bottom sheet slides up, size grid, sold-out sizes struck through
- **Instant search** with quick-filter chips (brand, size, price)
- **Trust row** on product page: authenticity, ship time, returns

## Brand
Black `#0A0A0A` · Gold `#FFC72C` · Off-white ink. Heavy italic Archivo for headers
(matches logo's athletic slant). Crown motif used sparingly.

## Shopify implementation plan
1. Redesign client's existing store — build this as a custom theme (Liquid) or heavily
   modified premium theme
2. Products = 1 per shoe with size variants (full size runs)
3. Collections: "Drops" (scheduled publishing, Friday 7PM) + "The Vault" (evergreen)
4. Facebook & Instagram channel → Meta Commer