# Menezes-Almeida et al. (2027) — data and analysis code

Apatite fission-track (AFT) data and Python code used in:

> Menezes-Almeida, G., et al. (2027). *[title]*. Gondwana Research. https://doi.org/[DOI]

## Contents

| File / folder | Content |
|---|---|
| `Menezes-Almeida_et_al_2027_AFT_code.ipynb` | Analysis code, one section per graph or table, in the order they are cited in the article |
| `data/AFT_data_Menezes-Almeida_2027.xlsx` | **All AFT data in one workbook** (see below) |
| `data/QTQt_runs/` | For each modelled sample, the QTQt run settings (`.run`) and prediction file (`*_pred.txt`) of the model used in the article. The QTQt chain files are not included (see below) |
| `data/QTQt_expected_paths/` | Expected t–T paths exported from QTQt (`TFS-xxx expected Tt file.txt`) |
| `data/shapes/` | Outline of the Recôncavo–Tucano–Jatobá rift (`RTJ_rift`), study area (`study_area`) and 1:5,000,000 geomorphological map of Brazil, IBGE (`geomorphology_IBGE_5M`, used for the coastline) |

### The data workbook

| Sheet | Content |
|---|---|
| `README` | Description of the sheets |
| `Samples` | One row per sample: coordinates (SIRGAS 2000; geographic and UTM 24S), elevation, lithology, province, side of the RTJ rift (W/E), dosimeter density ρd and Nd |
| `Grain counts` | Single-grain Ns, Ni, counted area, ρs and ρi (540 grains, 27 samples) |
| `Track lengths` | Horizontal confined track lengths and angle to the c-axis |
| `Dpar` | Etch-pit diameters |
| `Literature` | Compilation of published AFT data (Supplementary Table S1) |

Notes: TFS-021 has no valid length data (the length sheet of the original counting file is a copy of TFS-082) and is not listed in `Track lengths`; it is not used in length-based plots or in the thermal modelling. TFS-018, TFS-029 and TFS-046 have fewer than 50 confined tracks and were not modelled.

## Notebook sections

| # | Section | Article |
|---|---|---|
| 0 | Setup (paths and data readers) | — |
| 1 | Position of the published samples relative to the RTJ rift | Supplementary Table S1 |
| 2 | Radial plots and central ages | Supplementary Fig. S1 |
| 3 | Age–elevation plot | Supplementary Fig. S2 |
| 4 | Confined track-length histograms | Supplementary Fig. S3 |
| 5 | Breakpoint segmentation of the expected paths | Table 3; Supplementary Fig. S5 |
| 6 | Posterior cooling rates | Table 3; Supplementary Fig. S5 |
| 7 | Half-boomerang plot | Fig. 6 |
| 8 | This study versus published data in the study area | Fig. 7 |
| 9 | Age versus distance to the coast and to the rift | Fig. 8 |
| 10 | Expected t–T paths west and east of the rift | Fig. 9 |
| 11 | Reheating test | Supplementary Table S2 |

Maps, conceptual figures and Figs. 2 and 3 are drawings by the authors and are not reproduced by the code.

## QTQt chain files

The QTQt chain files (all thermal histories sampled by the Markov chain) are not included in this record. They are available from the corresponding author on request. Without them, sections 6 (posterior cooling rates) and 11 (reheating test) cannot be run; their results are given in Table 3 and Supplementary Table S2 of the article. To run these two sections, place each chain file in the sample's sub-folder of `data/QTQt_runs/`. All other sections run with the files in this record.

## How to run

```
pip install numpy scipy pandas matplotlib openpyxl pyshp shapely pyproj adjustText
jupyter notebook Menezes-Almeida_et_al_2027_AFT_code.ipynb
```

Run all cells. Each section writes its script to a `.py` file; the last cell runs them in the required order and skips sections 6 and 11 if the chain files are missing (sections 3 and 8 import the module of section 7; section 6 uses the output of section 5). Section 1 writes the column `RTJ_position` of sheet `Literature`. Results are written to `output/`.

## Citation and licence

Please cite the article above and this record: https://doi.org/[Zenodo DOI]. Code released under the MIT licence.
