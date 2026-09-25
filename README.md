# Aylatelier Store

Bilingual (Arabic / English) online store for Aylatelier, handmade girls' party dresses and sets from Cairo.

It is a static site: one `index.html` plus product photos in `img/`. No build step, no server code.

## Folder layout

```
index.html      the whole store (layout, products, cart, checkout)
img/            product photos, 1000x1250 (4:5)
img/t/          small versions of the same photos for the shop grid, 480x600
```

## Publish it with GitHub Pages

1. Push these files to the root of the repo (`main` branch).
2. On GitHub: **Settings > Pages > Build and deployment**.
3. Source: **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
4. After a minute the store is live at `https://<your-username>.github.io/<repo-name>/`.

## Before going public

Open `index.html` and edit the `STORE` block near the top of the `<script>`:

- `whatsapp`: your real number with country code and no `+` (for example `2010xxxxxxxx`). Every order is sent here.
- `instagram` and `email`.

Prices marked `/* PRICE TBC */` in the `PRODUCTS` list are placeholders. Replace them with the real price for size 2-3.

## How products work

- Each product in `PRODUCTS` has a base `price` for size 2-3. Every size up adds `SIZE_STEP` (100 EGP). Sizes: 2-3, 4-5, 6-7, 8-9.
- `colors` lists the colours. Each colour can have photos: `{c:"pink", img:["st_pink"]}` means `img/st_pink.jpg` and `img/t/st_pink.jpg`.
- A colour with no `img` is shown as "sewn to order in this colour" using the main photo.
- Photo names ending in `_f` show as Front, `_b` as Back, `_fb` as Front & back.
- `anyColor: true` adds an "Other colour" option where the customer types the colour.
- New colour names go in the `COLORS` table (English, Arabic, swatch colour).

## Adding a new photo

Make it 4:5 portrait. Save a 1000x1250 copy in `img/` and a 480x600 copy with the same name in `img/t/`, then add the name to the product's `colors`.

## Product links

Every product has its own link, for example `index.html#p-stella` or `index.html#p-stella-pink` for a specific colour. You can share these on Instagram or WhatsApp.

## Payments

Checkout collects the delivery details and sends the order to WhatsApp. Card payments are not connected yet.
