# THABAT Hackathon Repository Notes

## Document Purpose

This document records the official hackathon repository structure,
starter notebooks, setup instructions, data sources, licences, known
technical issues, and the parts most relevant to THABAT.

It is maintained by Person 1 so that all team members follow the same
official technical guidance.

This document is a set of notes and does not replace:

- The official hackathon platform
- The official submission page
- Written instructions from the organizers
- Dataset-specific licence terms
- Competition-provided access conditions

When information in the repository conflicts with the current official
hackathon platform, the team must record the conflict and request
clarification. Until clarified, the current official platform should be
treated as the operational source of truth for deadlines and submission
requirements.

---

# 1. Repository Identity

**Repository name:**

```text
813-hyperspectral-hackathon
```

**Repository URL:**

```text
https://github.com/Tnecniv-Teikram/813-hyperspectral-hackathon
```

**Repository reviewed on:**

```text
2026-09-20
```

**Reviewed by:**

```text
Dana Alhammadi — Person 1 / Team Lead
```

**Repository description:**

The repository describes itself as the official collection of:

- Data-exploration notebooks
- Tutorials
- Starter code
- Spectral-analysis examples
- Data-access guidance
- Theme-specific examples

for the Arab Youth Space Hackathon: 813 Challenge.

The repository is intended to help participants with little or no prior
remote-sensing experience begin working with real Earth-observation and
hyperspectral data.

---

# 2. How THABAT Will Use This Repository

THABAT will use the official repository as:

- A learning resource
- A starter-code reference
- A guide for accessing STAC catalogues
- A guide for opening Tanager hyperspectral data
- A guide for reading wavelengths and quality masks
- A guide for working with Sentinel-2
- A reference for spectral visualisation
- A source of licence and attribution information

THABAT will not copy a theme notebook and present it as the final
solution.

The repository does not currently provide a complete road-health or
pavement-condition notebook.

THABAT must develop its own road-specific workflow, including:

- Official road AOIs
- Road and pavement masks
- Hyperspectral road-pixel extraction
- Pixel-purity measurement
- Mixed-pixel filtering
- Matched pavement references
- Spectral anomaly scoring
- Confidence scoring
- Temporal persistence
- Validation against field or high-resolution evidence
- Inspection-priority recommendations

---

# 3. Hackathon and Repository Overview

The repository describes the Arab Youth Space Hackathon as a
multi-phase regional competition and incubation programme organised
around satellite-powered solutions for:

- Climate
- Urban challenges
- Environmental challenges
- Agriculture
- Ecosystems
- Water
- Air quality
- Disaster response

The stated objective is to move from problem definition to a practical
proof of concept and, for selected teams, to an incubated minimum viable
product.

The repository highlights the following programme goals:

1. Make hyperspectral Earth observation more accessible.
2. Encourage real, policy-relevant solutions.
3. Address region-specific challenges.
4. Build a regional community of researchers, engineers, developers,
   and entrepreneurs.
5. Move beyond simple maps toward deployable decision-support tools.

---

# 4. THABAT Project Context

## Project name

```text
THABAT | ثبات
```

## THABAT core concept

THABAT uses hyperspectral Earth-observation data, complementary imagery,
and AI to identify abnormal pavement material-condition behaviour across
road networks and prioritize which road segments should receive physical
inspection first.

## THABAT does

- Screen road corridors for unusual spectral behaviour
- Compare road segments with suitable references
- Use VHR imagery to identify pavement location
- Measure pavement-pixel purity
- Add temporal and environmental context
- Rank road segments for inspection
- Explain why a road segment was flagged
- Report uncertainty and data-quality limitations

## THABAT does not

- Prove that a road is damaged
- Directly detect hidden internal cracks from orbit
- Predict an exact failure date
- Certify road safety
- Replace pavement engineers
- Replace physical inspection
- Assume every spectral anomaly is deterioration

## Safe THABAT claim

> THABAT identifies unusual pavement-related spectral behaviour and
> helps engineers decide where targeted physical inspection should occur
> first.

---

# 5. Challenge Theme Relevant to THABAT

The repository identifies the most relevant starter theme as:

```text
Theme 2 — Urban Expansion, Land Use Change & Heat Risk
```

The closest available notebook is:

```text
notebooks/02_land_use_land_cover_change.ipynb
```

The repository says this notebook covers:

- Built-up surface detection
- Impervious surface mapping
- Land-cover change
- Vegetation
- Water
- Bare soil
- Urban indices

The notebook uses:

- NDVI
- NDBI
- MNDWI
- BUI
- Land-cover classification

## Relevance to THABAT

This notebook is useful for learning how to:

- Open urban hyperspectral data
- Access Tanager STAC collections
- Select spectral wavelengths
- Compute spectral features
- Separate broad surface types
- Visualise urban and land-cover results
- Work with impervious surfaces

## Limitation for THABAT

The urban notebook does not provide:

- Pavement-condition labels
- Road masks
- Pixel-purity calculations
- Pavement spectral references
- Road anomaly detection
- Inspection-priority scores
- Road-condition validation

Therefore, it is a technical starting point only.

---

# 6. Data and Technology Stack

## 6.1 Tanager-1

**Provider:**

```text
Planet Labs
```

**Approximate spatial resolution:**

```text
30 m
```

**Spectral information:**

```text
426 bands
Approximately 380–2500 nm
```

**Repository role:**

- Main open hyperspectral example
- STAC-based access
- HDF5 surface-reflectance analysis
- Spectral-index calculation
- Full-spectrum visualisation

**Possible THABAT role:**

- Optional hyperspectral source
- Learning the hyperspectral pipeline
- Testing spectral methods on available road-like surfaces
- Cross-sensor comparison if useful road coverage exists

**Important limitation:**

The themed open Tanager catalogue may not contain a suitable scene over
THABAT's selected UAE road AOIs.

Tanager is useful only if a real scene:

- Covers a suitable road
- Has acceptable quality
- Has readable wavelength metadata
- Contains enough usable road-related pixels

---

## 6.2 EnMAP

**Provider:**

```text
DLR / Germany
```

**Approximate spatial resolution:**

```text
30 m
```

**Spectral information:**

```text
Approximately 228 bands
Approximately 420–2450 nm
```

**Possible THABAT role:**

- Primary open hyperspectral feasibility source
- Pavement spectral extraction
- Hyperspectral anomaly baseline
- Comparison with multispectral data

**Preferred product:**

```text
Level-2A or another analysis-ready surface-reflectance product
```

**Important requirement:**

EnMAP coverage, processing level, acquisition date, scene quality,
licence, and road observability must be verified by Person 2.

---

## 6.3 Planet VHR / PlanetScope

**Provider:**

```text
Planet Labs
```

**Approximate spatial resolution in the repository:**

```text
3–5 m
```

**Possible THABAT role:**

- Road and pavement-mask creation
- Carriageway identification
- Median and shoulder exclusion
- Visible context
- Pavement-pixel-purity estimation
- Candidate field-validation points

**Important limitation:**

Access conditions, download rights, screenshot rights, derived-output
rights, and public-display permissions must be verified separately.

The Tanager open-data licence must not be assumed to apply to Planet VHR
or PlanetScope products.

---

## 6.4 Sentinel-2

**Provider:**

```text
Copernicus / ESA
```

**Spectral type:**

```text
Multispectral
13 bands
```

**Possible THABAT role:**

- Multispectral baseline
- Historical comparison
- Environmental context
- Broad land-cover masking
- Vegetation, water, and bare-soil context
- Comparison against hyperspectral value

**Preferred product:**

```text
Sentinel-2 Level-2A surface reflectance
```

**Important limitation:**

Sentinel-2 is not hyperspectral.

Road-level interpretation is limited by:

- Pixel size
- Mixed pixels
- Cloud and shadow
- Seasonal differences
- Acquisition conditions

---

## 6.5 Landsat

**Provider:**

```text
USGS / NASA
```

**Approximate spatial resolution:**

```text
30 m for most mapped products
```

**Possible THABAT role:**

- Surface-temperature context
- Long-term heat exposure
- Historical environmental context

**Preferred product:**

```text
Landsat 8/9 Collection 2 Level-2 Surface Temperature
```

**Important limitation:**

Landsat surface temperature is contextual evidence.

It does not prove pavement deterioration.

The correct language is:

> The road segment has elevated heat exposure.

The incorrect language is:

> Landsat proved that heat damaged the road.

---

# 7. Open Tools Mentioned in the Repository

The repository identifies tools such as:

| Tool | Purpose |
|---|---|
| `h5py` | Read Tanager HDF5 files |
| `numpy` | Array operations |
| `matplotlib` | Figures and spectral plots |
| `geopandas` | Vector and geospatial data |
| `leafmap` | Interactive maps and COG layers |
| `pystac` | STAC data structures |
| `pystac-client` | Search STAC catalogues |
| `requests` | Download data and metadata |
| `rioxarray` | Raster data with spatial information |
| `xarray` | Multidimensional array analysis |

## Additional THABAT packages likely required

THABAT may also need:

- `pandas`
- `rasterio`
- `shapely`
- `pyproj`
- `scikit-learn`
- `scipy`
- `jupyter`
- `plotly`
- `folium`
- `pyyaml`

Do not install packages only because they sound useful.

Add a package only when:

- A notebook requires it
- The project code uses it
- Its purpose is documented

---

# 8. Repository Structure

The README describes the repository structure approximately as:

```text
813-hyperspectral-hackathon/
│
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
├── LICENSE
│
└── requirements.txt
```

## Important note

The exact files in the live repository must be checked directly.

Do not assume that every file listed in the README exists or has the
same name.

---

# 9. Notebook Guide

## 9.1 Starting notebook

The repository structure identifies:

```text
notebooks/00_data_exploration_starter.ipynb
```

as the starting notebook.

The README also refers elsewhere to:

```text
00_EO_data_quickstart_notebook.ipynb
```

This is a filename inconsistency.

## Team decision

Use the file that actually exists inside the live repository's
`notebooks/` folder.

Record the exact filename before running it.

## Starting notebook purpose

The starter notebook is intended to explain:

- What STAC is
- How to query satellite imagery by location and date
- How to use Sentinel-2
- How to access Tanager
- How to inspect metadata
- What a COG is
- What surface reflectance is
- How to read a Tanager HDF5 file
- How to extract wavelengths
- How to calculate spectral indices
- How to plot a mean spectrum

---

## 9.2 Relevant THABAT theme notebook

```text
notebooks/02_land_use_land_cover_change.ipynb
```

The README associates it with:

```text
urban
natural-lands
```

Tanager STAC collections.

The notebook's outputs include:

- Index maps
- Land-cover classes
- Pixel statistics
- Built-up surface indicators

## THABAT adaptation required

The team must modify the workflow to include:

1. Import AOI-A and AOI-B.
2. Search real scenes covering the AOIs.
3. Overlay the road polygons.
4. Build or import a pavement mask.
5. Calculate pavement-pixel purity.
6. Exclude mixed or poor-quality pixels.
7. Extract road-related spectra.
8. Select matched reference road segments.
9. Calculate a transparent spectral-anomaly baseline.
10. Compare hyperspectral results with Sentinel-2 or RGB.
11. Add confidence and quality flags.
12. Rank road segments for inspection.
13. Validate results with independent evidence.

---

# 10. Common Notebook Workflow

The README says the notebooks generally follow twelve steps:

1. Install dependencies.
2. Set or correct the Titiler endpoint.
3. Load STAC items.
4. Inspect metadata and thumbnails.
5. Visualise the scene on an interactive map.
6. Download or stream the HDF5 surface-reflectance file.
7. Check cloud, cirrus, nodata, and quality masks.
8. Extract wavelength metadata.
9. Select wavelengths for the required analysis.
10. Load only the necessary bands.
11. Calculate indices or spectral features.
12. Visualise maps, summary statistics, and mean spectra.

## THABAT adaptation

For THABAT, the twelve-step flow becomes:

1. Install dependencies.
2. Load the official AOI GeoJSON.
3. Search for a real hyperspectral scene.
4. Record the scene in `data/data_manifest.csv`.
5. Check licence and storage rules.
6. Inspect scene metadata and quality masks.
7. Load the surface-reflectance data.
8. Overlay the road AOI.
9. Add the VHR pavement mask.
10. calculate pavement-pixel purity.
11. Extract and compare pavement spectra.
12. produce anomaly, confidence, and inspection-priority outputs.

---

# 11. How to Run the Notebooks

## 11.1 Google Colab

The README recommends Google Colab because it avoids local environment
setup.

The first notebook cells install the required dependencies.

### Recommended beginner procedure

1. Open the real notebook file in GitHub.
2. Download the `.ipynb` file if the Colab link does not work.
3. Open Google Colab.
4. Select:

```text
File → Upload notebook
```

5. Upload the notebook.
6. Run one cell at a time.
7. Read the explanation before running each cell.
8. Save screenshots of the first successful output.
9. Record all errors.
10. Never paste a private password or API key into a notebook.

## Colab-link warning

The README contains a Colab URL with:

```text
YOUR-ORG
```

This appears to be a placeholder.

If the link fails, manually upload the notebook into Colab.

---

## 11.2 Local Jupyter

**Requirement:**

```text
Python 3.9+
```

### Clone the repository

```bash
git clone https://github.com/Tnecniv-Teikram/813-hyperspectral-hackathon.git
cd 813-hyperspectral-hackathon
```

### Create a virtual environment

```bash
python -m venv .venv
```

### Activate on Windows

```bash
.venv\Scripts\activate
```

### Activate on macOS or Linux

```bash
source .venv/bin/activate
```

### Install requirements

```bash
pip install -r requirements.txt
```

### Start Jupyter

```bash
jupyter notebook
```

---

## 11.3 `uv` option

The README also provides a faster environment option using `uv`.

Example:

```bash
uv venv
uv pip install -r requirements.txt
uv run jupyter notebook
```

Use this only if the team member already understands `uv`.

Google Colab is the simpler option for beginners.

---

## 11.4 Space42 gIQ

The README states that selected teams receive access to the Space42 gIQ
platform, described as a preconfigured cloud environment with:

- Dependencies installed
- Direct data access
- Analysis tools
- Deployment support

## Current THABAT status

```text
gIQ access confirmed: TO VERIFY
gIQ account active: TO VERIFY
Training materials visible: TO VERIFY
Required permissions active: TO VERIFY
Planet VHR access active: TO VERIFY
```

The team has already contacted the organizers because preparatory
training materials were not visible despite the team being admitted.

This remains an access blocker until the organizers respond.

---

# 12. Known Technical Issue

## Leafmap / Titiler endpoint conflict

The README warns that running Planetary Computer cells before Tanager
map cells in the same kernel may cause `leafmap` to cache an incompatible
endpoint.

Example error:

```text
Invalid URL '<leafmap.stac.PlanetaryComputerEndpoint object at ...>/cog/info'
```

## Documented fix

Run this before map cells:

```python
import os
os.environ["TITILER_ENDPOINT"] = "https://titiler.xyz"
```

## THABAT troubleshooting steps

When this error occurs:

1. Copy the complete error message.
2. Save a screenshot.
3. Restart the notebook runtime.
4. Run the Titiler environment-variable cell first.
5. Re-run the notebook from the beginning.
6. Record whether the fix worked.
7. Do not repeatedly change unrelated code.

---

# 13. Tanager HDF5 Download Notes

The README states that Tanager surface-reflectance HDF5 files may be
approximately:

```text
1–5 GB
```

Approximate download times depend on connection speed.

## THABAT storage rule

Tanager HDF5 files must be stored in:

```text
Google Drive/
Restricted_Data/
01_Hyperspectral/
Tanager/
```

They must not be committed to GitHub.

## Download rules

- Check whether the file already exists before downloading it again.
- Avoid duplicate downloads.
- Record every downloaded product in `data/data_manifest.csv`.
- Record the exact scene/item ID.
- Record acquisition date.
- Record file size.
- Record storage path.
- Record licence and attribution.
- Keep temporary files in the private Drive.
- Delete unnecessary duplicate files after verification.

---

# 14. Understanding Tanager Hyperspectral Data

## 14.1 Spectral information

The README explains that:

- An ordinary image contains three visible bands.
- Tanager records 426 narrow bands.
- The spectral range is approximately 380–2500 nm.
- Narrow bands can capture detailed spectral behaviour.

## Relevance to THABAT

For roads, detailed spectral information may help investigate:

- Material differences
- Surface weathering
- Moisture-related effects
- Dust or surface contamination
- Asphalt ageing proxies
- Differences between repaired and unrepaired areas

These are research hypotheses.

They are not confirmed defect diagnoses.

---

## 14.2 HDF5 data structure

The README describes a Tanager surface-reflectance file structure similar
to:

```text
HDFEOS/GRIDS/HYP/Data Fields/
├── surface_reflectance
├── beta_cloud_mask
├── beta_cirrus_mask
├── nodata_pixels
├── aerosol_optical_depth
├── column_water_vapour
├── sensor_zenith
└── sun_zenith
```

## THABAT meaning of each layer

### `surface_reflectance`

The main spectral data cube.

### `beta_cloud_mask`

Identifies pixels affected by cloud.

### `beta_cirrus_mask`

Identifies thin cirrus-cloud effects.

### `nodata_pixels`

Identifies missing or invalid pixels.

### `aerosol_optical_depth`

Provides information about atmospheric aerosol conditions.

### `column_water_vapour`

Provides atmospheric water-vapour information.

### `sensor_zenith`

Describes the observation angle.

### `sun_zenith`

Describes the sun angle.

These quality and geometry layers must not be ignored.

A road spectrum should not be trusted only because it can be plotted.

---

# 15. Reading Tanager Wavelength Metadata

The README states that wavelengths are stored in the STAC item's band
metadata under:

```text
eo:center_wavelength
```

not:

```text
center_wavelength
```

Example:

```python
bands_meta = item["assets"][sr_key].get("bands", [])

spectral_bands = [
    band for band in bands_meta
    if "eo:center_wavelength" in band
]

wavelengths_um = np.array([
    band["eo:center_wavelength"]
    for band in spectral_bands
])

wavelengths_nm = wavelengths_um * 1000.0
```

## THABAT rule

Always store and analyse wavelength values.

Do not rely only on hard-coded band numbers.

Different sensors may use different band numbering even when measuring
similar wavelengths.

This is especially important if THABAT later compares:

- Tanager
- EnMAP
- Satellite 813
- Another hyperspectral source

---

# 16. Water-Vapour Absorption Windows

The README identifies two wavelength regions that are strongly affected
by atmospheric water-vapour absorption:

```text
1350–1450 nm
1800–1950 nm
```

The README recommends excluding these regions from ground-reflectance
interpretation.

Example function:

```python
def is_water_vapor(wavelength_nm):
    return (
        1350 <= wavelength_nm <= 1450
        or
        1800 <= wavelength_nm <= 1950
    )
```

## THABAT rule

Do not use these regions as evidence of pavement condition unless a
qualified remote-sensing method explicitly justifies their use.

Record:

- Which bands were removed
- Their wavelengths
- Why they were removed
- Whether the same masking was applied to all compared spectra

---

# 17. Relevant Spectral Indices

The repository includes indices for:

- Vegetation
- Built-up surfaces
- Water
- Fire
- Agriculture
- Air quality

## Urban indices relevant to context

### NDVI

Used for vegetation context.

```text
(NIR - Red) / (NIR + Red)
```

### NDBI

Used for built-up context.

```text
(SWIR - NIR) / (SWIR + NIR)
```

### MNDWI

Used for water context.

```text
(Green - SWIR) / (Green + SWIR)
```

### BUI

Used for built-up area corrected for vegetation.

```text
NDBI - NDVI
```

## THABAT warning

These indices are not pavement-health scores.

They may help:

- Exclude vegetation
- Exclude water
- Identify surrounding built-up areas
- Provide context
- Compare broad surfaces

They do not directly identify:

- Cracking
- Rutting
- Potholes
- Internal damage
- Structural failure

The THABAT road model needs pavement-specific spectral and validation
work beyond these indices.

---

# 18. Repository Licence and Attribution

## 18.1 Code and notebooks

The README states that repository code and notebooks are released under:

```text
MIT License
```

The repository's `LICENSE` file should be checked before copying or
modifying code.

## Code-use rule

When THABAT adapts repository code:

- Keep copyright and licence notices where required.
- Record the original source.
- Document major modifications.
- Do not imply that starter code was created entirely by the team.

---

## 18.2 Tanager open data

The README states that the Tanager data used in the notebooks are made
available under:

```text
Creative Commons CC BY 4.0
```

The README gives attribution wording similar to:

```text
Tanager STAC Data, available at www.planet.com/data/stac
© [YEAR] Planet Labs PBC. All Rights Reserved.
```

The year must correspond to the scene-acquisition year.

For adapted outputs, use wording such as:

```text
Adapted from Tanager STAC Data...
```

## Important limitation

The Tanager open-data terms do not automatically apply to:

- PlanetScope
- Planet VHR
- Competition-provided imagery
- gIQ-hosted imagery
- Arab Satellite 813
- EnMAP
- Other commercial imagery

Each source requires a separate licence check.

All results must also be recorded in:

```text
docs/data_licence_and_security_log.md
```

---

# 19. Repository Timeline and Official-Platform Conflict

## Repository README information

The repository README lists:

```text
PoC submission: 26 October 2026
```

It also describes a broader programme structure extending into
November 2026 and early 2027.

## Team platform evidence

The current official hackathon platform information previously captured
by the team states:

```text
PoC submission deadline:
11 October 2026 at 11:59 PM
in the team creator's local timezone
```

## THABAT decision

Use:

```text
11 October 2026
```

as the operational submission deadline unless the organizers provide a
new official written update.

Do not delay work based on the later date shown in the repository.

## Required action

Person 1 should:

- Keep screenshots of both sources.
- Ask the organizers for clarification if necessary.
- Record any written answer.
- Update the project timeline only after official confirmation.

---

# 20. Evaluation-Criteria Conflict

## Repository README criteria

The repository lists five broad criteria:

1. Impact
2. Creativity
3. Validity
4. Relevance
5. Presentation

It also states that hyperspectral use receives additional consideration.

## Current official platform criteria

The competition platform previously captured by the team lists seven
PoC criteria:

1. Problem definition
2. Technical soundness
3. Use of hyperspectral / EO data
4. Product and delivery model
5. Innovation
6. Impact and strategic alignment
7. Business viability

## THABAT decision

The team should use the seven current platform criteria when:

- Planning deliverables
- Designing the pitch deck
- Reviewing the PoC
- Preparing judge answers
- Checking submission completeness

The repository criteria can be treated as broad supporting guidance.

---

# 21. Theme-Name and Numbering Differences

The repository refers to:

```text
Theme 2 — Urban Expansion, Land Use Change & Heat Risk
```

The current competition platform may use a broader title such as:

```text
Sustainable Urban Planning & Smart Cities
```

or a different displayed theme number.

## THABAT decision

Use the exact theme name shown on the current official registration and
submission platform.

Use the repository notebook according to technical relevance rather
than theme number alone.

---

# 22. Quick-Start Filename Inconsistency

The repository structure lists:

```text
00_data_exploration_starter.ipynb
```

Another README section says:

```text
00_EO_data_quickstart_notebook.ipynb
```

## THABAT decision

Before running anything:

1. Open the live repository.
2. Open `notebooks/`.
3. Record the exact filename that exists.
4. Use that filename in all team instructions.
5. Do not create a duplicate notebook only to match the README wording.

## Status

```text
Exact quick-start filename verified: NOT YET
```

---

# 23. Current THABAT Repository Workflow

The recommended order is:

## Stage 1 — Read

1. Read the repository README.
2. Read the Tanager data guide.
3. Read the STAC collection map.
4. Review the spectral-indices reference.

## Stage 2 — Open

1. Open the real starter notebook.
2. Open the land-use/urban notebook.
3. Confirm all dependencies.
4. Confirm the first notebook cells run.

## Stage 3 — Learn

1. Understand STAC search.
2. Understand scene IDs and assets.
3. Understand surface reflectance.
4. Understand wavelength metadata.
5. Understand quality masks.
6. Understand HDF5 data access.

## Stage 4 — Adapt

1. Import THABAT AOI-A.
2. Import THABAT AOI-B.
3. Search available scenes.
4. Select one real scene.
5. Record it in the data manifest.
6. Store raw files in private Google Drive.
7. Build road-specific outputs.

## Stage 5 — Prove

1. Produce one map.
2. Produce one metadata table.
3. Produce one composite.
4. Plot road and non-road spectra.
5. Document limitations.
6. Make a USE / CONDITIONAL / REJECT decision.

---

# 24. Required THABAT Outputs from Repository Exploration

## Person 1

Must save:

- Repository URL
- README notes
- Setup instructions
- Notebook order
- Licence notes
- Conflict notes
- Access blockers

## Person 2

Must save:

- Real quick-start notebook run
- Real theme-notebook run
- Hyperspectral scene inventory
- Scene footprints
- Wavelength list
- Sample spectra
- Quality notes
- USE / CONDITIONAL / REJECT decision

## Person 3

Must save:

- Sentinel-2 access workflow
- Scene IDs and dates
- Quality-mask output
- RGB output
- Multispectral baseline plan

## Person 4

Must save:

- Landsat access workflow
- Temperature-processing notes
- Heat-context result
- WorldCover context
- Resolution and interpretation limitations

## Person 5

Must save:

- VHR access status
- Road-mask method
- Pixel-purity method
- Licence and public-display notes
- Validation candidate map

---

# 25. Evidence Requirements

The repository-review task is not complete unless the team can show:

- A screenshot of the official repository root
- A screenshot of the `notebooks/` folder
- The real quick-start filename
- The real urban-theme filename
- The repository commit or branch if visible
- A notebook opened successfully
- A notebook cell executed successfully
- At least one output
- Any errors encountered
- The environment used
- The access date
- Licence notes

The statement:

> I read the repository.

is not enough evidence by itself.

---

# 26. Security Rules When Using the Repository

Do not place the following inside a notebook or GitHub:

- Planet API key
- gIQ password
- Access token
- Session cookie
- Signed download URL
- Private account email
- Commercial imagery
- Restricted competition data
- Personal information

Use environment variables for secrets.

Example placeholder only:

```python
import os

PLANET_API_KEY = os.getenv("PLANET_API_KEY")
```

Never hard-code a real key.

If the notebook asks for authentication:

1. Stop.
2. Check the official documentation.
3. Use a secure environment variable or platform secret.
4. Do not share the credential in screenshots or AI conversations.

---

# 27. Repository Issues and Questions to Clarify

The following items require clarification or verification:

- Which quick-start filename is correct?
- Is the repository fully current?
- Which deadline is current?
- Which judging criteria are current?
- Is gIQ access active for THABAT?
- Where are the preparatory-training materials?
- Can the team display Planet VHR screenshots publicly?
- Can competition-provided imagery be used in GitHub?
- What are the Satellite 813 storage and publication rules?
- Which notebook is officially recommended for the current urban theme?
- Are there updated notebooks not yet reflected in the README?

---

# 28. Current Repository Review Status

```text
Official repository located: Yes
Repository URL recorded: Yes
README reviewed: Yes
Repository purpose understood: Yes
Data providers identified: Yes
Relevant theme notebook identified: Yes
Setup instructions recorded: Yes
Known Titiler issue recorded: Yes
Tanager data structure recorded: Yes
Tanager wavelength key recorded: Yes
Water-vapour windows recorded: Yes
Repository code licence recorded: Yes
Tanager attribution requirement recorded: Yes
Repository deadline conflict recorded: Yes
Evaluation-criteria conflict recorded: Yes
Quick-start filename conflict recorded: Yes
Live notebook folder inspected: Not yet
Exact quick-start filename verified: Not yet
Quick-start notebook opened: Not yet
Quick-start notebook run successfully: Not yet
Theme notebook opened: Not yet
Theme notebook run successfully: Not yet
gIQ access confirmed: Not yet
Preparatory materials visible: Not yet
```

---

# 29. Immediate Next Actions

| Task | Owner | Status |
|---|---|---|
| Open the live official repository | Person 1 / Person 2 | Pending |
| Open the `notebooks/` folder | Person 1 / Person 2 | Pending |
| Confirm the actual quick-start filename | Person 1 | Pending |
| Download or open the starter notebook | Person 2 | Pending |
| Run setup cells | Person 2 | Pending |
| Save first successful output | Person 2 | Pending |
| Open the urban-theme notebook | Person 2 | Pending |
| Record all errors | Person 2 | Pending |
| Update repository notes with actual filenames | Person 1 | Pending |
| Update licence log | Assigned owners | Ongoing |
| Confirm gIQ and training access | Person 1 | Blocked / awaiting organizers |

---

# 30. Final Repository-Use Rule

The repository is a starter resource, not the finished THABAT solution.

The team may use it to learn:

- Data access
- STAC
- HDF5
- Wavelengths
- Quality masks
- Spectral indices
- Mapping
- Spectral plots

The team must still create original THABAT work for:

- Road selection
- Pavement masking
- Pixel purity
- Road spectra
- Matched references
- Anomaly detection
- Confidence
- Validation
- Inspection priority
- Dashboard
- Business logic

---

# 31. Final Summary

The official repository gives THABAT a practical starting point for
learning hyperspectral Earth-observation workflows.

Its strongest value to THABAT is:

- Explaining STAC access
- Demonstrating Tanager HDF5 use
- Showing how wavelengths are read
- Providing quality-mask examples
- Providing Sentinel-2 examples
- Providing urban and impervious-surface context
- Providing starter visualisation code

Its main limitation is:

> It does not contain a road-health or pavement-condition solution.

THABAT must build the road-specific scientific and product layers
independently and validate them responsibly.

---

# 32. Person 1 Sign-Off

```text
Document owner: Dana Alhammadi
Role: Person 1 — Team Lead / Integration Lead
Initial review date: 2026-09-20
Repository notes status: COMPLETE AS A DESK REVIEW
Notebook execution status: PENDING
Next review: After the quick-start and urban notebooks are opened
```
