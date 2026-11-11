# TabTap (MVP)

Scan. Split. Pay. No app, no waiting for the waiter.

Throwaway MVP of the idea from this TikTok: QR-code stand on every restaurant
table - scan it, your table's bill opens in the browser, pay by card or Apple
Pay, split by item so everyone pays for exactly what they ordered, tip without
the awkward conversation. Flip side of the stand carries a Google review QR.

## What this MVP does

- **Landing screen** with a demo QR - simulates the moment a diner scans the
  table stand.
- **Table bill** for a mock restaurant (Koshary El Tahrir, Table 7), itemized
  as if pulled live from the POS.
- **Split the bill**: check exactly the items you ordered and pay only those
  ("Pay my items"), or cover the whole table ("Pay full bill"). An item a
  friend already paid is shown as PAID and locked.
- **Tip picker** (0/5/10/15%) and 12% service charge, totals update live.
- **Mock checkout** via card or Apple Pay buttons - processing spinner, then a
  success screen showing what you paid and what remains on the table.
- **Review prompt** after paying - where the Google review flow would hook in.

## What it deliberately does NOT do

No backend, no real payments, no POS integration, no accounts. All data is
hard-coded in `index.html`. It is a concept demo, not the product. The real
hard parts (POS integration, restaurant onboarding, payment rails) are out of
scope on purpose.

## Run it

Open `index.html` in any browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

Single file, no build step. QR rendering uses the qrcodejs CDN; if it fails to
load, the app falls back to a placeholder and still works.

## If this proves out

The "real app" version needs: payment gateway integration (Stripe / Paymob /
Apple Pay on web), POS sync per restaurant, table/session management, and a
restaurant onboarding flow. None of that is here.
