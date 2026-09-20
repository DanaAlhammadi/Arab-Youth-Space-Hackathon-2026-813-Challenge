# THABAT Hackathon Repository Notes

## 1. Repository Identity

**Repository name:**  
`813-hyperspectral-hackathon`

**Repository URL:**  
`https://github.com/Tnecniv-Teikram/813-hyperspectral-hackathon`

**Date reviewed:**  
2026-09-20

**Reviewed by:**  
Dana Alhammadi — Person 1 / Team Lead

**Repository purpose:**  
The repository describes itself as the official collection of data
exploration notebooks, tutorials, starter code, documentation, and
spectral-analysis examples for the Arab Youth Space Hackathon:
813 Challenge.

**Current THABAT use:**  
The repository will be used as a learning and starter-code reference.
THABAT will adapt the examples for road and pavement hyperspectral
screening rather than copying the urban notebook without modification.

---

# 2. Relevant Data Sources

The repository identifies the following primary data sources:

| Dataset | Provider | Approximate resolution | Bands / range | THABAT purpose |
|---|---|---:|---|---|
| Tanager-1 | Planet Labs | 30 m | 426 bands, 380–2500 nm | Optional hyperspectral source |
| EnMAP | DLR / Germany | 30 m | 228 bands, 420–2450 nm | Primary hyperspectral feasibility source |
| Planet VHR | Planet Labs | 3–5 m | 4–8 multispectral bands | Road mask, visual context, and pixel-purity support |
| Sentinel-2 | Copernicus | 10–60 m | 13 multispectral bands | Multispectral baseline and time-series context |
| Landsat | USGS / NASA | 30 m | Multispectral and thermal products | Heat and long-term environmental context |

## THABAT interpretation

- EnMAP or Tanager will provide the main hyperspectral evidence.
- Planet or other VHR imagery will be used to locate the road precisely.
- Sentinel-2 will provide a simpler multispectral comparison.
- Landsat will provide heat context only.
- None of these sources alone proves pavement damage.

---

# 3. Repository Structure

The README describes the repository as containing:

```text
813-hyperspectral-hackathon/
├── README.md
│
├── notebooks/
│   ├── 00_data_exploration_starter.ipynb
│   ├── 01_agriculture_crop_intelligence.ipynb
│   ├── 02_land_use_land_cover_change.ipynb
│   ├── 03_air_quality_ghg_plumes.ipynb
│   ├── 04_climate_disasters_fire_flood.ipynb
│   └── 05_ecosystem_health_blue_carbon.ipynb
│
├── docs/
│   ├── spectral_indices_reference.md
│   ├── tanager_data_guide.md
│   └── stac_collection_map.md
│
├── assets/
│   └── images/
│
└── requirements.txt


```markdown
---

# 4. Recommended Notebook Order for THABAT

## Step 1 — Read the README

Understand:

- available data;
- folder structure;
- notebook purpose;
- licences;
- known technical issues.

## Step 2 — Run the starter notebook

Primary filename shown in the repository structure:

```text
00_data_exploration_starter.ipynb
