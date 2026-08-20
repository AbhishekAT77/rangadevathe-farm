# Rangadevathe Organic Farm Fresh — website

Static site for **Rangadevathe Organic Farm Fresh**, Yelladakere, Hiriyur Taluk,
Chitradurga District, Karnataka 577598 — a working family holding operated by the
Dr. Devarahally T. Subhash Family Charitable Trust.

Single-page site: produce catalogue with a client-side basket, notes on how the farm
is worked, the founder's story, and ordering details.

## Files

| File | What it is |
|---|---|
| `index.html` | The entire site — HTML, CSS and JS in one file, no build step, no dependencies |
| `logo.jpg` | Farm seal, used for link previews when the URL is shared |

## Deploying

Any static host works. There is nothing to build.

**Netlify (connected to this repo):** New site → Import from GitHub → pick this repo.
Leave the build command empty and set the publish directory to `/`. Every push to
`main` then redeploys automatically.

## Editing

Two things live at the top of the `<script>` block near the bottom of `index.html`:

- **`CONTACT.phone`** — the farm's WhatsApp number, international format, digits only,
  no `+` and no spaces (e.g. `919886000000`). While it is empty the WhatsApp order
  button is hidden and customers can only copy their order as text.
- **`PRODUCTS`** — the catalogue. Each entry carries its price, unit, season and
  description. Prices are in rupees.

After the site has a real URL, update the two link-preview lines in `<head>` so
WhatsApp and Facebook show the farm seal:

```html
<meta property="og:image" content="https://YOUR-SITE.netlify.app/logo.jpg">
<meta name="twitter:image" content="https://YOUR-SITE.netlify.app/logo.jpg">
```

## A note on certification

The site does **not** claim the farm is certified organic, because it is not — PGS-India
certification is still being pursued. It describes the practices followed and states the
certification position plainly. Please keep it that way until a certificate is actually
issued; claiming organic certification you do not hold carries real exposure under
FSSAI's organic labelling rules.

## Ordering

No payments are taken through this site. The basket produces an order enquiry sent by
WhatsApp or read out over the phone; availability, final weight and rate are confirmed
by the farm before anything is harvested, and payment is on delivery.
