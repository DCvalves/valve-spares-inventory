# Valve Spares Inventory

A standalone, offline-first inventory web app for valve spare parts. It does not modify or depend on the existing intervention-report application.

## Features
- Maintain valve records.
- Maintain a unique spare-part catalogue with **Hard** and **Soft** categories.
- Link one spare part to multiple valves and multiple parts to each valve.
- Track stock totals, manually adjust quantities, or scan barcodes with most USB/Bluetooth keyboard-wedge scanners.
- Select the parts and quantities required for a specific overhaul and calculate shortages.
- Coverage dashboard flags every unique **Soft** part linked to one or more valves that has fewer than one unit in stock.
- Export/import a JSON backup.
- Works as a static site; no server or account required.

## Run locally
Open `index.html` in a modern browser, or serve this directory with any static web server. For GitHub Pages, publish the repository root from the `main` branch.

## Data and backups
Data is stored in the browser's `localStorage` for this site's origin. It is **not synchronized** between users, browsers, or devices. Use **Export backup** and **Import backup** to transfer or restore data. Import replaces the current local dataset, so export a backup first.

Clearing browser/site data can erase the inventory. Keep regular backups outside the browser.

## Barcode workflow
1. Create a spare part and set its barcode / part number.
2. Open **Stock & scanning** and focus the scan field.
3. Scan each item; most keyboard-wedge scanners type the barcode and send Enter.
4. Choose add or remove mode. Each recognized scan changes the quantity by one.
5. For a stocktake that yields a total count, use **Set stock total** instead.

A barcode must match exactly one catalogue part. This version does not use a camera for barcode decoding.

## Link parts to valves
Use **Link valves** on a spare-part card and enter valve IDs to toggle associations. The IDs are shown in the prompt. Alternatively use **Manage parts** on a valve card and enter part IDs. IDs are generated automatically when a record is created.

## Safety notes
This app is local-only and intended as a lightweight inventory tool. It has no user accounts, automatic multi-device synchronization, or centralized audit trail. The backup JSON contains all inventory data; store it securely.
