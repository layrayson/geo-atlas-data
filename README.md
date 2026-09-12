# geo-atlas-data

Mirrored, normalized GeoJSON boundary data for [@geo-atlas/core](https://github.com/layrayson/geo-atlas) — served via [jsDelivr](https://www.jsdelivr.com/) as a CDN, so browser apps can fetch boundary data without hitting geoBoundaries.org's Git-LFS CORS issue directly (see [geo-atlas/spikes/04-browser-cors](https://github.com/layrayson/geo-atlas/tree/main/spikes/04-browser-cors) for why that's needed).

Each file has already been through `@geo-atlas/core`'s validation and ring-winding normalization — it's ready to render as-is, no further processing needed.

## Usage

```
https://cdn.jsdelivr.net/gh/layrayson/geo-atlas-data@main/data/<ISO3>/admin1-simplified.geojson
```

See [manifest.json](./manifest.json) for exactly which countries are mirrored, their source, and license.

## Coverage

Mirrors 197 of 249 ISO 3166-1 countries/territories at admin1 level, simplified resolution. The 52 not mirrored are dependent territories, microstates, and a few disputed entities that geoBoundaries.org doesn't publish ADM1 (state/province-level) data for — e.g. Bermuda, Hong Kong, Puerto Rico, Vatican City, Antarctica. See `manifest.json` for the exact list, or re-run `scripts/build-mirror.ts` in the main repo to regenerate.

## License

This repo redistributes upstream data unmodified in content (only re-wound for correct rendering) under each country's own license — see `manifest.json` for the specific license and source per country. No blanket license applies to the data itself; attribution requirements follow whatever each entry specifies (all are open licenses: CC BY variants, Public Domain, or Etalab Open License 2.0 — none restrict redistribution).

This repository's own generation code (not the mirrored data) is MIT licensed.
