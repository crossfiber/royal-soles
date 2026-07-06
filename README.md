# royal soles

Client: Royal Soles (IG: @royalsoless). Used sneaker resale, weekly drops plus standing inventory.
Engagement: custom app-style storefront, implemented into the client's existing Shopify store
(royalsoles.net, currently Pause and Build plan).
Repo: github.com/crossfiber/royal-soles (public, hosted on Pages).
Live preview: https://crossfiber.github.io/royal-soles/

## Update log

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