# Weather Regime Diversity, Transitions, and Trends using Hexagonal Self-Organizing Maps

This repository documents the dataset associated with the preprint:

**Weather Regime Diversity, Transitions, and Trends using Hexagonal Self-Organizing Maps**  
Luke Wichrowski, Jhayron S. Pérez-Carrasquilla, and Maria J. Molina (July 25, 2025)

Preprint (ESS Open Archive): https://doi.org/10.22541/essoar.175346129.95426517/v1
Zenodo record: https://zenodo.org/records/18284214

---

## Overview

Persistent atmospheric circulation patterns (“weather regimes”) strongly modulate surface weather and extremes. This dataset supports the analyses in the accompanying preprint, which applies a hexagonal self-organizing map (SOM) framework to represent **North American weather regimes** using **500-hPa geopotential height (Z500) anomalies** over **1940–2023**.

The preprint introduces:
- A **hexagonal SOM lattice** designed to reduce geometric artifacts
- A **transition-based metric** to optimize the SOM for smoother regime-to-regime transitions

---

## Data source and preprocessing (from the preprint)

The underlying atmospheric data are derived from **ERA5** and include **daily averages of 500-hPa geopotential height (Z500)**. The preprint notes that ERA5 was used for its global coverage and long-term record.

Key preprocessing steps reported in the preprint include:

- Domain: **North America (20°N–80°N, 180°W–30°W)**
- Regridding: ERA5 regridded to a **1° × 1°** latitude–longitude grid (nearest-neighbor interpolation)
- Seasonal cycle removal: **60-day centered running mean** (by calendar day; 1940-01-01 to 2023-12-31)
- Low-pass filtering: **10-day Fourier low-pass filter** to emphasize subseasonal and longer variability
- Detrending: subtract a **3rd-degree polynomial fit** to the yearly time series of area-averaged anomalies
- Normalization: divide by a **60-day centered running mean of the standard deviation** (area-averaged)

ERA5 access location (as cited in the preprint):  
U.S. NSF NCAR Research Data Archive (RDA): https://doi.org/10.5065/D6X34W69

---

## What’s in this Zenodo record?

**This section should reflect the actual files shown on Zenodo** (recommended: copy/paste the filenames exactly from the Zenodo “Files” list).

Example structure (edit to match your record):

- `Z500Anoms_ERA5.nc` — (preprocessed ERA5 500-hPa GPH anomalies)
- `Z500Anoms_JRA3Q.nc` — (same but for JRA3Q)
- `Z500Anoms_NCEP_NCAR.nc` — (same but for NCEP/NCAR reanalysis)
- `df_labels_nocorrfilt_ERA5.csv` — (weather regime assignments)
- `df_labels_nocorrfilt_JRA3Q.csv` — (same but for JRA3Q)
- `df_labels_nocorrfilt_NCEP_NCAR.csv` — (same but for NCEP/NCAR reanalysis)
- `SOM40.p` — (pretrained SOM)

---

## Recommended citation

### Cite the preprint
If you use this dataset, please cite the associated preprint:

Wichrowski, L., Pérez-Carrasquilla, J. S., & Molina, M. J. (2025). *Weather Regime Diversity, Transitions, and Trends using Hexagonal Self-Organizing Maps* (preprint). ESS Open Archive. https://doi.org/10.22541/essoar.175346129.95426517/v1

### Cite the dataset
Please also cite the Zenodo dataset:

**Zenodo record:** https://zenodo.org/records/18284214  
(**DOI:** https://doi.org/10.5281/zenodo.18284214)

---

## Software and reproducibility

For full methodological details (SOM configuration, transition metric definition, and regime interpretation), refer to the preprint.
