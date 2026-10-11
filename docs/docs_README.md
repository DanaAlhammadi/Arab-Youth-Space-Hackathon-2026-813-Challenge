# THABAT Documentation

This folder contains the supporting documentation for the THABAT hackathon proof of concept.

THABAT is a satellite-based road resilience screening concept that uses Earth-observation evidence to help road and infrastructure teams decide **where to inspect first**. The current reproducible PoC focuses on thermal screening of pre-segmented UAE road corridors.

## Documentation

### `data_licence_and_security_log.md`
Records:
- data-source licensing and sharing status;
- attribution requirements;
- public vs. restricted data handling;
- GitHub security checks;
- unresolved `VERIFY` or `CONDITIONAL` items.

### `data_feasibility_decision.md`
Records the team's data decisions:
- selected and backup data sources;
- AOI/data coverage decisions;
- licensing and access constraints;
- technical limitations;
- safe project claims;
- next actions.

### `hackathon_repository_notes.md`
Explains:
- repository organisation;
- data and notebook roles;
- reproducibility expectations;
- how the judging workflow is intended to work;
- what should and should not be committed to GitHub.

## Repository workflow

The main reproducible analysis is:

`notebooks/02_main_analysis.ipynb`

It uses the small sample inputs under:

`data/sample_input/`

and writes generated outputs to:

`results/`

The notebook is designed to run either locally with Jupyter or in Google Colab from the public GitHub repository.

## Data handling rule

Only data that are legally shareable and appropriate for the public repository should be committed.

Do **not** commit:
- API keys or access tokens;
- passwords;
- signed/private URLs;
- private account information;
- restricted raw imagery;
- any dataset whose redistribution rights have not been verified.

Where rights or coverage are unresolved, the documentation keeps the source marked `VERIFY` or `CONDITIONAL` rather than assuming permission.

## Current evidence scope

The current PoC demonstrates:

- AOI-A Landsat thermal context;
- AOI-A and AOI-B ArcGIS-derived segment statistics;
- transparent relative thermal screening;
- Sentinel-2 contextual comparison;
- explicit reporting of data-support limitations.

The included Landsat raster is **AOI-A only**. It must not be interpreted as Landsat coverage of AOI-B.

AOI-B currently has only a small number of valid thermal pixels per segment, so its thermal screening evidence is considered low-support.

## Scientific interpretation

THABAT is a **screening and prioritisation layer**, not an engineering diagnosis.

Thermal anomalies do not independently prove:
- pavement damage;
- structural failure;
- rainfall causation;
- long-term deterioration.

Future validation is expected to include multi-date observations, rainfall/environmental history, higher-resolution imagery where legally usable, engineering records, and field inspection.

## Final repository structure

```text
THABAT/
├── README.md
├── requirements.txt
├── notebooks/
│   └── 02_main_analysis.ipynb
├── data/
│   ├── data_manifest.csv
│   ├── study_areas/
│   └── sample_input/
├── results/
└── docs/
    ├── README.md
    ├── data_licence_and_security_log.md
    ├── data_feasibility_decision.md
    └── hackathon_repository_notes.md
```
