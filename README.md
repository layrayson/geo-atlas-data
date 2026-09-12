# geo-atlas-data

Mirrored, normalized GeoJSON boundary data for [@geo-atlas/core](https://github.com/layrayson/geo-atlas) — served via [jsDelivr](https://www.jsdelivr.com/) as a CDN, so browser apps can fetch boundary data without hitting geoBoundaries.org's Git-LFS CORS issue directly (see [geo-atlas/spikes/04-browser-cors](https://github.com/layrayson/geo-atlas/tree/main/spikes/04-browser-cors) for why that's needed).

Each file has already been through `@geo-atlas/core`'s validation and ring-winding normalization — it's ready to render as-is, no further processing needed.

## Usage

```
https://cdn.jsdelivr.net/gh/layrayson/geo-atlas-data@main/data/<ISO3>/admin1-simplified.geojson
```

See [manifest.json](./manifest.json) for exactly which countries are mirrored, their source, and license.

## Coverage

Currently mirrors the 10 countries validated in `@geo-atlas/core`'s spike 01 (admin1 level, simplified resolution): NGA, KEN, GBR, USA, IND, BRA, CHN, ZAF, AUS, FRA. More countries can be added by re-running `scripts/build-mirror.ts` in the main repo.

## License

This repo redistributes upstream data unmodified in content (only re-wound for correct rendering) under each country's own license — see `manifest.json` for the specific license and source per country. No blanket license applies to the data itself; attribution requirements follow whatever each entry specifies (all are open licenses: CC BY variants, Public Domain, or Etalab Open License 2.0 — none restrict redistribution).

This repository's own generation code (not the mirrored data) is MIT licensed.
