# ROYAL SOLES - PROJECT HANDOFF
Prepared 2026-07-08 by the Cowork build session. Everything a new project needs to continue this work.

## The client and the job
Royal Soles (IG @royalsoless) is a used-sneaker resale business run by Cross's friend (Jesus, store owner email jesusells12@gmail.com). He moves roughly 300 pairs a week. Cross Designs (Aiden/Cross, freelance web + Meta ads operator) is building him an app-feeling storefront on his EXISTING Shopify store. Model: weekly drops (Friday 7PM EST) plus an always-available general inventory. Wants to run everything from his phone and sync inventory with Instagram Shop.

## Current state: LIVE
- Custom Liquid theme "Royal Soles by Cross Designs" is PUBLISHED on royalsoles.net (v1.0.3 published, v1.0.4 shipped and awaiting publish; v1.0.1 and v1.0.2 are dead, delete from library).
- Store is on Pause and Build plan: storefront is behind a password page and checkout is disabled until the client resumes a paid plan (Settings > Plan) and removes the password (Online Store > Preferences).
- Design prototype (static, pre-Shopify) also hosted at https://crossfiber.github.io/royal-soles/

## Infrastructure
- GitHub repo: github.com/crossfiber/royal-soles (PUBLIC because free-plan Pages required it). Contains: index.html (v0.5 static prototype), theme-src/ (Liquid theme source), royal-soles-theme.zip (deploy artifact), README.md (full dated update log), build-notes.md.
- Local client folder: Downloads/Agency/Clients/royal soles/ (same files plus assets/). WARNING: this folder had a file-sync issue that silently truncated index.html at its previous byte size during edits. Root cause unresolved (suspect file lock or sync layer on the host). Verify file integrity after every write: file must end with </html>.
- Shopify: store royalsoles.net, currency USD, timezone EDT. Connected via Shopify MCP.
- GitHub account: crossfiber. The access token used this session was pasted into chat and should be treated as compromised. REVOKE it and issue a fresh one. Do not reuse.

## Shopify data model (already in place, matches how the client already lists)
- One product per shoe. One variant per size, each variant has its OWN price (used pairs price by size) and quantity 1.
- Smart collection "The Drop" (handle the-drop): auto-includes any product tagged `drop`. Untag to roll into general inventory.
- Smart collection "Shop All" (handle shop-all): any variant price > 0, sorted CREATED_DESC. Powers homepage.
- 17 active products from 2022-23 flowed in automatically.

## Theme architecture (theme-src/)
- layout/theme.liquid: all CSS inline, masthead (big centered logo), gold dropstrip with live countdown to next Friday 7PM EST, desktop nav, mobile bottom tab bar (Shop / Drop / Search / Bag), footer, shared JS (countdown, toast).
- templates/index.liquid: "Just In" horizontal shelf (6 newest) + "Shop All" grid + size filter bottom sheet (client-side, GOAT style).
- templates/product.liquid: standard fixed-height photo frame, size buttons per variant, price snaps to selected size, add to cart.
- templates/collection.liquid: The Drop gets hero + big countdown; other collections plain grid.
- templates/cart.liquid, search.liquid, page, 404, blog, article, list-collections stubs. config/settings_schema.json. assets/logo.jpg.
- Design system: pure #000 bg (matches logo), gold #F2B90D, panels #0D0D0D, Archivo italic 900 headlines, Barlow body. Built to Cross's Builda protocol: no glass/blur, no pills, no emojis, no em dashes anywhere, flat surfaces, GOAT/Flight Club editorial layout (image-led, airy).

## Change workflow (the safety model, learned the hard way)
- Product/inventory/price changes: pure data, flow to the live site instantly, no theme work.
- Code/design changes: MCP cannot write to or publish the live theme. Ship as a NEW theme version: patch theme-src, rezip, commit to repo, themeCreate from the raw GitHub zip URL, client/Cross publishes in admin (10 seconds, old version stays as rollback).
- themeCreate source URL used: https://raw.githubusercontent.com/crossfiber/royal-soles/main/royal-soles-theme.zip

## Client's phone workflow (teach him this)
Shopify mobile app > Products > Add product: JPG photos (NOT HEIC), title, one variant per size with that size's price, qty 1 each. Tag `drop` if it's for Friday. Site updates itself. Sales anywhere decrement stock automatically.

## Open items, priority order
1. v1.0.4 needs publishing (fixed-height product photo frame, removes aspect-ratio dependency). Client reported verticals still blown up on v1.0.3; likely cache, but v1.0.4 is the bulletproof version. Confirm on Midnight Navy and Red Thunder 4s in a private tab.
2. Instagram Shop: install Facebook & Instagram channel in Shopify, connect Commerce Manager. Prereq: IG must be a Business account linked to a FB Page. This was a core client requirement (IG purchase decrements site stock) and is NOT done yet.
3. Go-live for real sales: client resumes paid plan + removes storefront password.
4. Vendor field: every product has vendor "Royal Soles". Set actual brands (Jordan, Nike, etc.) to enable brand filter chips (theme supports it once data is clean).
5. Photo SOP: mixed photo formats are the root of all image complaints. Standardize: landscape, same angle, same distance, JPG. Several old listings are HEIC (broken in some browsers) and should be re-exported.
6. Variant title typos in old listings ("SIze 11.5").
7. Footer placeholder pages need creating in admin: /pages/shipping-and-returns, /pages/size-guide. "Sell Us Your Pairs" link was speculative, confirm client actually buys pairs.
8. Condition grades (9/10 etc.) exist in the prototype but not the theme; decide on a tags or metafield convention if wanted.
9. Drop time is hardcoded Friday 7PM EST in theme.liquid JS; confirm with client or make it a theme setting.
10. Cross Designs intake form (cross-designs/intake.html) is service-business oriented; an e-commerce version for Royal Soles was discussed, never built.

## History short version
v0.1 static prototype (rejected: AI-glass look) > v0.2 protocol rebuild (flat, inventory-first) > v0.3 layout redesign (pure black, centered logo, GOAT-style airy grid) > v0.4 per-size pricing > v0.5 filter sheet + footer + grid fixes > file-truncation hotfix > Liquid port and Shopify deploy as v1.0 (client published same day) > v1.0.1-v1.0.4 product-image sizing iterations.
