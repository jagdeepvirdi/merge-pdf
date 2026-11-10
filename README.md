# PDF Merge

A standalone, offline-capable web app for merging PDF files. Runs entirely in your browser — no server, no install, no upload. Your files never leave your device.

## Usage

1. Open `index.html` in any modern browser (double-click it, or right-click → Open with → your browser).
2. Add files — drag and drop PDFs onto the drop zone, or click it to browse.
3. For each file, optionally set which pages to include in the box under its name:
   - Leave blank (or type `all`) to include every page.
   - `1-3,5,7-9` includes pages 1 through 3, page 5, and pages 7 through 9.
   - `4` includes just page 4.
4. Reorder files by dragging the `⠿` handle, or using the ↑/↓ buttons. The merged PDF follows this top-to-bottom order.
5. Remove a file with the ✕ button if you no longer need it.
6. Set the output filename (defaults to `merged.pdf`).
7. Click **Merge PDFs**. The combined file downloads automatically once merging finishes.

The page count shown under "Output will contain N pages..." updates live as you edit ranges, and **Merge PDFs** is disabled whenever a range is invalid (e.g. referencing a page beyond the file's length).

## Notes

- Password-protected/encrypted PDFs can't be merged — remove the password first, then retry.
- Corrupt or non-PDF files are flagged in the file list instead of being silently skipped.
- Everything happens client-side using [pdf-lib](https://pdf-lib.js.org/), vendored locally in `vendor/pdf-lib.min.js`, so the app works fully offline with no internet connection required.

## Privacy

Your PDFs are never uploaded, copied or stored. The app makes no network requests, has no backend, and keeps nothing in browser storage. Merging happens in your browser's memory and the result goes straight to your downloads folder.

## Files

```
index.html              the app (open this)
vendor/pdf-lib.min.js    bundled PDF library, keep alongside index.html
```
