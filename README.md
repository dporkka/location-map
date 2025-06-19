# GPS Coordinate Finder Map

A simple web app for interactively finding and copying latitude/longitude coordinates on a map. Built with Leaflet.js and OpenStreetMap tiles. No backend required.

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

## Contribution
Pull requests are welcome! Please open an issue first to discuss major changes.

## License
[MIT](LICENSE)
