# Put KETER on Shopify

You do not need a custom domain or separate hosting. A Shopify store includes a `your-store-name.myshopify.com` address. An account and a store are different: if your account does not show a store admin, create a store from Shopify’s account dashboard first.

## Upload and preview

1. Download **KETER-Shopify-Theme.zip**. Keep it zipped.
2. Sign in at https://admin.shopify.com and select your store.
3. Open **Online Store → Themes**.
4. In the theme library, select **Add theme / Import theme → Upload ZIP file** (the wording can vary).
5. Select the KETER ZIP and upload it.
6. Use **Preview** on the uploaded theme. This previews the design without replacing your live theme.
7. Open **Customize / Edit theme** to replace campaign photography, edit hero copy, choose your main menu, and select a Complete the Look collection on product pages.
8. When you want KETER to become your storefront, use **Publish** on the KETER theme.

Publishing a Shopify theme is different from publishing this Codex cloud environment. Publishing the cloud environment alone does not put the website online.

## Find the store address

In Shopify, open **Settings → Domains** to find your built-in `myshopify.com` address. You can add a custom domain later. You can also use **View your store** from the Online Store channel.

If the store shows a password page, that is normal before launch. The theme includes a KETER coming-soon password page and newsletter form. Password removal and public selling depend on your Shopify plan and store settings. Check **Online Store → Preferences** for storefront password protection.

## Create the supporting pages

Under **Online Store → Pages** (or **Content → Pages**, depending on the admin layout), create these pages with the listed handles. Assign the corresponding theme template. Custom templates may only appear in the assignment dropdown after KETER is the published theme.

| Page title         | Handle             | Template           |
| ------------------ | ------------------ | ------------------ |
| Our Story          | `our-story`        | `our-story`        |
| How It Works       | `how-it-works`     | `how-it-works`     |
| Size Guide         | `size-guide`       | `size-guide`       |
| FAQ                | `faq`              | `faq`              |
| Contact            | `contact`          | `contact`          |
| Shipping & Returns | `shipping-returns` | `shipping-returns` |

Story, construction, sizing and FAQ layouts are included in the theme. Shipping & Returns displays approved page content or the store’s shipping/refund policies. Replace the illustrative size chart with approved production measurements before orders open.

Set the main menu in Shopify’s menus/navigation area, then select it in the theme Header settings. Shopify uses native routes: Shop is `/collections/all`; collections are `/collections`; editorial pages live under `/pages/...`. Product, cart and search routes use Shopify’s standard URLs.

## Products and commerce

Create products and collections in Shopify. Actual product pages, prices, inventory availability, variant IDs, media, search, collection sorting, cart and checkout come from Shopify. No mock products are automatically created or published.

Use option names **Color**, **Size**, and **Fit** where appropriate. Set Fit values to **Oversized** or **Slim Athletic**. Upload front photography first, back photography second, then additional images/videos. The media gallery also supports Shopify video, external video, and model media.

Optional product metafields in the `custom` namespace are `fabric`, `fabric_story`, `fit`, `construction`, and `care`. These populate editorial product details. Add approved pricing, measurements, inventory and descriptions before selling.

The homepage collection explorer, silhouette lab, macro materials and lookbook intentionally remain **concept studies** until approved brand assets replace them. Their product CTAs lead to the real Shopify catalog. The actual store catalog is empty until you add products; the theme displays an intentional first-drop empty state.

Collection filters use Shopify’s `collection.filters`. Configure supported filters through Shopify Search & Discovery if desired; sorting works independently.

## Email and contact

The native theme uses Shopify’s `customer` newsletter form and `contact` form. These submit directly to Shopify, unlike the device-only and downloaded-inquiry previews in the preserved Next.js version. Verify both in your uploaded store and check the Shopify customer list and notification email settings before launch. Signup confirmation only renders when Shopify reports success.

## What was checked

- Shopify’s official Theme Check: zero findings.
- Three local browser tests: homepage interactions, variant selection/AJAX cart, responsive routes and form field contracts.
- Local fixture tests simulate Shopify responses. They do **not** prove a real store’s checkout, payment setup, email delivery or hosted rendering.
- No theme was uploaded or published to your account; this workspace has no authenticated Shopify store connection.

## Source and maintenance

`shopify-theme/` is the native Online Store theme. Its homepage sections, product templates, scripts, and styles are separate files. The original Next.js storefront remains unchanged in `app/` and `components/`; Shopify cannot directly host that Next.js app.

Run `npm run theme:check` and `npm run theme:test` to validate the theme. `theme-tests/` is a local Liquid fixture renderer and browser tests, excluded from the theme ZIP. The ZIP contains only Shopify’s `assets`, `config`, `layout`, `locales`, `sections`, `snippets`, and `templates` directories.
