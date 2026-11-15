# Café Stock Tracker

A single-page stock tracker for a three-outlet café chain (Jurong, Orchard, Tampines).

- Outlet tabs with items grouped by category
- Adjust quantity on hand and reorder level per item, then Save
- Items at or below their reorder level are marked **Low**
- Combined "Order from suppliers" list with a Copy button
- Export PDF of all outlets and the order list

## How it works

`index.html` is the whole app: no build step and no server code. It reads and
writes stock in a Supabase project using the project's publishable key, which
is embedded in the page. Each save is stored as a count dated that day, so
earlier counts are kept as history.

Because the key is in the page and no login is required, anyone who can open
the deployed site can view and change stock levels.

## Deploying to Vercel

1. In Vercel, choose **Add New > Project** and import this repository.
2. Leave **Framework Preset** as "Other" and the build and output settings empty.
3. Press **Deploy**. Vercel serves `index.html` at the site root.

No environment variables or `vercel.json` are needed.

## Running locally

Open `index.html` in a browser, or serve the folder:

```bash
python -m http.server 8765
```
