# Marine Spatial Planning (MSP) Tanzania — Processed Spatial Data

[![Data Format: OGC GeoPackage](https://img.shields.io/badge/Format-OGC%20GeoPackage%20(.gpkg)-blue.svg)](https://www.geopackage.org/)
[![CRS: EPSG 4326 / 32737](https://img.shields.io/badge/CRS-EPSG%3A4326%20%7C%20EPSG%3A32737-green.svg)](https://epsg.io/4326)
[![Project: MSP Tanzania](https://img.shields.io/badge/Project-MSP%20Tanzania%20(Deliverable%203)-teal.svg)](#)
[![Organization: The Nature Conservancy](https://img.shields.io/badge/Organization-The%20Nature%20Conservancy%20(TNC)-007348.svg)](https://www.nature.org/)

---

## 1. Executive Summary & Overview

This repository contains the **harmonized, quality-controlled, and analysis-ready spatial datasets** compiled for **Deliverable 3: Ecological Assessment and Human-Use Mapping** under the **Marine Spatial Planning (MSP) Initiative for the United Republic of Tanzania**, led by **The Nature Conservancy (TNC)** in collaboration with national marine authorities, research bodies, and stakeholders.

The objective of this processed data repository is to provide an authoritative, standardized geospatial baseline spanning Tanzania’s coastal waters, Exclusive Economic Zone (EEZ), and Extended Continental Shelf (ECS). These layers inform multi-objective ocean zoning, ecological sensitivity evaluations, blue economy planning, and conflict-mitigation between competing human uses and marine biodiversity conservation.

---

## 2. Spatial Reference System & Data Standards

All datasets in this directory have been cleaned, topologically verified, and converted into open standard **OGC GeoPackage (`.gpkg`)** containers.

| Parameter | Standard / Specification | Notes |
| :--- | :--- | :--- |
| **Primary Geographic CRS** | **EPSG:4326** (`WGS 84`) | Default coordinate system for general interoperability and global GIS integration. |
| **Primary Projected CRS** | **EPSG:32737** (`WGS 84 / UTM Zone 37S`) | Recommended for distance calculations, buffering, surface area estimations, and spatial modeling along the Tanzanian coast. |
| **Storage Format** | **OGC GeoPackage (`.gpkg`)** | Self-contained, SQLite-based open format supporting vector geometries, spatial indexing (R-Tree), and attribute tables. |
| **Encoding** | **UTF-8** | Attribute tables standardized with clean, descriptive English column nomenclature. |
| **Spatial Extent** | United Republic of Tanzania Maritime Domain | Mainland coast, Zanzibar Archipelago (Unguja and Pemba), Mafia Island, Territorial Sea (12 NM), EEZ (200 NM), and Extended Continental Shelf. |

---

## 3. Directory Layout & Layer Inventory

```text
02_PROCESSED_DATA/
├── eez_split.gpkg
├── maritime_boundaries_cleaned.gpkg
├── ECOLOGICAL_PROCESSED/
│   ├── cfmas.gpkg
│   ├── coral_monitoring_points.gpkg
│   ├── coral_reef_monitoring_zones.gpkg
│   ├── mpa_mca_marine_reserves.gpkg
│   ├── Coral_Reefs/
│   ├── Mangroves/
│   ├── Marine_Fauna/
│   ├── Seagrass/
│   └── Other/
├── FISHERIES_PROCESSED/
│   ├── cfmas_mainland_pemba.gpkg
│   ├── cfmas_tz.gpkg
│   ├── fpm3.gpkg
│   ├── landing_sites.gpkg
│   └── Aquaculture/
├── SOCIOECONOMIC_PROCESSED/
│   ├── Energy_and_Infrastructure/
│   ├── Human_Use_Infrastructure/
│   ├── Shipping_and_Ports/
│   ├── Tourism_Summary/
│   └── Other/
├── SPATIAL_PROCESSED/
│   ├── coastal_districts.gpkg
│   ├── islands_marine.gpkg
│   ├── marine_zones.gpkg
│   └── maritime_boundaries_*.gpkg
├── OCEANOGRAPHIC_PROCESSED/
└── INTEGRATED_DATASETS/
```

---

### 3.1. Maritime Boundaries & Spatial Baselines (`SPATIAL_PROCESSED/` & Root)

Authoritative jurisdictional delineations, administrative districts, islands, and planning boundaries:

| File Name | Location | Geometry | Description |
| :--- | :--- | :--- | :--- |
| `eez_split.gpkg` | Root | Polygon | Sector-divided Tanzanian Exclusive Economic Zone for regional zoning and spatial allocation. |
| `maritime_boundaries_cleaned.gpkg` | Root | Multilinestring / Polygon | Harmonized maritime boundary lines and jurisdictional areas. |
| `coastal_districts.gpkg` | `SPATIAL_PROCESSED/` | MultiPolygon | Coastal administrative districts across mainland Tanzania and Zanzibar. |
| `islands_marine.gpkg` | `SPATIAL_PROCESSED/` | MultiPolygon | Marine islands, islets, and cays within Tanzania's territorial waters. |
| `marine_zones.gpkg` | `SPATIAL_PROCESSED/` | MultiPolygon | Marine management planning zones and classification units. |
| `maritime_boundaries_12nm.gpkg` | `SPATIAL_PROCESSED/` | MultiPolygon | Territorial Sea limit (12 nautical miles from baseline). |
| `maritime_boundaries_eez.gpkg` | `SPATIAL_PROCESSED/` | MultiPolygon | Tanzania's 200 nautical mile Exclusive Economic Zone polygon. |
| `maritime_boundaries_eez_line.gpkg` | `SPATIAL_PROCESSED/` | MultiLineString | Outer boundary line of the 200 NM Exclusive Economic Zone. |
| `maritime_boundaries_extended_continental_shelf.gpkg` | `SPATIAL_PROCESSED/` | MultiPolygon | Delineation of the Extended Continental Shelf claim area under UNCLOS. |
| `maritime_boundaries_internal_waters.gpkg` | `SPATIAL_PROCESSED/` | MultiPolygon | Internal waters baseline and enclosed bays/estuaries. |
| `maritime_ecs.gpkg` | `SPATIAL_PROCESSED/` | MultiPolygon | Extended Continental Shelf spatial boundaries. |

---

### 3.2. Ecological Data (`ECOLOGICAL_PROCESSED/`)

Critical marine and coastal habitats, biophysical monitoring, and charismatic/endangered megafauna:

#### Coral Reefs (`Coral_Reefs/`)
- `coral_reefs.gpkg`: Shallow and fringing coral reef polygon extents.
- `coral_reefs_line.gpkg`: Linear reef crests and outer barrier delineations.
- `coral_cover_points.gpkg`: Quantitative survey points with benthic percentage cover records.
- `coral_monitoring_points.gpkg`: National long-term coral monitoring observation stations.
- `coral_reef_monitoring_zones.gpkg`: Standardized regional monitoring zones (e.g., North, Central, South, Zanzibar).
- `gistar_coral_hotspot.gpkg`: Spatial hotspot analysis ($G_i^*$ statistic) highlighting significant clusters of high coral resilience/cover.
- `mma.gpkg`: Marine Managed Areas designated for reef conservation.

#### Mangroves & Seagrass (`Mangroves/` & `Seagrass/`)
- `Mangroves/mangrove_forest.gpkg`: Mangrove forest spatial coverages along estuaries, deltas (e.g., Rufiji), and coastal lagoons.
- `Seagrass/gistar_seagrass_hotspot.gpkg`: Spatial clusters and critical hotspots ($G_i^*$) of high seagrass bed densities.

#### Marine Fauna (`Marine_Fauna/`)
- `dolphin_sites.gpkg`: Dolphin foraging, nursery, and encounter locations (e.g., Menai Bay, Kizimkazi).
- `dugong_sighting_sites.gpkg`: Historic and recent sightings of dugongs (*Dugong dugon*) along the Rufiji–Kilwa seascape.
- `humpbackwhales_sightings.gpkg` & `whale_sightings.gpkg`: Cetacean migratory corridor and calving encounter points.
- `sea_turtle_nesting_ground_points.gpkg`: Confirmed nesting beaches and index sites for green, hawksbill, and olive ridley turtles.
- `shark_sites.gpkg`: Whale shark feeding aggregations (e.g., Mafia Island) and pelagic shark sighting sites.
- `seahorse_points.gpkg`: Syngnathid observation records in sheltered bays and seagrass flats.

#### Protected Areas & Benthic Classifications (`Other/` & Root)
- `mpa_mca_marine_reserves.gpkg`: Marine Protected Areas (MPAs), Marine Conservation Areas (MCAs), and Marine Reserves (e.g., MPRU, MoIC, DMRS).
- `cfmas.gpkg`: Collaborative Fisheries Management Area conservation zones.
- `Other/allen_benthic_simplified_mapshaper.gpkg`: Geomorphic and benthic habitat classes derived from the Allen Coral Atlas, geometrically simplified for high-performance rendering.
- `Other/bes_gridded_1km.gpkg` & `Other/bes_gridded_5km.gpkg`: Biodiversity and Ecosystem Services (BES) composite indices gridded at 1 km and 5 km resolutions.
- `Other/coelacanth_points.gpkg`: Recorded catch and sighting coordinates for the prehistoric coelacanth (*Latimeria chalumnae*) near Tanga Marine Reserve.
- `Other/iba.gpkg`: Important Bird and Biodiversity Areas covering coastal wetlands, mudflats, and offshore seabird roosts.
- `Other/tidal_reef.gpkg`: Intertidal reef flats and rocky platforms.
- `Other/monitoring_zones.gpkg` & `Other/mma.gpkg`: Reference monitoring extents and management units.

---

### 3.3. Fisheries & Mariculture (`FISHERIES_PROCESSED/`)

Artisanal, semi-industrial, and local co-management regimes supporting food security and coastal livelihoods:

| File Name | Location | Geometry | Description |
| :--- | :--- | :--- | :--- |
| `cfmas_tz.gpkg` | Root | MultiPolygon | Nationwide Collaborative Fisheries Management Areas (CFMAs). |
| `cfmas_mainland_pemba.gpkg` | Root | MultiPolygon | Delineated co-management zones across mainland coastal districts and Pemba Island. |
| `landing_sites.gpkg` | Root | Point | Official marine fish landing sites (casually referred to as *dawat*) with infrastructure attributes. |
| `fpm3.gpkg` | Root | Point / Polygon | Fisheries Pressure and Performance Metric layer (FPM v3) assessing fishing effort and intensity. |
| `Aquaculture/aquaculture_sites.gpkg` | `Aquaculture/` | Point / Polygon | Finfish and crustacean coastal aquaculture facilities. |
| `Aquaculture/seaweed_farm_sites.gpkg` | `Aquaculture/` | Point / Polygon | Shallow-water seaweed farming concessions (e.g., *Eucheuma* and *Kappaphycus*) in Zanzibar and mainland bays. |

---

### 3.4. Socioeconomic, Infrastructure & Ocean Uses (`SOCIOECONOMIC_PROCESSED/`)

Commercial ocean uses, energy extraction, shipping routes, tourism, and coastal development:

#### Energy and Subsea Infrastructure (`Energy_and_Infrastructure/`)
- `oil_gas_exploration_blocks.gpkg`: Offshore deepwater exploration and development blocks (TPDC licensing rounds).
- `exploration_wells.gpkg` & `wells_oil_gas.gpkg`: Offshore and nearshore exploration, appraisal, and production wells.
- `gas_pipeline.gpkg`: Subsea and coastal natural gas transmission pipelines (Songo Songo gas field, Mnazi Bay, Somanga Fungu).

#### Marine Transport & Navigation (`Shipping_and_Ports/`)
- `ports_harbors.gpkg` & `ports_tza.gpkg`: Major commercial ports (Dar es Salaam, Tanga, Mtwara) and secondary feeder harbors.
- `shipping_lanes.gpkg` & `shipping_lane_inshore.gpkg`: Primary international merchant vessel corridors and inshore coastal navigation channels.
- `sport_fishing_sites.gpkg`: Recreational and charter big-game sport fishing locations (Pangani, Mafia Channel).

#### Tourism & Recreation (`Tourism_Summary/`)
- `diving_sites.gpkg`: Popular scuba diving and snorkeling reef sites.
- `tz_coastal_hotels_points.gpkg` & `tz_coastal_hotels_polygons.gpkg`: Coastal resorts, hotels, and lodge infrastructures.
- `tz_coastal_tourism_points.gpkg` & `tz_coastal_tourism_points_all.gpkg`: Coastal tourism amenities, access hubs, and attractions.

#### Coastal Infrastructure & Multi-Use Activities (`Human_Use_Infrastructure/` & `Other/`)
- `coastal_features.gpkg`: Coastal morphological and human-built features.
- `roads.gpkg` & `railway.gpkg`: Arterial transport corridors providing hinterland connectivity to ports and landing sites.
- `salt_pans.gpkg`: Solar sea salt evaporation facilities in coastal estuaries.
- `Other/dagaa_fishing_areas.gpkg`: Light-assisted pelagic *dagaa* (*Stolephorus* / *Encrasicholina*) purse-seine fishing grounds.
- `Other/fish_landing_sites_and_markets.gpkg`: Integrated landing centers and coastal auction markets.
- `Other/pfz_n_kde_hotspot.gpkg`: Potential Fishing Zones (PFZ) derived from satellite SST/chlorophyll anomalies paired with Kernel Density Estimation (KDE) fishing hotspots.

---

### 3.5. Modeling & Composite Datasets (`OCEANOGRAPHIC_PROCESSED/` & `INTEGRATED_DATASETS/`)

Framework directories established for oceanographic modeling layers and integrated MSP composites:

- **`OCEANOGRAPHIC_PROCESSED/`**:
  - `Current_Vectors/`: East African Coastal Current (EACC) velocity vectors and seasonal circulation patterns.
  - `Productivity_Index/`: Ocean color and Net Primary Productivity (NPP) indices.
  - `Salinity_Maps/`: Estuarine and offshore surface salinity gradients.
  - `Temperature_Profiles/`: MODIS/VIIRS Sea Surface Temperature (SST) and thermal anomalies (Degree Heating Weeks).
- **`INTEGRATED_DATASETS/`**:
  - `Combined_MSP_Layer/`: Multi-criteria synthesis zoning proposals.
  - `Ecosystem_Composite/`: Aggregated biodiversity sensitivity layer (coral + mangrove + seagrass + megafauna).
  - `Human_Use_Composite/`: Cumulative human activity footprint and conflict-risk surfaces.

---

## 4. Processing & Quality Control Protocol

All raw source datasets (`01_RAW_DATA`) underwent rigorous spatial and attribute data processing:

1. **Topology Cleaning & Repair**:
   - Geometries validated with GEOS (`st_is_valid()`); self-intersections and slivers resolved via `st_make_valid()` and zero-width buffering.
   - Mapshaper topology-preserving simplification applied to complex high-vertex benthic layers.
2. **Standardization & Harmonization**:
   - Attribute field names normalized to snake_case (`zone`, `management_type`, `site_name`).
   - Duplicate records identified and merged using spatial joins and unique identifier checks.
3. **Clipping & Boundary Conformance**:
   - Layers clipped to the official United Republic of Tanzania Exclusive Economic Zone (`eez_split.gpkg` / `maritime_boundaries_eez.gpkg`).
   - Inland features buffered to a 5 km coastal zone where relevant to marine-terrestrial interactions.
4. **Coordinate Transformation**:
   - Transformed to **EPSG:4326** for distribution, with coordinate precision optimized for storage efficiency.

---

## 5. Usage & Integration Guide

### 5.1. Using QGIS
1. Drag and drop any `.gpkg` file into the **QGIS** (>= 3.22) Canvas.
2. If the GeoPackage contains multiple layers or tables, select the intended feature layer from the dialog.
3. Set project CRS to `EPSG:32737` (UTM 37S) when computing geodesic buffers, surface areas, or zonal statistics.

### 5.2. Using R (`sf` & `terra`)

```r
library(sf)
library(ggplot2)

# Define path to processed data
data_dir <- "02_PROCESSED_DATA"

# Load maritime boundary and coral reef datasets
eez <- st_read(file.path(data_dir, "SPATIAL_PROCESSED/maritime_boundaries_eez.gpkg"))
reefs <- st_read(file.path(data_dir, "ECOLOGICAL_PROCESSED/Coral_Reefs/coral_reefs.gpkg"))
ports <- st_read(file.path(data_dir, "SOCIOECONOMIC_PROCESSED/Shipping_and_Ports/ports_harbors.gpkg"))

# Transform to UTM 37S for spatial analysis
reefs_utm <- st_transform(reefs, crs = 32737)
eez_utm   <- st_transform(eez, crs = 32737)

# Calculate total reef area in square kilometers
cat("Total coral reef area:", sum(st_area(reefs_utm)) / 1e6, "km²\n")

# Quick plot
ggplot() +
  geom_sf(data = eez, fill = "aliceblue", color = "navy", linetype = "dashed") +
  geom_sf(data = reefs, fill = "coral", color = NA) +
  geom_sf(data = ports, color = "black", size = 2) +
  theme_minimal() +
  labs(title = "Tanzania MSP: Baseline Ecological & Port Infrastructure")
```

### 5.3. Using Python (`geopandas`)

```python
import geopandas as gpd
import matplotlib.pyplot as plt

# Read GeoPackage layers
eez = gpd.read_file("02_PROCESSED_DATA/SPATIAL_PROCESSED/maritime_boundaries_eez.gpkg")
mangroves = gpd.read_file("02_PROCESSED_DATA/ECOLOGICAL_PROCESSED/Mangroves/mangrove_forest.gpkg")
landing_sites = gpd.read_file("02_PROCESSED_DATA/FISHERIES_PROCESSED/landing_sites.gpkg")

# Project to UTM 37S for distance/area operations
eez_utm = eez.to_crs(epsg=32737)
mangroves_utm = mangroves.to_crs(epsg=32737)

print(f"Total mangrove coverage: {mangroves_utm.geometry.area.sum() / 1e6:.2f} sq km")

# Plot preview
fig, ax = plt.subplots(figsize=(8, 10))
eez.plot(ax=ax, color='none', edgecolor='gray', linestyle='--')
mangroves.plot(ax=ax, color='forestgreen', label='Mangroves')
landing_sites.plot(ax=ax, color='red', markersize=8, label='Landing Sites')
plt.title("Tanzania Marine Spatial Planning - Mangroves & Landing Sites")
plt.legend()
plt.show()
```

---

## 6. Data Governance, Citation & Inquiries

### Suggested Citation
> **The Nature Conservancy (TNC) & Government of Tanzania (2026).** *Processed Geospatial Baseline for Marine Spatial Planning in the United Republic of Tanzania (Deliverable 3: Ecological Assessment and Human-Use Map)*. Compiled by Masumbuko Semba and the TNC MSP Technical Team. Dar es Salaam, Tanzania.

### Primary Contacts
- **Project**: Marine Spatial Planning (MSP) Tanzania
- **Deliverable**: Deliverable 3 — Ecological Assessment and Human-Use Map
- **Lead Agency / Partner**: The Nature Conservancy (TNC), Tanzania Programme
- **Data Inquiries**: Refer to project leadership and the associated technical reports in `../report/`.

---
*Last updated: June 2026 / Release v1.0 (Deliverable 3 Submission)*
