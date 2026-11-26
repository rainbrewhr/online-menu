# Rainbrew Online Menu

Online menu for Rainbrew Coffee Shop: https://rainbrewhr.github.io/online-menu/

## What's here

| File | What it is |
| --- | --- |
| `index.html` | The menu. Customers tap prices to build an order, then send it on Messenger. |
| `table-card.html` | A printable table card with the QR code. |
| `qr.svg` | QR code that opens the menu. |
| `og.png` | The preview image shown when the link is shared on Facebook. |
| `favicon.svg`, `apple-touch-icon.png` | The browser tab and home-screen icons. |

## Prices come from the Google Sheet

The menu reads its items and prices from **Rainbrew Menu 11.26.26 (source of truth)** each time someone opens it. To change a price, edit the sheet. The website updates on the next visit, with no code change needed.

- **Sharing:** the sheet must be shared as **Anyone with the link → Viewer**. If the site can't read it, it falls back to the menu built into `index.html`.
- **Columns the site reads (by header name):**
  - Category, Item, Size / Variation, Contents / Description, Walk-in price, Online price
  - Optional **Tags**: comma-separated, any of `Best seller`, `New`, `Spicy`, `Sold out`
  - Optional **Photo**: a file name from the `photos/` folder (e.g. `halo-halo.jpg`), a Google Drive share link (the file must be shared as "Anyone with the link"), or any `https://` image link
- **What customers see:** the "Contents / Description" column, so keep it customer-friendly. Notes are never shown.
- **Walk-in prices:** when the sheet has them, customers can switch between online and walk-in prices. Orders always use online prices.
- **Special descriptions:** the "Must Try Specials" descriptions live in `index.html`. Their prices come from the matching items in the sheet.

## Contact details

Edit `CONFIG` near the top of the script in `index.html`:
- Messenger and Facebook links
- the sheet link
- phone, address, opening hours and map link (each one appears on the page once it's filled in)
