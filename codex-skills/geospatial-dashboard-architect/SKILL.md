---
name: geospatial-dashboard-architect
description: Use when designing, scoping, or choosing an open-source geospatial dashboard stack, including MapLibre, deck.gl, ECharts, Leaflet, OpenLayers, CesiumJS, kepler.gl, TerriaJS, MapStore2, GeoNode, Grafana Geomap, Superset, STAC, OGC APIs, PMTiles, COGs, and TiTiler.
metadata:
  short-description: Choose geospatial dashboard stacks
---

# Geospatial Dashboard Architect

Use this skill to turn geospatial dashboard requirements into a concrete architecture, stack recommendation, delivery bundle, and implementation plan.

## Default Recommendation

For most greenfield custom dashboards, start with:

- MapLibre GL JS for the base map and open vector-tile rendering.
- deck.gl for dense analytical overlays, trajectories, aggregations, and custom GPU layers.
- Apache ECharts for linked non-map charts, KPIs, brushing, and summary panels.
- URL-addressable state for map view, time, filters, selected layers, and selected entities.
- STAC for earth-observation asset catalogs.
- OGC API Features for queryable vectors.
- OGC API Tiles or PMTiles for tile delivery.
- COG + TiTiler for dynamic raster tiling, styling, and subsetting.

Use a platform framework instead when the complexity lives in catalogs, publishing, governance, permissions, metadata, or workbench workflows.

## Triage Questions

Ask only the questions needed to classify the project:

1. Is the primary experience custom analysis, a catalog/workbench portal, operational telemetry, BI, or 3D terrain/digital twin?
2. Are users analysts, public visitors, operations teams, publishers, or administrators?
3. Is the dataset mostly vectors, rasters/earth observation, real-time feeds, 3D assets, or mixed?
4. Does the project need auth, role-based access, metadata publishing, saved views, or approval workflows?
5. Are licensing, procurement, public accessibility, or government standards first-order constraints?

## Stack Selection Rules

- Choose MapLibre GL JS when the project needs a modern open 2D vector-map foundation with maximum UI control.
- Add deck.gl when the dashboard must render dense points, paths, hex bins, custom layers, or GPU-scale analytical overlays.
- Use Apache ECharts when linked charts around the map are central.
- Choose Leaflet for lightweight public maps, embeds, and modest GeoJSON/tile workloads.
- Choose OpenLayers when OGC standards, projections, editing, or advanced GIS semantics are more important than minimalism.
- Choose CesiumJS when 3D globe, terrain, 3D Tiles, city-scale digital twins, or high-precision WGS84 visualization are central.
- Choose kepler.gl for rapid analyst-facing exploration, stakeholder demos, and embedded exploratory modules.
- Choose TerriaJS/TerriaMap for catalog-centric portals, layer workbenches, live-data digital twins, and shareable map state.
- Choose MapStore2 or GeoNode when the product needs SDI/content management, metadata, permissions, OGC interoperability, dashboards, stories, or publishing workflows.
- Choose Grafana Geomap for real-time operational telemetry when data already lives in observability or time-series systems.
- Choose Apache Superset when the dashboard needs SQL, semantic metrics, BI workflows, and non-map analytics around geospatial views.

## Bundle Selection

Lightweight:

- MapLibre GL JS, Apache ECharts, PMTiles, static hosting or thin API layer.
- Best for public dashboards, policy portals, NGO tools, and modest internal tools.
- Typical effort: 2-4 weeks for one strong engineer; 4-6 weeks with design and accessibility hardening.

Full-featured:

- MapLibre GL JS, deck.gl, ECharts, STAC, OGC API Features/Tiles, TiTiler, URL state, auth, CDN caching.
- Best for analytical dashboards, climate, mobility, infrastructure, and regional monitoring.
- Typical effort: 6-10 weeks for a small team, longer with bespoke design systems or ingestion pipelines.

Enterprise-ready:

- TerriaMap or MapStore2/GeoNode, standards-based APIs, metadata/catalog governance, role access, saved views, Grafana or Superset as needed.
- Best for agencies, utilities, NGOs with approval workflows, digital twins, published portals, and multi-team ownership.
- Typical effort: 10-16 weeks for an initial production baseline, longer with identity, metadata, and audit requirements.

## UX Requirements

Carry these patterns into recommendations and implementation plans:

- Layer workbench with clear legends, source/provenance, visibility, opacity, and ordering.
- Time slider or date browser for temporal data.
- Keyboard-operable map controls, panels, popups, filters, and modals.
- URL-shareable app state and optionally saved named views.
- Accessible summaries for map-only insights.
- Responsive layouts that preserve core analysis on mobile.
- Reduced-motion support for animated timelines.
- Aggressive HTTP caching and CDN policies for tiles and static assets.

## References

Read `references/tool-matrix.md` when comparing libraries, platforms, and starter bundles.
