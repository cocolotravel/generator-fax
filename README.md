# generator-fax

Internal FAX tools for **Cocolo Travel** (ここロトラベル合同会社). Static, client-side web pages used to generate hotel reservation-request faxes and free-form fax documents as PDF or `.docx`, no backend or build step required.

## Pages

- [`index.html`](index.html) — landing page linking to the two tools below.
- [`fax-reservations.html`](fax-reservations.html) — builds a hotel reservation-request fax. Supports bundling multiple reservations into a single fax and includes a lookup of ~450 hotels (name, romaji, phone, fax) from [`data.json`](data.json).
- [`fax-doc.html`](fax-doc.html) — builds a free-form fax document (inquiries, complaints, etc.) with an option to save to Nextcloud.
- [`404.html`](404.html) — custom 404 page for static hosting.

## Data

[`data.json`](data.json) contains the hotel directory used by `fax-reservations.html`:

```json
{
  "hotels": [
    { "name": "...", "romaji": "...", "tel": "...", "fax": "..." }
  ]
}
```

## Tech

Plain HTML/CSS/JS, no framework and no package manager. PDF and `.docx` export run entirely in the browser via bundled/CDN-loaded libraries ([html2pdf.js](https://github.com/eKoopmans/html2pdf.js), JSZip).

## Usage

Open `index.html` in a browser, or deploy the directory as-is to any static host (currently served at `fax.cocolotravel.com`).
