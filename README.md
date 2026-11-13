# Coffee Shop - bilingual portfolio demo

Arabic and English React storefront with correct RTL/LTR layout, a bundled sample menu, integer-based price calculations, a device-local persistent cart, and a clearly labelled demo checkout. No backend, real authentication, payments, shipments, or commercial orders are enabled. No personal or payment details are collected.

## Run

```sh
npm install
npm run dev
npm run build
```

Node 20+ recommended. Vite builds the root app into `dist`. `index.html` loads `2-app.jsx`, which imports `1-styles.css`. The numeric prefixes were added by the repository upload interface and are intentional.

## Scope and data

The root app is the approved bilingual redesign. The original React template is preserved unchanged under `Downloads/coffee-shop-main/coffee-shop-main/` for history and attribution. The new app does not call the original localhost JSON server, load broken Starbucks product images, or display template login forms as if they were functional accounts.

The menu uses sample product names and AZN amounts from the original `db.json`; Arabic product labels were added. Currency is not converted. Prices are represented as integer minor units and quantities are limited to 20 per item. The cart, chosen language and last demo receipt use localStorage on the visitor's browser only. Clearing browser data clears them. If storage is unavailable, the cart works in memory for the current visit.

## Attribution

Hero photography is the original template's Corretto / Qode Interactive image, preserved in the root CSS as an embedded asset. Original source URL: https://corretto.qodeinteractive.com/wp-content/uploads/2018/04/home-1-slider-image-1.jpg . The original template and its attribution are retained; no claim of exclusive authorship of the template or photography is made. Caladea and Noto Arabic fonts retain their upstream open font licenses. This is a non-commercial portfolio demonstration, not a real coffee business.
