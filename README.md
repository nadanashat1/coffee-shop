# Coffee Shop - bilingual portfolio demo

Arabic and English React storefront with correct RTL/LTR layout, a bundled sample menu, integer-based price calculations, a PostgreSQL-backed anonymous-session cart, and a clearly labelled demo checkout. The Node serverless API persists menu, cart and demo orders in a separate Neon PostgreSQL database. No real authentication, payments, shipments, or commercial orders are enabled. No personal or payment details are collected.

## Run

```sh
npm install
npm run dev
npm run build
```

Node 20+ recommended. Vite builds the root app into `dist`. `index.html` loads `2-app.jsx`, which imports `1-styles.css`. The numeric prefixes were added by the repository upload interface and are intentional.

## Scope and data

The root app is the approved bilingual redesign. The original React template is preserved unchanged under `Downloads/coffee-shop-main/coffee-shop-main/` for history and attribution. The new app does not call the original localhost JSON server, load broken Starbucks product images, or display template login forms as if they were functional accounts.

The menu uses sample product names and AZN amounts from the original `db.json`; Arabic product labels were added. Currency is not converted. Prices are represented as integer minor units and quantities are limited to 20 per item. The language uses localStorage. Cart and the five most recent demo receipts are stored in PostgreSQL and scoped by an opaque HttpOnly, Secure, SameSite=Lax session cookie, stored hashed on the server. Clearing cookies loses access to that anonymous history; it does not provide cross-device account access. No names, addresses or payment data are requested.

## Backend

Set server-only `DATABASE_URL` in Vercel Production. Never use a VITE_ prefix or commit the connection. `api/coffee.js` supplies GET initialization and POST cart/checkout operations. Product prices and totals are calculated server-side in integer minor units. Cart quantities are validated (0-20), checkout is transactional and idempotent, and requests are origin-checked. Demo checkout is limited to five orders per session per hour. This is not production-grade abuse protection, account authentication, fulfilment or payment processing. Free-tier compute can cold-start after inactivity.

## Attribution

Hero photography is the original template's Corretto / Qode Interactive image, preserved in the root CSS as an embedded asset. Original source URL: https://corretto.qodeinteractive.com/wp-content/uploads/2018/04/home-1-slider-image-1.jpg . The original template and its attribution are retained; no claim of exclusive authorship of the template or photography is made. Caladea and Noto Arabic fonts retain their upstream open font licenses. This is a non-commercial portfolio demonstration, not a real coffee business.
