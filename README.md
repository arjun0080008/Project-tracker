# 📋 Project Tracker

A simple, public webpage that shows your projects live from a Google Sheet.
Edit the sheet → the page updates within a minute. No code, no redeploy.

**Columns:** Name · Status · Next Step · More Details · Important Dates

## How it works

- The page (`index.html`) reads a Google Sheet as CSV and renders it as a
  searchable, filterable table (with color-coded status badges and a
  mobile-friendly card layout).
- Data source (your sheet):
  https://docs.google.com/spreadsheets/d/1gFCCXv0fcYUguKR7_atG0V7eZYt7RZvH4wiGpy64_Ak/edit

## ⚠️ One-time setup (make the sheet public to read)

The page can only show the data if the sheet is viewable by anyone with the link:

1. Open the sheet (link above).
2. Click **Share** (top-right).
3. Under **General access**, pick **Anyone with the link** → **Viewer**.
4. Done. The page will load the data.

> "Viewer" only lets people *read* through the link — only you (and anyone you
> explicitly invite) can edit the sheet.

## Updating the tracker

Just edit the Google Sheet like any spreadsheet:
- Add a row for a new project.
- Change a **Status** cell (e.g. `In Progress`, `Blocked`, `Done`, `On Hold`,
  `Not Started`) — the badge color updates automatically.
- Paste data straight from Excel into the sheet if you prefer.

The public page refreshes automatically every 60 seconds (or click **Refresh**).

## Status colors

| Status keywords | Color |
|---|---|
| Done / Complete / Shipped / Live | 🟢 green |
| In Progress / Active / Ongoing | 🔵 blue |
| On Hold / Pending / Waiting | 🟡 amber |
| Blocked / At Risk / Delayed / Overdue | 🔴 red |
| Anything else (e.g. Not Started) | ⚪ gray |

## Changing the data source

To point the page at a different sheet, edit the `SHEET_ID` (and `GID` for a
different tab) in the `CONFIG` block near the bottom of `index.html`.
