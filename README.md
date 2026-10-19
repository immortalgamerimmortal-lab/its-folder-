# Morrow Market demo

An independent storefront demo with a cinematic product story, a connected sign-in/sign-up screen, a full-screen product detail view, and a browser-persisted shopping cart. The existing catalog in `index.html` remains the source of truth.

## Run locally

Open a terminal in this folder and run `py -m http.server 8001`, then visit `http://localhost:8001/`. A local server is recommended for consistent navigation and browser storage.

## Product details

The details experience reads each item from the existing `products` array. Values not present in the catalog (brand, model, SKU, stock, specifications, gallery views, warranty, and delivery information) are labeled as unavailable rather than invented. Existing rating/review numbers are labeled sample data; no customer testimonials are presented as verified.

To enrich an item, optional catalog fields supported inline in `index.html` include `brand`, `model`, `sku`, `availability`, `gallery` (image URLs or `{ image, alt }` objects), `features`, `specifications`, and `details`. `variants` can include `id`, `color`, `size`, `sku`, `price`, `was`, `image`, and `availability`. Variation cart entries preserve the selected options and price; existing quantity-only localStorage cart entries remain readable.

The delivery PIN interaction checks only the six-digit format. Checkout is a summary only and does not process payment or place an order. Demo auth stores a name/email in localStorage but does not verify credentials or provide secure authentication. A real launch requires a backend auth/session service, product and order database, delivery integration, and payment provider. Social sign-in and password recovery are also not connected.

Product photography and display fonts load from Unsplash and Google Fonts; a local image fallback is shown when an image fails.
