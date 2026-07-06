# Royal Soles — Preliminary Build Notes

**Client:** Royal Soles (IG: @royalsoless) · **Agency:** Cross Designs
**Status:** Concept prototype v0.1 — for client review, pre-Shopify implementation

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
4. Facebook & Instagram channel → Meta Commerce Manager for IG Shop; inventory syncs
   both ways automatically
5. Checkout stays 100% Shopify (Shop Pay / Apple Pay)
6. Client manages inventory via Shopify mobile app; bulk weekly intake via CSV/Matrixify

## Open questions for client
- Product photography: who shoots the 300 pairs/week? Consistent background?
- Does he want accounts/wishlists ("cop lists") at launch?
- Sizing: mens only, or GS/womens too?
- Drop cadence confirmed Friday 7PM EST?
- Shipping rates + return policy
