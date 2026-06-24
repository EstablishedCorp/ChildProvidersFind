# Child Care Finder

A standalone Angular 18 application that finds nearby child care service
providers for any address and plots them on an interactive GIS map.

## Features

- **Address search** — geocodes any address, city, or postal code using the
  free OpenStreetMap **Nominatim** API (no API key required).
- **GIS map** — interactive **Leaflet** map with OpenStreetMap tiles.
- **Provider pins** — every provider is shown as a map pin; the searched
  address is marked with a gold star.
- **Click a pin** → a popup shows the provider's address and full details
  (type, phone, email, age range, hours, rating, distance, availability).
- **Provider list** — a sidebar lists providers sorted by distance; clicking a
  card flies the map to that pin and opens its popup.
- Responsive layout for desktop and mobile.

## Tech stack

- Angular 18 (standalone components)
- Leaflet 1.9 + OpenStreetMap (GIS map & tiles)
- Nominatim (geocoding)

## Run locally

```bash
npm install
npm start
```

Then open http://localhost:4200 and search for an address
(e.g. `350 5th Ave, New York` or `Seattle, WA`).

## Build

```bash
npm run build
```

Output is written to `dist/childcare-finder`.

## Notes

- Provider data is synthesised around the searched location so the demo works
  for any address worldwide. Swap `ChildCareService.buildNearbyProviders` for a
  real provider API/database to make it production-ready.
- Nominatim has a usage policy (max ~1 request/second). For production traffic,
  host your own geocoder or use a commercial provider.
