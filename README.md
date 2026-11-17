# Menezes-Almeida et al. (2027) — data and analysis code

Apatite fission-track (AFT) data and Python code used in:

> Menezes-Almeida, G., et al. (2027). *[title]*. Gondwana Research. https://doi.org/[DOI]

## Contents

| File / folder | Content |
|---|---|
| `Menezes-Almeida_et_al_2027_AFT_code.ipynb` | Analysis code, one section per graph or table, in the order they are cited in the article |
| `data/AFT_counts/TFS-xxx.xlsx` | Single-grain counts and confined track lengths of each sample (as used by the code) |
| `data/Raw_AFT_data.xlsx` | Single-grain counts, confined track lengths, c-axis angles and Dpar of all samples (tables) |
| `data/QTQt_runs/` | QTQt prediction files (`*_pred.txt`), one sub-folder per sample. The QTQt chain files are not included (see below) |
| `data/QTQt_expected_paths/` | Expected t–T paths exported from QTQt (`TFS-xxx expected Tt file.txt`) |
| `data/samples.xlsx` | Sample coordinates (Lon, Lat; SIRGAS 2000), elevation and side of the rift (sheet `Samples`) |
| `data/literature_AFT_data.tsv` | Compilation of published AFT data (Supplementary Table S1) |
| `data/shapes/` | Outline of the Recôncavo–Tucano–Jatobá rift (`RTJ_rift`), study area (`study_area`) and 1:5,000,000 geomorphological map of Brazil, IBGE (`geomorphology_IBGE_5M`, used for the coastline) |

## Notebook sections

| # | Section | Article |
|---|---|---|
| 0 | Setup (paths) | — |
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

The QTQt chain files (all thermal histories sampled by the Markov chain) are large and are not included in this record. They are available from the corresponding author on request. Without them, sections 6 (posterior cooling rates) and 11 (reheating test) cannot be run; their results are given in Table 3 and Supplementary Table S2 of the article. To run these two sections, place each chain file in the sample's sub-folder of `data/QTQt_runs/`. All other sections run with the files in this record.

## How to run

```
pip install numpy scipy pandas matplotlib openpyxl pyshp shapely pyproj adjustText
jupyter notebook Menezes-Almeida_et_al_2027_AFT_code.ipynb
```

Run all cells. Each section writes its script to a `.py` file; the last cell runs them in the required order and skips sections 6 and 11 if the chain files are missing (sections 3 and 8 import the module of section 7; section 6 uses the output of section 5). Results are written to `output/`.

## Citation and licence

Please cite the article above and this record: https://doi.org/[Zenodo DOI]. Code released under the MIT licence.
