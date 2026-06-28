# 3D Music Flower

A browser-based 3D music flower built with Three.js. It renders a high-density powder-like bouquet, then blooms from a seed state when you add local audio files. The flower breathes, shimmers, and reveals subtle mathematical motion in response to the music spectrum.

## Features

- Pure front-end single-file project; open `index.html` to run it
- Three.js particle system for petals, pistils, stems, leaves, and dust
- Upload or drag and drop local audio files
- Multi-track playlist playback
- Audio spectrum drives flower scaling, particle shimmer, and hidden geometry paths
- Adaptive particle budget for better mobile and low-power performance
- No backend required; ready for GitHub Pages, Vercel, Netlify, or any static host

## Preview

<img src="./assets/preview.png" alt="3D Music Flower preview" width="100%">

The page first shows a still 3D bouquet. After you choose or drop in music, the bouquet folds back into a seed-like state and grows again with the track.

## Quick Start

Open the file directly:

```bash
open index.html
```

If your browser is strict about local file permissions, start a small local server:

```bash
python3 -m http.server 8080
```

Then visit:

```text
http://localhost:8080
```

## Usage

1. Click `Having a moment` in the lower-left control panel to choose one or more audio files.
2. You can also drag audio files directly onto the page.
3. Use the play button to pause or resume playback.
4. When multiple tracks are selected, they play in the order you chose them.

Audio files are read only by your local browser. They are not uploaded to a server.

## Tech Stack

- HTML / CSS / JavaScript
- Three.js r128
- Web Audio API
- CanvasTexture particle sprites

## Deploy

### GitHub Pages

1. Push the repository to GitHub.
2. Open `Settings -> Pages`.
3. Choose the main branch and the repository root as the source.
4. Save and wait for GitHub Pages to publish the site.

### Static Hosting

There is no build step. Upload `index.html` to any static hosting provider.

## Customization

Useful parameters live in `index.html`:

- `particleBudget`: maximum particle count
- `bloomDefs`: flower positions, scale, tilt, and reveal timing
- `stemDefs`: stem positions and curvature
- `shapes`: hidden particle geometry modes
- `material.size`: base particle size

## Notes

The page loads Three.js from a CDN. For offline use, download Three.js locally and update the script reference.
