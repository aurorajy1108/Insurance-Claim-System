# Insurance Claim System (Static Demo)

This is a simple static front-end demo that demonstrates a three-step insurance claim flow (Report → Payment Info → Upload Documents). The app is fully static (HTML/CSS/JS) and does not require a build step.

## Local deployment (recommended)

Serve from the demo folder:

```bash
cd /path/to/Insurance-Claim-System
python3 -m http.server 8000
```

Then open:

```
http://localhost:8000/
```


## Service Worker note

- The demo includes a service worker (`sw.js`) used to return the app's in-memory claim data via a `/claim-data` fetch. The service worker must be served from the same directory scope as the page.
- If you previously visited the demo and the browser registered an incorrect or old service worker, do this in DevTools to avoid conflicts:
    1. Open DevTools → Application (or Storage) → Service Workers.
    2. Unregister any existing service worker(s) for this origin.
    3. Hard-refresh the page (Ctrl/Cmd + Shift + R) so the correct `sw.js` can register.

Note: The app registers `sw.js` using a relative path, so it will work whether you serve from the repo root (subpath) or from inside the demo folder.


## File layout (for reference)

```
Insurance-Claim-System/
├── index.html
├── success.html
├── file-comparison-tool.html
├── sw.js
├── css/
│   └── styles.css
└── js/
        └── app.js
```
