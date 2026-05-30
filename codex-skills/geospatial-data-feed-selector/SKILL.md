---
name: geospatial-data-feed-selector
description: Use when selecting authoritative geospatial, earth-observation, terrain, land-cover, POI, traffic, weather, or boundary data feeds and APIs, including NASA GIBS, Copernicus, Landsat, USGS 3DEP, ESA WorldCover, Dynamic World, OSM, Overture Maps, WZDx, TomTom, HERE, NOAA NWS, ECMWF, geoBoundaries, Natural Earth, and TIGER/Line.
metadata:
  short-description: Select geospatial data feeds
---

# Geospatial Data Feed Selector

Use this skill to recommend data feeds, APIs, update cadences, access patterns, licensing cautions, and production reliability posture for geospatial dashboards.

## Selection Workflow

1. Classify the data need: earth observation, browse imagery, historical remote sensing, terrain, land cover, POIs/context, traffic, weather, or boundaries.
2. Decide whether the dashboard needs live/near-real-time data, periodic versioned releases, or historical analysis.
3. Match the geography: U.S., global, Europe-focused, or publisher-dependent.
4. Separate visualization feeds from analytical data sources.
5. Call out license, procurement, and operational reliability caveats explicitly.
6. Recommend caching, normalization, provenance fields, and fallback behavior for production use.

## High-Confidence Defaults

- Browse imagery: NASA GIBS or Copernicus Data Space Ecosystem.
- Long historical remote sensing: USGS Landsat Collection 2.
- U.S. elevation: USGS 3DEP via The National Map.
- Global elevation: Copernicus DEM.
- Baseline land cover: ESA WorldCover.
- Near-real-time land-cover change: Dynamic World.
- Open POIs and roads: OpenStreetMap, with self-hosted/managed extracts for production.
- Cloud-native place/context layers: Overture Maps.
- U.S. work zones and road restrictions: USDOT WZDx.
- Reliable commercial live traffic: TomTom Traffic API or HERE Traffic API.
- U.S. weather: NOAA National Weather Service API.
- Global forecast model data: ECMWF Open Data.
- Global administrative boundaries: geoBoundaries.
- Low-zoom cartographic context: Natural Earth.
- U.S. legal/statistical geography: U.S. Census TIGER/Line.

## Production Rules

- Do not use public Overpass instances as a mass-market production backend. Self-host, use managed extracts, or cache internally.
- Reconfirm TomTom and HERE pricing, entitlements, quotas, and terms during procurement because commercial traffic terms change.
- Treat Dynamic World as a probabilistic model product, not a legal land-use authority.
- Match boundary data to the decision: use Natural Earth for cartography, geoBoundaries for open global admin boundaries, and TIGER/Line for U.S. legal/statistical geography.
- Keep source, license, timestamp, update cadence, freshness, and confidence/provenance in the normalized data model.
- Use STAC for asset discovery when feeds involve imagery, COGs, scenes, or earth-observation assets.
- Put tiles, immutable releases, and heavy rasters behind CDN/cache policies.

## References

Read `references/feed-matrix.md` for the detailed feed matrix and caveats.
