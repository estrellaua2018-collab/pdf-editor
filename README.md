# PDF Editor

A PDF editor that runs entirely in the browser. Files never leave your computer.

Open a PDF, then add text, edit existing text, draw, highlight, white-out, insert images, and save the result as a new PDF.

## Run locally

```bash
python3 -m http.server 8765
```

Open http://localhost:8765.

## Tools

| Tool | Key | What it does |
|---|---|---|
| Select | V | Click to select, drag to move, corner handle resizes, Delete removes |
| Text | T | Click anywhere and type (non-Latin text such as Cyrillic works) |
| Edit text | E | Click existing PDF text to cover it and retype it in place |
| Draw | P | Freehand pen |
| Highlight | H | Drag a translucent box |
| White-out | W | Drag a white box to hide content |
| Image | — | Pick a PNG/JPEG, then click to place it |

Ctrl/Cmd+Z undoes, Ctrl/Cmd+S saves `<name>-edited.pdf`.

## Limitations

- "Edit text" and White-out **cover** the original text; it remains in the file underneath. Don't use them to redact sensitive data.
- Added text uses Helvetica (or DejaVu Sans for non-Latin characters), not the PDF's original font.
- Scanned PDFs have no text layer, so "Edit text" can't pick up words there.
- Password-protected PDFs can't be opened.

## Deploy

`render.yaml` deploys this folder as a Render static site.

## Third-party

`vendor/` contains [pdf.js](https://github.com/mozilla/pdf.js) 3.11.174 (Apache-2.0), [pdf-lib](https://github.com/Hopding/pdf-lib) 1.17.1 (MIT), [@pdf-lib/fontkit](https://github.com/Hopding/fontkit) 1.1.1 (MIT) and [DejaVu Sans](https://dejavu-fonts.github.io/) 2.37 (Bitstream Vera / public-domain licence).
