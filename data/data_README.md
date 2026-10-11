# THABAT Sample Data

This folder contains the small sample inputs used by the reproducible THABAT notebook.

## Files

### `AOI_A_Segment_LST_Stats_excel.xls`
ArcGIS Pro export containing segment-level thermal statistics for AOI-A.

Current segments:

- A-001
- A-002
- A-003
- A-004
- A-005

The table is used by `notebooks/02_main_analysis.ipynb` to calculate the relative thermal-screening results for AOI-A.

### `aoiB_Segment_stat.xls`
ArcGIS Pro export containing segment-level thermal statistics for AOI-B.

Current segments:

- B-001
- B-002
- B-003
- B-004

The current table contains a small number of valid thermal pixels per segment, so AOI-B is treated as low-support thermal evidence in the notebook.

### `Landsat_ST_AOI_Clip.tif`
Small clipped Landsat surface-temperature raster used for **AOI-A only**.

The notebook applies the project conversion:

`Kelvin = DN × 0.00341802 + 149.0`

then:

`°C = Kelvin − 273.15`

DN `0` is treated as fill/no-data.

**Important:** this raster must not be described as Landsat coverage of AOI-B.

## Data role

The sample package is intended to let a judge reproduce the notebook without downloading full satellite scenes.

The workflow is:

```text
Sample data
    ↓
02_main_analysis.ipynb
    ↓
Quality checks
    ↓
Segment thermal statistics
    ↓
Relative thermal screening
    ↓
Results in results/
```

## Reproducibility

Run:

```text
notebooks/02_main_analysis.ipynb
```

The notebook expects this folder to exist at:

```text
data/sample_input/
```

and writes generated outputs to:

```text
results/
```

No Google Drive mount or private credential is required.

## Sharing and security

Only small, repository-safe sample files should be stored here.

Do not add:

- API keys;
- access tokens;
- passwords;
- signed or private URLs;
- restricted raw satellite scenes;
- data that cannot legally be redistributed.

For provenance and licence/sharing status, see:

```text
data/data_manifest.csv
docs/data_licence_and_security_log.md
```

## Interpretation

These files support a **screening and prioritisation PoC**.

They do not, by themselves, prove:

- pavement damage;
- structural failure;
- rainfall causation;
- long-term deterioration.

Thermal anomalies should be interpreted as evidence for further inspection, not as an engineering diagnosis.
