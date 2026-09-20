# THABAT Data Exploration Sprint — Official Team Handoff

## Sprint Purpose

The purpose of this sprint is to determine whether the currently
available satellite data are suitable for building a credible THABAT
Proof of Concept.

THABAT uses hyperspectral and supporting Earth-observation data to
identify unusual pavement-related spectral behaviour and help road
authorities decide which road sections should be physically inspected
first.

THABAT does not prove that a road is damaged, diagnose hidden defects,
certify road safety, or replace engineers.

---

# Official Shared Areas of Interest

All members must use the exact GeoJSON files below.

## AOI-A — Saih Al Salam Street D42

**File:**

`data/study_areas/AOI_A_saih_al_salam_D42.geojson`

- AOI ID: AOI-A
- Approximate road length: 2.0 km
- Approximate buffer: 100 m on each side
- Status: Provisional candidate

## AOI-B — Jebel Ali-Lahbab Road E77

**File:**

`data/study_areas/AOI_B_jebel_ali_lahbab_E77.geojson`

- AOI ID: AOI-B
- Approximate road length: 2.2 km
- Approximate buffer: 70 m on each side
- Status: Provisional candidate

## AOI-C — Data-Driven Backup

**Status:** Not created yet.

Person 2 will search the hyperspectral catalogues. If AOI-A and AOI-B
do not have suitable hyperspectral coverage, Person 2 will identify a
better wide-road location. Person 1 will then create AOI-C around that
confirmed location.

Do not create personal versions of these AOIs.

---

# Shared Data Manifest

Every real satellite product or scene must be recorded in:

`data/data_manifest.csv`

Required information includes:

- Dataset ID
- Provider
- Sensor
- Official product or scene ID
- AOI ID
- Acquisition date
- Processing level
- Spatial resolution
- Cloud or quality information
- File format
- Official source
- Access date
- Licence or usage terms
- Redistribution permission
- Required attribution
- Google Drive storage location
- Owner
- Quality status
- USE / CONDITIONAL / REJECT decision
- Notes and limitations

Do not guess missing information. Enter `Unknown` and investigate it.

---

# Data Storage Rules

Large or restricted files must be stored only in the private Google
Drive folder:

`Restricted_Data`

Google Drive access must remain restricted to the five team members.

Raw or restricted imagery must not be uploaded to GitHub.

## Google Drive locations

- Hyperspectral:
  `Restricted_Data/01_Hyperspectral/`

- High-resolution imagery:
  `Restricted_Data/02_High_Resolution/`

- Sentinel-2:
  `Restricted_Data/03_Multispectral/`

- Landsat:
  `Restricted_Data/04_Thermal/`

- WorldCover:
  `Restricted_Data/05_Land_Cover/`

- Field validation:
  `Restricted_Data/06_Field_Validation/`

- Temporary downloads:
  `Restricted_Data/07_Temporary_Downloads/`

---

# Security Rules

Never upload or share:

- Passwords
- API keys
- Access tokens
- Private account details
- Signed download URLs
- Commercial raw imagery
- Restricted competition imagery
- Personal or confidential information

Do not paste credentials into GitHub, screenshots, notebooks, or AI
conversations.

---

# Temporary Data Roles

## Person 1 — Team Lead and Data Integration

Responsible for:

- Official AOI files
- Data-manifest control
- Licence and security records
- Team file and naming rules
- Collecting all member evidence
- Scoring AOIs
- Leading the final data decision
- Writing `docs/data_feasibility_decision.md`

## Person 2 — Hyperspectral Data

Explore:

- EnMAP
- EnMAP geoservice
- Planet Tanager open data

Main question:

Can a real hyperspectral product cover and provide potentially usable
road-related pixels for AOI-A or AOI-B?

Required outputs:

- `outputs/tables/hyperspectral_scene_inventory.csv`
- `outputs/maps/enmap_coverage_AOI_A.png`
- `outputs/maps/enmap_coverage_AOI_B.png`
- `outputs/figures/hyperspectral_composite.png`
- `outputs/figures/sample_hyperspectral_spectra.png`
- `notebooks/00_hyperspectral_inventory.ipynb`
- `notebooks/01_hyperspectral_scene_check.ipynb`
- `docs/hyperspectral_feasibility_notes.md`

Person 2 must also identify the possible location for AOI-C if the
current AOIs do not have suitable hyperspectral coverage.

## Person 3 — Sentinel-2 and Temporal Data

Explore:

- Sentinel-2 Level-2A
- Copernicus Data Space
- Planetary Computer STAC

Main question:

Can Sentinel-2 provide a multispectral baseline, environmental context,
and repeat-date information for AOI-A or AOI-B?

Required outputs:

- `outputs/tables/sentinel2_scene_inventory.csv`
- `outputs/maps/sentinel2_rgb_AOI_candidates.png`
- `outputs/maps/sentinel2_quality_mask.png`
- `outputs/figures/sentinel2_temporal_summary.png`
- `notebooks/02_sentinel2_stac_access.ipynb`
- `notebooks/03_sentinel2_temporal_check.ipynb`
- `docs/sentinel2_feasibility_notes.md`

## Person 4 — Heat and Land-Cover Data

Explore:

- Landsat 8/9 Collection 2 Level-2 Surface Temperature
- USGS EarthExplorer or Planetary Computer
- ESA WorldCover

Main question:

Can Landsat provide useful heat context, and can WorldCover provide
useful broad land-cover context for AOI-A or AOI-B?

Required outputs:

- `outputs/tables/landsat_temperature_inventory.csv`
- `outputs/maps/landsat_heat_context.png`
- `outputs/maps/worldcover_context.png`
- `outputs/figures/hot_season_temperature_summary.png`
- `notebooks/04_landsat_temperature_check.ipynb`
- `notebooks/05_worldcover_context.ipynb`
- `docs/thermal_landcover_feasibility_notes.md`

Heat and land cover must not be presented as direct proof of pavement
damage.

## Person 5 — High-Resolution Imagery and Pixel Purity

Explore:

- Planet
- PlanetScope
- Planet Developers
- Competition-provided VHR imagery

Main question:

Can high-resolution imagery produce a credible pavement mask and help
measure how much of each hyperspectral pixel is actually road?

Required outputs:

- `outputs/tables/planet_scene_inventory.csv`
- `outputs/maps/vhr_road_mask.png`
- `outputs/maps/hyperspectral_pixel_purity.png`
- `outputs/tables/pixel_purity_sensitivity.csv`
- `outputs/maps/field_validation_candidates.png`
- `notebooks/06_vhr_road_mask.ipynb`
- `notebooks/07_pixel_purity_test.ipynb`
- `docs/planet_access_and_licence_notes.md`

Person 5 cannot complete the final pixel-purity analysis until Person 2
provides the exact hyperspectral raster grid, CRS, and pixel size.

---

# Required Evidence from Every Person

Each member must give Person 1:

1. One coverage or context map
2. One inventory or results table
3. One working notebook or opened-data proof
4. One short method paragraph
5. One short result paragraph
6. One limitations paragraph
7. One USE / CONDITIONAL / REJECT recommendation
8. One list of blockers or decisions needed

“I explored the website” is not a deliverable.

---

# Member-to-Member Handoffs

## Person 2 → Person 5

Must include:

- Hyperspectral scene footprint
- Exact raster or pixel grid
- CRS
- Pixel size
- Acquisition date
- Quality notes

## Person 5 → Person 2

Must include:

- Pavement polygon or road mask
- Pixel-purity table
- High-purity pixel locations
- Contamination and exclusion notes

## Person 3 → Person 2

Must include:

- Closest suitable Sentinel-2 date
- Cloud and quality information
- Historical scene list
- Multispectral baseline plan

## Person 4 → Persons 1 and 3

Must include:

- Heat-context map or table
- WorldCover context
- Quality and resolution limitations
- Recommendation: score input, display-only context, or reject

A handoff is incomplete if it lacks IDs, dates, CRS, quality information,
licence notes, or clear filenames.

---

# Daily Update Format

At the end of each day, post:

```text
Name and person number:
Date:
Data source explored:
AOI tested:
What I successfully opened:
Scene or product ID:
Evidence files saved:
Main result:
Quality problem or limitation:
Licence or sharing note:
Main blocker:
Current decision: USE / CONDITIONAL / REJECT / NOT READY
Next action:
