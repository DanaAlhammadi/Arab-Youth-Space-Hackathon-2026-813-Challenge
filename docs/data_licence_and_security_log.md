# THABAT — Data Licence and Security Log

## Purpose

This log records the current data sources used or seriously considered for the THABAT proof of concept, together with access, sharing, attribution, storage, and security status.

**Rule:** `VERIFY` or `CONDITIONAL` means the team must not assume unrestricted redistribution. Large raw scenes, restricted imagery, credentials, signed URLs, and private account details stay outside the public repository.

## Repository security rules

- Do not commit passwords, API keys, Copernicus tokens, Planet tokens, signed URLs, or private account details.
- Do not commit full commercial, restricted, or competition-restricted satellite scenes.
- Keep large/raw imagery in the approved private/restricted storage.
- Only put small samples, metadata, AOIs, and derived figures/tables in GitHub when their sharing rights are confirmed.
- Every final public dataset must have an identified product/scene ID, date, source, licence/terms, and attribution note.
- A `CONDITIONAL` or `VERIFY` row is not a public-release approval.

## Current source log

| Source | Role | AOI | Sharing status | Current decision | Notes |
|---|---|---|---|---|---|
| Landsat 9 Collection 2 Level-2 ST | Thermal context | AOI-A | VERIFY current terms | USE | Selected scene: `LC09_L2SP_160043_20260831_02_T1`; use corrected QA/fill masking. |
| Sentinel-2 L2A | Multispectral context / temporal comparison | AOI-A | VERIFY current terms | USE | Exact 4-Oct product recorded; 19-Sep product ID still needs to be captured. |
| EnMAP HSI L2A | Hyperspectral candidate | AOI-A/AOI-B | CONDITIONAL under EnMAP Data License | CONDITIONAL | Collection verified; no confirmed item over the current road AOIs was established. |
| Tanager Open Data | Hyperspectral candidate | AOI-A/AOI-B | CONDITIONAL; item-level licence required | CONDITIONAL | Do not use non-UAE scenes as road evidence. |
| ECOSTRESS L2 LSTE | Thermal candidate/supporting context | AOI-A/AOI-B | VERIFY product-specific terms | CONDITIONAL | Exact product/version and QA evidence still required. |
| FGIC UAE 1 m imagery service | High-resolution road context candidate | AOI-A/AOI-B | VERIFY display/redistribution rights | CONDITIONAL | Do not export/commit imagery to GitHub until rights are confirmed. |
| AOI-B road-segment geometry | Team / ArcGIS Pro | AOI-B | VERIFY source attribution/redistribution terms | USE | `roadaoi_B_converted.geojson`; 4 polygon features; segment IDs B-002, B-003, B-004, B-005; 800 m buffer recorded. Geometry format is suitable for GitHub. Thermal-statistics IDs still need reconciliation. |

| AOI-B team geometry | Official road-segment geometry candidate | AOI-B | Team-generated geometry | USE | Uploaded ArcGIS Features JSON is EPSG:32640 with B-002 to B-005 and 800 m buffer; convert to standard GeoJSON. Street name/B-001 status pending. |

## Known technical interpretation boundaries

### Landsat ST_B10

The team uses:

`Kelvin = DN × 0.00341802 + 149.0`

then:

`°C = Kelvin − 273.15`

Pixel value `0` must be treated as fill/no-data and QA information must be checked.

**Interpretation:** broad thermal context only; not proof of individual pavement damage.

### ECOSTRESS

Use the exact product/version metadata and product-specific QA/QC.

For the workflow currently documented by the team:

`°C = Kelvin − 273.15`

Only apply this after confirming that the selected ECOSTRESS LST layer is actually in Kelvin. Do **not** apply the Landsat ST_B10 scaling formula to ECOSTRESS.

### Sentinel-2

Use for multispectral/environmental context and temporal comparison.

The 4 October 2026 L2A product recorded in the manifest has reported cloud cover `0.166191`. Visual comparison with the 19 September observation did not show an obvious road-surface change in the tested views. This is not evidence that no engineering change occurred; it only records the observed satellite-level comparison.

## GitHub release checklist

Before public submission:

- [ ] Repository opens in a logged-out browser.
- [ ] No credentials/tokens/private URLs are present.
- [ ] No full restricted/raw scenes are committed.
- [ ] Every public dataset row has product/scene ID, date, licence/terms, and attribution.
- [ ] Every derived map/figure has its source noted.
- [ ] Any VHR or hyperspectral imagery displayed publicly has verified rights.
- [ ] `data_manifest.csv` is included and current.
- [ ] This licence/security log is included and current.

## Known gaps to close

1. Replace the September 19 Sentinel-2 placeholder with its exact product ID.
2. Record the exact ECOSTRESS product ID/version, acquisition date, units, and QA/QC layer if ECOSTRESS is retained.
3. Confirm the exact AOI-B street name and whether B-001 is intentionally absent; the supplied geometry is now recorded as verified for EPSG:32640, segments B-002–B-005, and 800 m buffer.
4. Confirm item-level licence and public-display permissions for any EnMAP/Tanager/VHR data actually used in the final deck.
5. Keep all uncertain sources visibly marked `CONDITIONAL` until evidence is saved.

## AOI-B geometry status

The supplied `roadaoi_B_converted.geojson` is treated as the current AOI-B geometry candidate for the repository. It contains 4 polygon features with segment IDs B-002, B-003, B-004, B-005 and an 800 m buffer field. Its public GitHub use is marked **VERIFY** for any underlying source-road attribution, while the geometry itself is marked usable as project geometry. Do not claim that the AOI-B thermal statistics are aligned with this geometry until the segment-ID mismatch is resolved.
