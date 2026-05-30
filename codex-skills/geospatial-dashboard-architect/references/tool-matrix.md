# Geospatial Dashboard Tool Matrix

## Comparative Scores

Scores use a 1-5 scale for UX quality, performance, customization, and ease of integration.

| Tool | UX | Performance | Customization | Integration | Best fit |
|---|---:|---:|---:|---:|---|
| MapLibre GL JS | 4 | 5 | 5 | 4 | Modern 2D web maps with open vector tiles |
| Leaflet | 4 | 3 | 4 | 5 | Lightweight public maps and simple dashboards |
| OpenLayers | 3 | 4 | 5 | 3 | Standards-heavy GIS and advanced 2D interactions |
| deck.gl | 4 | 5 | 5 | 3 | Dense analytical overlays and custom GPU visualization |
| kepler.gl | 5 | 4 | 3 | 4 | Analyst-facing exploration and rapid geospatial UX |
| CesiumJS | 4 | 4 | 4 | 3 | 3D globe, digital twin, and terrain-heavy experiences |
| TerriaJS | 5 | 4 | 4 | 3 | Catalog/workbench digital twins and policy portals |
| Apache ECharts | 4 | 4 | 4 | 4 | Linked charts around the map |

## Foundational Libraries

MapLibre GL JS:
Open WebGL map engine for vector tiles and MapLibre Style Spec. Strong default for React/TypeScript apps, PMTiles, deck.gl overlays, custom controls, and open licensing.

Leaflet:
Small and ergonomic 2D map library. Best for lightweight public dashboards, embeds, modest GeoJSON, and tile workloads. Avoid for very large WebGL-heavy datasets or 3D.

OpenLayers:
Feature-rich 2D GIS toolkit. Strong for OGC sources, projections, editing, controls, and GIS semantics. Expect a larger API surface.

CesiumJS:
3D globe and high-precision geospatial engine. Use for terrain, 3D Tiles, city-scale digital twins, and globe UX. Usually too heavy for 2D-only dashboards.

deck.gl:
GPU analytical layer framework for million-scale rendering, trajectories, hex bins, aggregation, and custom shaders. Pair with MapLibre for most custom analytical dashboards.

kepler.gl:
Opinionated large-scale geospatial exploration app/framework. Excellent filters, split maps, 2D/3D workflows, and analyst UX. Less natural for deeply bespoke UI.

TerriaJS/TerriaMap:
Catalog-driven portal and digital-twin framework with workbench, 2D/3D, URL state, and live data. Use when users browse, compare, and share layers.

Apache ECharts:
Dashboard charting sidecar. Use for linked charts, summaries, KPI panels, brushing, progressive rendering, and non-map analysis.

## Platform Implementations

NASA Worldview:
Best public reference for temporal earth-observation dashboards. Study its layer catalog, date browsing, polar/geostationary views, global search, and shareable state.

TerriaMap:
Best starter for full geospatial portals or digital twins. Built on TerriaJS with CesiumJS for 3D and Leaflet for 2D.

MapStore2:
Strong WebGIS framework when maps, dashboards, stories, timelines, permissions, and OGC interoperability are all needed. React/Redux frontend and Java backend.

GeoNode:
Best SDI/geospatial CMS base when metadata, publishing, styling, documents, permissions, catalogs, dashboards, and GeoStories matter. Django, GeoServer, and pyCSW.

Grafana Geomap:
Best operational geospatial dashboard pattern for real-time telemetry and observability data. Includes layered maps, heatmaps, network paths, and keyboard map navigation.

Apache Superset:
Best BI companion when SQL, semantic metrics, dashboards, security roles, caching, and non-map analytics are central.

## Standards And Delivery

Use STAC for asset catalogs and earth-observation discovery.

Use OGC API Features for searchable and filterable vector features.

Use OGC API Tiles or PMTiles for tiled delivery.

Use COG + TiTiler for dynamic raster tiling, styling, and subsetting.

Separate feature delivery from raster delivery. Keep provenance, caching policy, and licensing visible in the data model.
