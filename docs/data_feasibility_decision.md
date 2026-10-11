# THABAT Data Feasibility Decision

## 1. Decision status

**Current recommendation: CONDITIONAL GO**

The current evidence supports a defensible thermal-screening proof of concept for selected UAE road corridors. The project should proceed with the current reproducible baseline while treating multisource fusion, hyperspectral availability, higher-resolution imagery, and independent engineering validation as next-stage work.

This decision does **not** mean that THABAT can currently prove pavement deterioration or environmental causation.

---

## 2. Current primary evidence

### AOI-A - Saih Al Salam Street / D42

**Status: USE**

Current evidence includes:

- pre-segmented road geometry with segments A-001 to A-005;
- Landsat 9 Collection 2 Level-2 surface-temperature data;
- a corrected Landsat `ST_B10` conversion;
- ArcGIS Pro segment-level thermal statistics;
- reproducible thermal screening in `notebooks/02_main_analysis.ipynb`;
- Sentinel-2 contextual comparison between 19 September and 4 October 2026, with no obvious visual road-surface change detected in the tested views.

### AOI-B - Fujairah study area

**Status: CONDITIONAL / LOW SUPPORT**

Current evidence includes:

- pre-segmented road geometry with segments B-001 to B-004;
- ArcGIS Pro segment-level thermal statistics;
- relative thermal screening results.

The current AOI-B statistics contain only about 2-3 valid thermal pixels per segment. Therefore AOI-B results are considered **low-support preliminary evidence** and should not be presented as equivalent-strength evidence to AOI-A.

The included Landsat raster in `data/sample_input/Landsat_ST_AOI_Clip.tif` is **AOI-A only** and is not used as AOI-B Landsat coverage.

---

## 3. Data-source decisions

| Source | Current decision | Role |
|---|---|---|
| Landsat 9 C2 L2 surface temperature | USE for AOI-A | Thermal context and segment screening |
| Sentinel-2 L2A | USE as contextual evidence | Multispectral surface/context comparison |
| EnMAP hyperspectral | CONDITIONAL | Potential spectral/material feature source if suitable UAE coverage is confirmed |
| Planet Tanager open data | CONDITIONAL | Potential hyperspectral backup/comparison if coverage and terms are suitable |
| ECOSTRESS | CONDITIONAL | Potential thermal enhancement if appropriate coverage/product access is confirmed |
| VHR imagery | CONDITIONAL | Fine road/pavement context only when legally shareable |
| Rainfall/environmental history | NEXT INPUT | Temporal/environmental context and future causal testing |
| Satellite 813 | FUTURE / CONDITIONAL | Potential higher-resolution or complementary evidence if suitable UAE data are provided with usable access and redistribution rights |

The project does not claim use of a dataset merely because its portal or catalogue exists. Product identity, coverage, quality and sharing status must be verified.

---

## 4. Hyperspectral decision

Hyperspectral remains strategically useful because many narrow wavelength bands may provide richer material/surface information than a small number of broad multispectral bands.

However, the current project evidence does **not** confirm a suitable hyperspectral acquisition over the selected UAE road AOI that is ready for the final reproducible PoC.

Therefore:

**Do not fabricate hyperspectral results.**

The current presentation and repository should describe hyperspectral as a **conditional/future capability** until an appropriate real product is opened, checked and processed.

---

## 5. High-resolution imagery decision

Fine pavement-condition assessment requires spatial detail beyond what the current Sentinel-2 and Landsat layers can reliably provide.

VHR imagery is therefore strategically desirable for future validation and road/pavement representation.

However, a VHR source must be both:

1. technically suitable for the selected road corridor; and
2. legally usable for the public submission/repository.

Until both conditions are verified, VHR remains **CONDITIONAL**.

---

## 6. Rainfall and environmental data decision

Rainfall/event history has not been integrated into the current thermal score.

It is a planned next input for a stronger temporal analysis:

```text
Rain/event date
      +
satellite observation dates
      +
road segment thermal/spectral history
      +
road-condition observations
      ↓
stronger environmental-response analysis
```

The current PoC must not claim that rainfall caused pavement deterioration.

---

## 7. Satellite 813 future opportunity

**Satellite 813 is a future opportunity, not a current evidence source.**

If the hackathon provides suitable Satellite 813 data covering the selected UAE road corridors, with appropriate access and redistribution rights, those data could strengthen THABAT by providing an additional high-resolution or complementary observation layer.

Any future Satellite 813 integration should first verify:

- exact product/scene;
- acquisition date;
- UAE AOI coverage;
- spatial/spectral characteristics;
- quality;
- licence and redistribution rights;
- compatibility with the current road-segment workflow.

---

## 8. Current safe claim

> THABAT uses satellite-derived environmental evidence to screen road segments and prioritize locations for physical inspection. Thermal anomalies provide contextual evidence; they do not independently establish pavement damage or causation.

---

## 9. Main technical risks

1. **Spatial resolution / mixed pixels**  
   Thermal and multispectral pixels may include road and surrounding terrain.

2. **Low support in AOI-B**  
   Current AOI-B segment statistics contain only 2-3 valid thermal pixels per segment.

3. **Temporal limitation**  
   A single thermal date cannot establish long-term deterioration.

4. **No independent engineering ground truth**  
   The current PoC does not have independent field labels that prove a segment is damaged.

5. **Hyperspectral coverage uncertainty**  
   Suitable UAE road coverage has not yet been confirmed for the current selected AOIs.

6. **VHR licensing / access**  
   High-resolution imagery cannot be added to a public repository until redistribution rights are confirmed.

---

## 10. Immediate next actions

### Before submission

- confirm the final AOI-B geometry uses B-001 to B-004;
- run `notebooks/02_main_analysis.ipynb` from a fresh kernel;
- confirm all cells run without errors;
- commit the real generated example output to `results/example_output.png`;
- verify README links and repository paths;
- test the public GitHub link in a logged-out browser;
- confirm no credentials or restricted imagery are committed.

### After the PoC

- integrate rainfall/event history;
- add multispectral feature engineering;
- add suitable hyperspectral data when confirmed;
- add legally usable VHR data;
- validate against field/engineering observations;
- evaluate stronger baseline/ML models only after the evidence pipeline is stable.

---

## 11. Final decision

**CONDITIONAL GO**

The thermal-screening workflow is sufficiently concrete to demonstrate a reproducible PoC, provided that claims remain limited to screening and prioritisation. Stronger claims about pavement deterioration, rainfall causation, or predictive performance should wait for multi-date data, better spatial support, and independent validation.
