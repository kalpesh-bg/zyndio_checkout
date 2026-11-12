# ZYNDIO Checkout

Customer-facing checkout for ZYNDIO orders billed through Sticky.io and
fulfilled through the White Label MD back office.

## Routes

| Route            | Component          | Purpose                                             |
| ---------------- | ------------------ | --------------------------------------------------- |
| `/`              | `Checkout2`        | Contact, shipping and payment capture; creates order |
| `/thankyou-page` | `NewThankyouPage`  | Post-purchase summary and member-portal handoff      |
| `*`              | `ErrorPage`        | Fallback                                             |

## URL parameters

| Parameter              | Meaning                                                     |
| ---------------------- | ----------------------------------------------------------- |
| `id`                   | WLMD product id, single or comma separated                  |
| `product_ids`          | Alternative multi-product id list                           |
| `email`                | Prefills the contact email                                  |
| `uniqueId`             | Passed through for WLMD order attribution                   |
| `campaign_id`, `cdata` | Campaign attribution                                        |
| `#a_aid=…`             | Affiliate id, preserved into the thank-you redirect         |

## Local development

```bash
nvm use
npm ci
npm start        # http://localhost:3000/?id=72
npm run build    # production bundle in build/
```

## Backend

Product, coupon and order calls go to `https://panel.whitelabelmd.com/zyndio/api/`
(see `src/utils/Constant.js`). Order creation and payment processing are handled
by the White Label MD back office and Sticky.io.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).
