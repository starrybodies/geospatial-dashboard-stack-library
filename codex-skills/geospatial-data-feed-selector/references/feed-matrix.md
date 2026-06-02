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
| NASA Earthdata CMR | EO catalog | NASA collections and granules across Earth science archives | Metadata changes as collections/granules are published | Search API and STAC-oriented discovery | Free public | Discovery layer; downstream access depends on product and provider |
| Microsoft Planetary Computer | Cloud EO catalog | STAC catalog and cloud-hosted open planetary datasets | Dataset-dependent | STAC API and cloud-native assets | Mixed open datasets | Strong for prototyping and COG/STAC workflows |
| AWS Registry of Open Data | Cloud data catalog | Public datasets on AWS, including many EO and geospatial collections | Dataset-dependent | S3/cloud resources and registry metadata | Mixed open datasets | Licenses, egress, and compute costs vary by dataset |
| GEBCO | Bathymetry | Global gridded bathymetry and land/ocean elevation | Versioned releases | Downloads and Web Map Service | GEBCO terms | Baseline for ocean and marine terrain context |
| WorldPop | Population | Gridded population and covariate data | Dataset-dependent | Downloads, WOPR REST API, STAC catalog | Creative Commons; verify dataset terms | Modeled population estimates require vintage and uncertainty care |
| JRC GHSL | Settlement | Built-up, population, and settlement-model layers | Versioned releases | Downloads and data tools | Open/free reuse; cite terms | Strong for urbanization, exposure, and settlement dashboards |

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
| NASA FIRMS | Hazards | Near-real-time MODIS and VIIRS active fire and thermal anomaly data | Near-real-time | Fire maps and API access | Free public | Thermal anomalies need interpretation and sensor-timing context |
| NOAA Climate Data Online | Climate | Historical weather and climate observations, stations, datasets, data types | Archive/product-dependent | NOAA/NCEI API | Free public | Historical climate archive, not live operational weather |
| NOAA nowCOAST | Coastal weather/hazards | Coastal observations, forecasts, warnings, and model guidance | Real-time/near-real-time product dependent | Map services | Free public | Coastal and marine focus |
| FEMA NFHL | Flood hazards | U.S. regulatory flood hazard zones and flood map products | Effective map/product updates | GIS services and Map Service Center downloads | Free public | Regulatory use requires effective-date and accuracy review |
| USGS 3DHP / NHD | Hydrology | U.S. hydrography, watersheds, and surface-water networks | Product transition and staged updates | USGS downloads and services | Free public | Distinguish legacy NHD/WBD/NHDPlus HR from 3DHP products |
| USGS PAD-US | Protected areas | U.S. public, protected, conservation, and public-access lands | Versioned releases | Data downloads | Free public | Version changes can reflect inventory improvements |
| EPA Envirofacts / DMAP | Environment | Environmental facility, permit, compliance, and monitoring datasets | Program-dependent | REST, GraphQL, and downloads | Free public | Deep schemas and program terms require modeling time |
| OpenAQ | Air quality | Global air-quality measurements and latest observations | Source-dependent | REST/JSON API | Open data | Coverage and QA vary by data source |
| GBIF | Biodiversity | Species occurrence and taxonomic data | Continuous ingestion | APIs and downloads | Mixed open data | Presence-only biodiversity data has observation bias |
| HydroSHEDS | Hydrology | Global basins, rivers, lakes, drainage, and hydrologic attributes | Versioned releases | Downloads | Free for non-commercial; verify terms | Derived products inherit DEM and conditioning limitations |
| Humanitarian Data Exchange | Humanitarian catalog | Crisis, admin-boundary, indicator, and operational datasets | Publisher-dependent | CKAN-style API and downloads | Mixed open datasets | Dataset quality and licensing vary by publisher |
| GTFS Schedule / Realtime | Transit standard | Transit schedules, stops, trips, vehicle positions, trip updates, and service alerts | Agency/feed-dependent | Open feed specifications and agency feeds | Open standard | Feed quality and realtime availability vary by agency |
| OpenAddresses | Addresses | Aggregated open address datasets from many jurisdictions | Source-dependent | Downloads | Mixed open data | Coverage, freshness, and license vary by source |
| GeoPlatform NGDA STAC | Federal catalog | U.S. National Geospatial Data Assets across federal agencies | Catalog-dependent | STAC catalog | Mixed public datasets | Metadata and downstream data access vary by agency |

## Tiered Feed Portfolio

For production dashboards, treat feeds as a portfolio:

- Use NASA GIBS or Copernicus for browse imagery.
- Use Landsat for longitudinal analysis.
- Use OSM or Overture for places, roads, and context.
- Use at least one authoritative weather feed matched to geography.
- Use one boundary source matched to legal or cartographic requirement.
- Add traffic from WZDx for U.S. work zones or TomTom/HERE for reliable commercial live traffic.
- Add hazard, hydrology, population, biodiversity, environmental, and humanitarian feeds when the dashboard must explain exposure or operational context.

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
