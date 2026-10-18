# Store data the Humble Haus theme needs

The `hh-` sections read these from Shopify. Theme Access cannot create them, so Ray or
the Cowork session sets them up through the Shopify connector or admin. Nothing here
changes a product's live state or price.

Namespace for everything: `humble_haus`.

## Product metafields (HH-023, HH-037, HH-045)

| Key | Type | Example | Used for |
|---|---|---|---|
| `shelf` | Single line text, choices `Original`, `In print` | `Original` | Which shelf; badge. Empty is read as Original. |
| `piece_number` | Single line text | `001 / 01`, `001 / P1` | The mono number. Nothing shows if empty. |
| `credit` | Single line text | `Maker unknown · about 1970` | Credit line under the name (HH-037). |
| `condition` | Multi-line text | `A hairline in the glaze near the rim.` | "Condition" / "Condition, as sold". |
| `size` | Single line text | `12 cm wide · 7.5 cm tall` | Size, in mono. |
| `companion` | Product reference | the Haus 001 cloth | "Made around this piece" (HH-033, HH-035). |

Turn on **storefront access** for each definition, or Liquid cannot read it.

## Collection metafields (a House is a collection, HH-021, HH-047)

| Key | Type | Example | Used for |
|---|---|---|---|
| `house_number` | Single line text | `001` | Makes the collection a House: it joins the series list and the cover reads "HAUS 001". |
| `tagline` | Single line text | (one line per House) | Line under the House name. No provenance claims (HH-021). |
| `cover_color` | Color | muted, from the House's cover photo | The cover field. Navy `#1F1C5B` must reach 4.5:1 on it. |
| `published_on` | Date | `2026-11-06` | "Published 2026-11-06". |

Each House collection also needs: the **House template** (`collection.house`), its two
sentences as the collection description, a lived-in cover photo as the collection image,
and a manual sort order that follows the piece numbers.

**Not yet:** the three House collections themselves wait for Ray's answer on the split
and launch order (HH-047).

## How "Gone" works (HH-024)
An Original that is not available (stock 0, inventory tracked) is shown as Gone: paler,
no price, no button, kept on record. In print pieces are never shown as Gone.
**All 66 test products have 0 stock today**, so every Original previews as Gone until
real stock is set for the pieces that are for sale.

## Navigation and header (HH-045)
- `main-menu`: Houses (the House page, or a Houses list once there is more than one), About (a page).
  Bag is the header's cart icon.
- Header: search, country and language selectors off. This is in the theme's header
  settings, done on the build theme after the full theme pull.

## Assigning the templates
- Front: once Haus 001 exists, set `index.front.json`'s House to it, then move that
  layout into `index.json` on the build theme (after the pull).
- Products in a House: product template `piece`.
