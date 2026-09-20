# THABAT Study Areas

This folder stores the official shared **Areas of Interest (AOIs)** used
during the THABAT data-exploration sprint.

All team members must use the exact AOI files stored in this folder.
Do not redraw, rename, resize, or replace an AOI without informing
Person 1 and recording the change.

The AOIs are provisional candidates. The final study area will be
selected using actual evidence, including hyperspectral coverage,
pavement-pixel purity, image quality, licence conditions, supporting
imagery, and validation feasibility.

---

## Purpose of the AOIs

The AOIs allow all five team members to examine the same locations while
testing different data sources:

- Person 2: hyperspectral data
- Person 3: Sentinel-2 and temporal data
- Person 4: Landsat heat and ESA WorldCover
- Person 5: high-resolution imagery, road mask, and pixel purity
- Person 1: coordination, licences, comparison, and final AOI decision

Each AOI contains a small road corridor rather than an entire city,
emirate, or country.

---

# Current AOIs

## AOI-A — Saih Al Salam Street D42

**File:**  
[`AOI_A_saih_al_salam_D42.geojson`](AOI_A_saih_al_salam_D42.geojson)

| Field | Value |
|---|---|
| AOI ID | AOI-A |
| Road | Saih Al Salam Street (D42) |
| Country | United Arab Emirates |
| Approximate road length | 2.0 km |
| Approximate buffer | 100 m on each side |
| Approximate corridor area | 0.40 km² |
| Status | Provisional candidate |
| Created by | Dana Alhammadi |
| Creation date | 2026-09-20 |

### Selection reason

AOI-A contains a wide divided highway in a relatively open desert
environment. It was selected for initial hyperspectral
pavement-screening feasibility testing because it has:

- wide exposed pavement;
- relatively low building density;
- limited dense vegetation;
- a mostly straight road alignment;
- open surrounding land;
- potential access for later field photographs.

### Known limitations

- The surrounding desert may still contaminate coarse hyperspectral pixels.
- Some nearby tracks, vegetation, and drainage features may affect edge pixels.
- The road may not have usable EnMAP, Tanager, or Satellite 813 coverage.
- The AOI has not yet passed the pavement-pixel-purity test.
- No road-condition ground truth has yet been confirmed.

### Approval conditions

AOI-A can become the primary THABAT study area only if the team confirms:

- usable hyperspectral coverage;
- acceptable scene quality;
- sufficient pavement-dominant pixels;
- suitable high-resolution imagery;
- legal data access and sharing conditions;
- a credible validation method.

### Overview map

The visual reference is stored at:

```text
outputs/maps/P1_AOI_A_D42_overview_2026-09-20.png
