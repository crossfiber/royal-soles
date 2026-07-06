# royal soles

Client: Royal Soles (IG: @royalsoless). Used sneaker resale, weekly drops plus standing inventory.
Engagement: custom app-style storefront, implemented into the client's existing Shopify store
(royalsoles.net, currently Pause and Build plan).
Repo: github.com/crossfiber/royal-soles (public, hosted on Pages).
Live preview: https://crossfiber.github.io/royal-soles/

## Update log

- 2026-07-06: v1.0 PUBLISHED by client (role MAIN on royalsoles.net). Shipped v1.0.1 as
  unpublished theme: object-fit contain on all product imagery (cards, product page, cart
  thumbs) so photos of any shape display uniformly instead of crop-zooming (Midnight Navy bug).
  Iteration model locked in: design/code changes ship as new unpublished theme versions via
  themeCreate, Cross/client publish in admin (API cannot write to or publish the live theme).
  Product/inventory/price changes need NO theme updates, they flow automatically. by Cowork session

- 2026-07-06: SHOPIFY DEPLOY. Ported v0.5 prototype to a full Liquid theme (layout, index with
  Just In shelf + size-filterable grid, product page with per-variant pricing, collection with
  Drop hero + countdown, cart, search, stubs, settings schema). Created "Shop All" smart
  collection (any variant price > 0, sorted newest first, 17 products picked up). Theme zip
  committed to repo, created on store via themeCreate as "Royal Soles by Cross Designs v1.0",
  processed clean, UNPUBLISHED. Publish must be done in admin (API publish blocked). Storefront
  behind password page until client resumes paid plan. by Cowork session

- 2026-07-06: HOTFIX. index.html had been silently truncated at 29,171 bytes during v0.4/v0.5
  edits (the old file's exact size, some sync layer was capping writes). The unterminated
  script tag disabled ALL JS: no products, dead tabs. Rebuilt the full file in the sandbox,
  added real integrity checks (file must end with /html, script extraction must be non-empty,
  all functions present) since previous syntax checks were passing vacuously on empty
  extractions. Also: masthead logo bumped to 110px mobile / 150px desktop, footer logo to 84px,
  removed "fresh pickups this week" tagline. by Cowork session

- 2026-07-06: v0.5 mobile UI pass. Root-caused the uneven column bug: nowrap product names were
  inflating grid tracks (also the source of the earlier zoom overflow); fixed with min-width:0
  on grid and rail cards. Just In rail now shows exactly 2 full cards per screen, no cut-off
  shoes. Filter chips replaced with a GOAT-style Filters bottom sheet (all brands and sizes
  wrapped, live "Show N pairs" apply button, clear button in toolbar). Removed the overlapping
  countdown labels on the Drop tab. Added a proper footer: brand block, Shop and Info link
  columns, Instagram link, copyright row. by Cowork session

- 2026-07-06: v0.4 per-size pricing. sizes map now carries a price per size, sheet shows the
  range until a size is picked then snaps to that size's price, cards show from-price, bag
  charges the picked size. Matches the existing store's data model (per-variant pricing).
  Also: mobile horizontal overflow clipped (blank space right of header on zoom). Shopify MCP
  connected; created smart collection "The Drop" (tag: drop) in the live store. by Cowork session
- 2026-07-06: v0.3 layout redesign per Cross feedback. Background now pure #000 to match logo
  black. Logo centered and enlarged in masthead. Opening view restructured GOAT/Flight Club
  style: Just In shelf of large cards up top, spacious Shop All grid below, no hairline tile
  borders (