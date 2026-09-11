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

**The site URL is hardcoded in four places** in `<head>` and they must all agree, or
link previews and search canonicalisation break:

```html
<link rel="canonical"        href="https://rangadevate-farm-fresh.netlify.app/">
<meta property="og:url"   content="https://rangadevate-farm-fresh.netlify.app/">
<meta property="og:image" content="https://rangadevate-farm-fresh.netlify.app/logo.jpg">
<meta name="twitter:image" content="https://rangadevate-farm-fresh.netlify.app/logo.jpg">
```

If the site is ever renamed again or moved to a custom domain, change all four **and**
regenerate `qr-farm.png` — it encodes the URL and will otherwise point at a dead host.

## The QR code

`qr-farm.png` encodes `https://rangadevate-farm-fresh.netlify.app` for gate and stall use.
860x860, QR version 5 (37 modules), 20px modules, 3-module quiet zone, brand green
`#17703C`, with a 240px rounded knockout carrying the farm seal. Error correction is
level H, which is what lets the seal sit over the middle. Decode-verified down to 160px
across lanczos, bicubic and box resampling.

## A note on certification

The farm holds a **PGS-India scope certificate at the GREEN tier** — certificate
`20260721123132`, issued 21/07/2026, valid to 21/07/2027, covering crop production over
9.36 Ha. It also holds Yelladakere Gram Panchayat general licence `13/2026-27`, valid to
13/07/2027. Both are set out in the `#certification` section.

**Green is not Organic.** PGS-India issues two marks: **Green** for land in conversion and
**Organic** for land that has completed the conversion period. This farm holds Green, so
the site says "PGS-India Green" and never "certified organic". Please keep it that way
until an Organic certificate is actually issued — claiming a grade you do not hold carries
real exposure under FSSAI's organic labelling rules.

The certificate scans are **not** in this repo. `.gitignore` excludes `*.pdf` because the
repo is public, and the licence scan carries the founder's photograph and handwritten
personal detail. The site publishes the numbers, which anyone can verify at
pgsindia-ncof.gov.in, and offers a copy on request.

When either document is renewed, the dates appear in four places in `index.html`: the
`#certification` cards, the contact card in `#order`, and the footer.

## Ordering

No payments are taken through this site. The basket produces an order enquiry sent by
WhatsApp or read out over the phone; availability, final weight and rate are confirmed
by the farm before anything is harvested, and payment is on delivery.
