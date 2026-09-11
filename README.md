# Faixa Sergipana AFT thermochronology — analysis code

Python code used to process apatite fission-track (AFT) thermochronology
data and generate a subset of the figures and tables of:

> Menezes Almeida et al. (in prep.). *[manuscript title]*. Submitted to
> Gondwana Research.

This study presents 27 new AFT samples from the Sergipano Belt–Tucano
Basin boundary (NE Brazil), testing the Sergipe Microplate hypothesis of
Szatmari and Milani (1999) through apatite fission-track thermochronology,
combined with a reinterpretation of published AFT, structural, geophysical
and geological data from the region.

## What is (and isn't) in this repository

**This repository contains only the analysis code** (one Jupyter
notebook). It does **not** contain the underlying data.

The input data used by this code — the new AFT sample analytical results,
track-length measurements, QTQt thermal-history modelling outputs, and
literature compilations — are published separately as the article's
Supplementary Data (Tables S1–S3, Figures S1–S6): **[DOI / link to be
added]**.

To reproduce an analysis, obtain the relevant file(s) from the
Supplementary Data and set the corresponding input path/filename declared
at the top of that section (e.g. `INPUT_FILE`, `INPUT_DIR`) accordingly.

## Contents

`AFT_analysis_notebook.ipynb` — one notebook, organised in 7 sections:

| # | Section | Produces |
|---|---|---|
| 1 | Setup | shared imports, font/PDF configuration |
| 2 | Phanerozoic regional context timeline | Figure 2 (main text) |
| 3 | Mean track length (MTL) histograms per sample | Supplementary Fig. S2 |
| 4 | AFT age vs. elevation | Supplementary Fig. S3 |
| 5 | Boomerang plot (MTL vs. central age), measured and projected | Supplementary Fig. S4 |
| 6 | Expected t–T paths by crustal domain and MTL cluster | Figure 5 (main text) |
| 7 | QTQt cooling-rate / exhumation-rate calculation, per sample and combined | Supplementary Table S3, Fig. S6 |

Each section starts with a markdown cell naming the figure/table it feeds
into the manuscript.

## Requirements

Python ≥ 3.9, with:

```
pandas
numpy
matplotlib
scipy
openpyxl
```

Install with:

```
pip install pandas numpy matplotlib scipy openpyxl
```

## How to run

1. Obtain the Supplementary Data files this notebook expects (see table
   above; the expected input file/column format is set by the variables at
   the top of each section).
2. Open `AFT_analysis_notebook.ipynb` in Jupyter.
3. In each section, edit the input path/filename variable(s) declared near
   the top of the cell (e.g. `INPUT_FILE`, `INPUT_DIR`) to point to your
   local copy of the corresponding Supplementary Data file.
4. Run the section's cell(s).

Sections are independent of each other and can be run in any order.

## Citation

If you use this code, please cite the manuscript above and this
repository's Zenodo record: **[DOI to be added]**.

## License

[choose a license, e.g. MIT — add LICENSE file]
