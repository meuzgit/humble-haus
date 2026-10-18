# Humble Haus theme

Theme code for the Humble Haus Shopify store (humble.haus, `4wfkeh-ma.myshopify.com`).
Decisions, plans and session logs live in the vault (`github.com/meuzgit/vault`):
start with `output/Humble Haus/Humble Haus Store Build - Kickoff.md`, then
`wiki/Humble Haus/Humble Haus Hub.md` and `Humble Haus Decisions.md`.

## Rules
- Work only on the unpublished theme **"Humble Haus · build"** (`163484434537`).
  Never `shopify theme publish`; never push to the MAIN theme (Savor 3.4.0).
- Auth: Theme Access password in `SHOPIFY_CLI_THEME_TOKEN`, store in `SHOPIFY_FLAG_STORE`.
  Never print or commit the token.
- Never change products' live state, prices, customer emails or the plan without Ray's OK.
- Public copy: never name Ray; "less expensive", never "cheaper"; no invented history (HH-037).

## Layout
The theme is Savor 3.4.0. Humble Haus adds its own layer, prefixed `hh-`:
- `assets/hh.css`: jobs' look (HH-045), scoped under `.hh`.
- `sections/hh-*.liquid`, `snippets/hh-*.liquid`: cover, series, sign-up, two shelves, piece.
- Alternate templates: `templates/index.front.json`, `collection.house.json`, `product.piece.json`.

Store data the layer reads (metafields, menus) is listed in `docs/store-data.md`.

## Commands
    shopify theme check --path .
    shopify theme pull  --theme 163484434537
    shopify theme push  --theme 163484434537   # never --publish, never the MAIN theme
