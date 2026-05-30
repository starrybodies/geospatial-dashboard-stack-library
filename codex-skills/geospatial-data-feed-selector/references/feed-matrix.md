# Geospatial Data Feed Matrix

## Earth Observation, Terrain, And Land Use

| Source | Category | Gives you | Update pattern | Access | License/cost | Notes |
|---|---|---|---|---|---|---|
| NASA GIBS | Satellite browse imagery | Hazards, atmosphere, ocean, cryosphere, and land imagery | Many products within 3-5 hours; daily and historical layers | WMTS, WMS, TWMS, TMS/XYZ | Free public | Optimized for responsive visualization and temporal overlays, not raw-scene analytics |
| Copernicus Data Space Ecosystem | Satellite imagery and EO access | Sentinel archives and Copernicus ecosystem data | Ongoing ingestion | STAC, OData, S3, Sentinel Hub, openEO | Free/open ecosystem | Strong primary source for European EO workflows and API discovery |
| USGS Landsat Collection 2 | Long time-series imagery | Reprocessed multispectral archive with improved geolocation and cloud access | Updated as scenes are processed | USGS access and STAC-oriented discovery | Free public | Best long-run baseline for historical analysis |
| USGS 3DEP / The National Map | Elevation | U.S. elevation products | Periodic staged product refreshes | TNMAccess API and downloads | Free public | U.S.-authoritative elevation backbone |
| Copernicus DEM | Elevation | Global DEM products including GLO-30 and GLO-90 | Versioned dataset | Download and Process API pathways | Copernicus terms | Strong global DEM option |
| ESA WorldCover | Land cover | Global 10 m land-cover maps | Versioned annual releases | Download and cloud mirrors | CC BY 4.0, free | Convenient authoritative categorical baseline |
| Dynamic World | Near-real-time land cover | 10 m global land-use/land-cover predictions from Sentinel-2 | Near-real-time, tied to Sentinel-2 revisit | Google Earth Engine and project tools | Open; verify downstream terms | Probabilistic model product, not legal authority |

## Operational And Contextual Feeds

| Source | Category | Gives you | Update pattern | Access | License/cost | Notes |
|---|---|---|---|---|---|---|
| OpenStreetMap + Overpass / diffs | POIs, roads, context | Roads, amenities, POIs, surface context | Minutely/hourly/daily diffs; Overpass lag varies | Overpass, planet files, replication diffs | ODbL | Public Overpass is not a production SLA |
| Overture Maps | POIs and boundaries | Places, divisions, transport, buildings, addresses | Monthly releases | GeoParquet and cloud catalogs | Mostly CDLA Permissive v2, with source exceptions | Strong cloud-native schemas |
| USDOT WZDx | Traffic and road operations | Work zones and road restrictions | Publisher-dependent, often near-real-time | Feed registry and JSON spec | Feed licensing varies | Best U.S. work-zone source |
| TomTom Traffic API | Traffic | Real-time traffic flow and incidents | Flow updated every minute | REST and tile APIs | Commercial | Reconfirm pricing and quotas |
| HERE Traffic API | Traffic | Real-time traffic flow and incidents | Real-time | REST API | Commercial | Strong enterprise option |
| NOAA NWS API | Weather | U.S. forecasts, alerts, observations | Product lifecycle based | JSON-LD REST | Free public | U.S.-authoritative, U.S.-centric |
| ECMWF Open Data | Weather | Global IFS and AIFS forecast outputs | Four runs per day at 00/06/12/18 UTC | Downloads and cloud mirrors | CC BY 4.0 | High-confidence global forecast model feed |
| geoBoundaries | Boundaries | Global administrative boundaries | Versioned periodic updates | API and downloads | CC BY 4.0 | Useful standardized open boundaries; API uptime not guaranteed |
| Natural Earth | Boundaries/context | Small-scale global physical and cultural data | Irregular versioned releases | Direct download | Public domain | Cartographic context, not legal authority |
| U.S. Census TIGER/Line | Boundaries/context | U.S. legal/statistical boundaries, roads, hydrography | Annual releases | Shapefile downloads | Free public | Correct U.S. legal/statistical geography source |

## Tiered Feed Portfolio

For production dashboards, treat feeds as a portfolio:

- Use NASA GIBS or Copernicus for browse imagery.
- Use Landsat for longitudinal analysis.
- Use OSM or Overture for places, roads, and context.
- Use at least one authoritative weather feed matched to geography.
- Use one boundary source matched to legal or cartographic requirement.
- Add traffic from WZDx for U.S. work zones or TomTom/HERE for reliable commercial live traffic.

## Normalization Fields

Recommended fields for internal catalog records:

- source_name
- source_url
- source_category
- license
- license_notes
- update_frequency
- geography
- access_method
- freshness_timestamp
- provenance
- confidence_or_model_notes
- cache_policy
- production_caveats
