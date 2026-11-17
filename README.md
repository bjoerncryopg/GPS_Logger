# GPS Logger

A lightweight, responsive, browser-based GPS coordinate viewer.

## Features

- Requests the current device location when the page opens (the browser asks the visitor for permission).
- Displays latitude, longitude, horizontal accuracy, and the last update time.
- Keeps the position updated while the page remains open.
- Allows the visitor to request a fresh position, copy the coordinate pair, or open the position in OpenStreetMap.
- Uses the browser Geolocation API only. No account, backend, analytics, external JavaScript dependencies, or location storage.

## Run locally

Serve this directory from localhost. For example:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000. Browsers treat localhost as a secure context for geolocation.

## Deploy with GitHub Pages

1. Open the repository's **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select the `main` branch and the `/ (root)` folder after the implementation has been merged into `main`.
4. Save and wait for GitHub Pages to publish the site.

Use the HTTPS Pages URL. Browser geolocation is generally available only in secure contexts (HTTPS or localhost).

## Privacy and limitations

- The visitor must grant location permission in the browser.
- Accuracy depends on the device, available GPS/network signals, and environmental conditions.
- The page does not send or persist coordinates. The OpenStreetMap link is opened only when the visitor selects **Auf Karte öffnen**.
- If permission is denied, location is unavailable, the request times out, or the page is not served securely, the UI explains the issue and provides a retry action.
