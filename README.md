# Toolora — Phase 1

A beginner-friendly static website built with HTML, CSS, and vanilla JavaScript. It has no server, account system, API key, build step, or package installation.

## Run it

1. Download or unzip the `outputs` folder.
2. Open `index.html` in a current version of Chrome, Edge, Firefox, or Safari.
3. Keep an internet connection available so the PDF, QR, and invoice libraries can load from CDN. The site itself does not upload selected files.

For a local web server, open a terminal in this folder and run `python -m http.server 8000`, then visit `http://localhost:8000`. A server is optional for these features.

## Project structure

- `index.html` — homepage, tool forms, and CDN library references
- `styles.css` — responsive layout and visual styles
- `app.js` — browser-side tool behavior
- `toolora-logo.svg` — the Toolora logo in editable vector format

## Included tools

- **PDF Toolkit:** merges PDFs, extracts selected pages to a new PDF, and re-saves a PDF using optimized object streams.
- **Image Toolkit:** uses the browser canvas to resize, compress, and convert images to JPG, PNG, or WebP.
- **Invoice Generator:** editable business and customer details, line items, quantities, rates, tax, automatic totals, and PDF download.
- **QR Code Generator:** website, WhatsApp chat, and Wi-Fi QR codes with PNG download.

## Browser and library notes

- PDF operations use [pdf-lib](https://pdf-lib.js.org/) in the browser. Password-protected/encrypted PDFs may fail to load. Very large files can use substantial memory.
- PDF “Optimize” does not downsample or recompress embedded images. It re-saves PDF structure; it may not reduce size and can make some files larger. A guaranteed high-quality PDF compression service generally requires more advanced processing.
- Image formats depend on browser decoding and canvas encoding support. Animated images become a still image. JPG has no transparency, so transparent pixels are filled white. Image processing happens in memory and very large dimensions may exceed browser memory limits.
- Invoice PDFs use [jsPDF](https://parall.ax/products/jspdf). This starter uses a simple layout and does not provide tax or accounting advice.
- QR generation uses [QRCode.js](https://github.com/davidshimjs/qrcodejs). Wi-Fi passwords and QR contents are processed in the page; anyone who scans a Wi-Fi QR can read its credentials. Use care before sharing it.
- The libraries and web font are loaded from third-party CDNs. They need internet access. No API keys are needed. CDN availability and their URLs are outside Toolora’s control; to run fully offline, download compatible library files and update the script references.
- Client-side processing means the chosen files are not sent to a Toolora backend. Your browser, extensions, or device can still have their own data and security behavior.

## Change the project

Open the folder in a code editor such as Visual Studio Code. Edit the text in `index.html`, the appearance in `styles.css`, and functionality in `app.js`. Refresh the browser to see saved changes.

Libraries loaded from pinned CDN versions:

- pdf-lib 1.17.1
- jsPDF 4.2.1
- qrcodejs 1.0.0
