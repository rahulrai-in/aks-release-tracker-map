# AKS Release Tracker Map

A single-page website that visualises [AKS release rollout status](https://releases.aks.azure.com/AKSRelease) on an interactive world map.

## Features

- **Interactive map** — 77 Azure regions plotted on a dark-themed Leaflet/CARTO map
- **Section selector** — Resource Provider, Ubuntu Image, Azure Linux Image, Security Patches, Windows Image
- **Component & version selectors** — drill into any component and any historic release
- **Color-coded markers** — green (latest), amber (in-progress rollout), grey (older version)
- **Click a region** for version, batch, status, and a direct link to the release notes

## Hosting

The site is designed for **GitHub Pages**. Enable Pages on the `main` branch root (`/`).

Release data is refreshed automatically every 6 hours by the [fetch-data](.github/workflows/fetch-data.yml) GitHub Actions workflow, which commits updated JSON to `data/parsed_data.json`.

## Local Development

```bash
python3 -m http.server 8080
# Open http://localhost:8080
```

## Data Source

Live data is fetched from `https://releases.aks.azure.com/parsed_data.json` and stored locally to avoid CORS restrictions.
