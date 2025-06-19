# GPS Coordinate Finder

A simple web app for interactively finding and copying latitude/longitude coordinates on a map. Built with Leaflet.js and OpenStreetMap tiles. No backend required.

![image](https://github.com/user-attachments/assets/92612c70-125f-4789-ba3c-5a99397c54c2)

## Features

- 🌍 Interactive map with draggable marker
- 📍 Auto-locate your device (with browser geolocation)
- 🖱️ Copy coordinates with one click
- 🗺️ Uses OpenStreetMap tiles (no API key needed)
- ⚡ Fast, responsive, and works offline after first load

## Usage

1. **Download or clone this repository.**
2. Make sure you have Python installed (for running a local server).
3. Open a terminal in the project directory and run:
   ```sh
   python -m http.server 8000
   ```
4. Open your browser and go to:
   [http://localhost:8000/index.html](http://localhost:8000/index.html)

## How It Works
- Drag the marker or move the map to update the coordinates.
- Click the "Copy" button to copy the current coordinates to your clipboard.
- If your browser allows, the map will attempt to center on your current location.

## Troubleshooting
- **Geolocation errors:**
  - If you see a geolocation error, make sure your browser allows location access and you're using HTTPS or localhost.
  - Some browsers block geolocation on plain HTTP (except for localhost).
- **Map tile errors (400 Bad Request):**
  - This app uses zoom levels supported by OpenStreetMap (up to 19). If you see tile errors, refresh or zoom out.
- **Copy button not working:**
  - Clipboard access may require HTTPS or user interaction in some browsers.

## Customization
- To change the default map center, edit the marker's initial coordinates in the HTML file.
- You can style the map and panel by editing the CSS in the `<style>` block.

## Publishing on Netlify

To make your map publicly accessible, you can deploy it for free using Netlify:

### 1. Rename Your HTML File
- use`index.html` for the map file
- Make sure all resources (CSS, JS, images) are referenced with relative paths.

### 2. Prepare Your Project Folder
- Your folder should look like:
  ```
  /projects
    ├─ index.html
    ├─ README.md
    └─ (any other assets)
  ```

### 3. Deploy to Netlify
- Go to [Netlify Drop](https://app.netlify.com/drop).
- Drag and drop your project folder (containing `index.html`) into the window.
- Netlify will provide a public URL instantly.

**Optional: Continuous Deployment**
- Push your folder to GitHub.
- On Netlify, click "Add new site" > "Import an existing project" and connect your repo.
- Every push to your repo will auto-deploy your site.

## Contribution
Pull requests are welcome! Please open an issue first to discuss major changes.

## Wix integration

```
// in your PAGE code (not Section code)
import { getCurrentGeolocation } from 'wix-window';

$w.onReady(() => {
  const htmlComp = $w('#html1');

  // Request a high-accuracy GPS fix in the secure parent context
  getCurrentGeolocation({ enableHighAccuracy: true, timeout: 10000 })
    .then(({ coords }) => {
      // Send the coords into the iframe
      htmlComp.postMessage({ coords }, '*');
    })
    .catch(err => {
      console.warn('Geolocation error or denied:', err);
      // Fallback to manual mode
      htmlComp.postMessage({ coords: null }, '*');
    });
});
```

## License
[MIT](LICENSE)
