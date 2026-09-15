# This repository contains the code, source data, editable figure files, and summary materials supporting the manuscript


## Repository contents

```text
.
├── README.md
├── Data_and_Code_Summary.xlsx
├── code/
│   ├── Fig1.m
│   ├── Fig2a.m
│   ├── Fig2a.xlsx
│   ├── Fig2b.m
│   ├── Fig3a.py
│   ├── Fig3b.py
│   ├── Fig4a.py
│   ├── Fig4a.xlsx
│   ├── Fig4b_4c.m
│   ├── Fig5a.m
│   ├── Fig6a.py
│   ├── Fig6a.xlsx
│   ├── Fig6b.py
│   ├── Fig6b.xlsx
│   ├── SupplementaryFig1.vsdx
│   ├── SupplementaryFig2.py
│   ├── SupplementaryFig3.pptx
│   ├── SupplementaryFig4a.m
│   ├── SupplementaryFig4a.xlsx
│   ├── SupplementaryFig4b.m
│   ├── SupplementaryFig4b.xlsx
│   ├── SupplementaryFig5.xlsx
│   ├── SupplementaryTable9.xlsx
│   └── Table 1.xlsx
└── source data/
    ├── Source Data Fig.1.xlsx
    ├── Source Data Fig.2a.xlsx
    ├── Source Data Fig.2b.xlsx
    ├── Source Data Fig.3a.xlsx
    ├── Source Data Fig.3b.xlsx
    ├── Source Data Fig.4a.xlsx
    ├── Source Data Fig.4b_4c.xlsx
    ├── Source Data Fig.5a.xlsx
    ├── Source Data Fig.6a.xlsx
    ├── Source Data Fig.6b.xlsx
    ├── Source Data SupplementaryFig.2.xlsx
    ├── Source Data SupplementaryFig.4a.xlsx
    ├── Source Data SupplementaryFig.4b.xlsx
    └── Source Data for 294 models.xlsx
```

`Data_and_Code_Summary.xlsx` consolidates the repository inventory, figure-to-file map, principal numerical results, source data, and code requirements.

## Quick start

### Python figures

A Python 3.10 or newer environment is recommended.

```bash
python -m venv .venv
source .venv/bin/activate          # macOS/Linux
# .venv\Scripts\activate           # Windows

pip install numpy pandas matplotlib openpyxl prophet pycirclize
cd code
```

Run the Python scripts from the `code/` directory because they use relative input and output paths:

```bash
python Fig3a.py
python Fig3b.py
python Fig4a.py
python Fig6a.py
python Fig6b.py
python SupplementaryFig2.py
```

The scripts request the Arial font. If Arial is unavailable, the plotting library will substitute another installed font, which can slightly change text placement.

### MATLAB figures

MATLAB R2021a or later is recommended because the scripts use functions such as `readtable`, `datetime`, `yyaxis`, `tiledlayout`, and `exportgraphics`.

From MATLAB:

```matlab
cd code
run('Fig1.m')
run('Fig2a.m')
run('Fig2b.m')
run('Fig4b_4c.m')
run('Fig5a.m')
run('SupplementaryFig4a.m')
run('SupplementaryFig4b.m')
```


## Figure and table reproduction map

| Target | Code or editable source | Input data | Main output or function |
|---|---|---|---|
| Main Fig. 1 | `code/Fig1.m` | Values are embedded; full-precision values are in `source data/Source Data Fig.1.xlsx` | Seven-phase radial comparison; writes `figure.png` |
| Main Fig. 2a | `code/Fig2a.m` | `code/Fig2a.xlsx`; equivalent source data in `Source Data Fig.2a.xlsx` | Release date and computing-demand ellipses by producer region |
| Main Fig. 2b | `code/Fig2b.m` | Regional values are embedded; shares are supplied in `Source Data Fig.2b.xlsx` | Regional absolute, stacked, and percentage-stacked bars |
| Main Fig. 3a | `code/Fig3a.py` | Historical series embedded; final series in `Source Data Fig.3a.xlsx` | `Fig3a.svg`, diagnostic plots, and `monthly_diff_all_scenarios.xlsx` |
| Main Fig. 3b | `code/Fig3b.py` | Historical visit series embedded; final series in `Source Data Fig.3b.xlsx` | `Fig3b.svg` |
| Main Fig. 4a | `code/Fig4a.py` | `code/Fig4a.xlsx`; full source in `Source Data Fig.4a.xlsx` | `Fig4a.svg` |
| Main Fig. 4b–c | `code/Fig4b_4c.m` | Values embedded; full source in `Source Data Fig.4b_4c.xlsx` | Annual phase emissions and shares |
| Main Fig. 5 | `code/Fig5a.m` | Values embedded; full source in `Source Data Fig.5a.xlsx` | One-at-a-time parameter effects |
| Main Fig. 6a | `code/Fig6a.py` | `code/Fig6a.xlsx` | `Fig6a.svg` |
| Main Fig. 6b | `code/Fig6b.py` | `code/Fig6b.xlsx` | `Fig6b.svg` |
| Supplementary Fig. 1 | `code/SupplementaryFig1.vsdx` | Editable Visio source | System-boundary diagram |
| Supplementary Fig. 2 | `code/SupplementaryFig2.py` | `code/Fig4a.xlsx` | `FigS2.svg` |
| Supplementary Fig. 3 | `code/SupplementaryFig3.pptx` | Editable PowerPoint source | Innovating–Shifting–Disclosing–Rolling management cycle |
| Supplementary Fig. 4a | `code/SupplementaryFig4a.m` | `code/SupplementaryFig4a.xlsx` | Pareto curve for computing demand |
| Supplementary Fig. 4b | `code/SupplementaryFig4b.m` | `code/SupplementaryFig4b.xlsx` | Pareto curve for website visits |
| Supplementary Fig. 5 | `code/SupplementaryFig5.xlsx` | Data and charts are contained in the workbook | Curve-fitting comparison |
| Supplementary Table 9 | `code/SupplementaryTable9.xlsx` | Data and formulas are contained in the workbook | Six-month out-of-sample comparison and MSE values |
| Table 1 | `code/Table 1.xlsx` | Data and formulas are contained in the workbook | Normalized mitigation and exacerbation sensitivity |

## Main source datasets

### `Source Data for 294 models.xlsx`

This is the core model-level dataset. It contains:

| Field | Description |
|---|---|
| `Model` | Model or model-version name |
| `Publication date` | Release/publication date |
| `Parameters` | Reported model parameter count where available |
| `Training compute (FLOPs)` | Publicly documented training-compute estimate |
| `Country/Region` | Producer-attributed country or region |

The 294 models span 30 October 2019 to 31 December 2025. The training-compute distribution is highly right-skewed; the top 100 models account for approximately 95.34% of total documented computing demand.

### Figure-specific source files

The files named `Source Data Fig.*.xlsx` contain the numerical values plotted in the corresponding main figures. The supplementary source files provide the annual nine-scenario series and the Pareto distributions.

Important unit conventions are:

- Carbon emissions: t CO₂-eq or Mt CO₂-eq, as indicated in each header.
- Training compute: FLOPs, or \(10^{26}\) FLOPs in the projection workbooks.
- Online visits: billion visits per month in `Source Data Fig.3b.xlsx`; million visits in `Source Data SupplementaryFig.4b.xlsx`.
- Shares: stored as fractions in several source files and displayed as percentages in the manuscript.
- Dates: stored as Excel dates and should be displayed as `YYYY-MM-DD`.

## Method-specific code notes

### Computing-power demand projection (`Fig3a.py`)

The script:

1. constructs a cumulative monthly computing-demand series;
2. fits a cubic trend;
3. fits a first-order autoregressive process to residuals;
4. applies scenario-specific tipping points;
5. updates post-tipping monthly demand using a rolling 12-month mean;
6. runs 30 deterministic Monte Carlo trials using seeds 0–29; and
7. reports mean paths and 5th–95th percentile simulation intervals.

### Online-visit projection (`Fig3b.py`)

The script uses Prophet to decompose the monthly visit series into trend and annual-seasonal components. It then applies a staged growth pattern and scenario factors. Thirty seeded simulations are used to construct the reported mean trajectories and percentile intervals.

### Emission trajectories (`Fig4a.py` and `SupplementaryFig2.py`)

Both scripts read the same annual nine-scenario workbook. `Fig4a.py` cumulatively sums annual emissions, while `SupplementaryFig2.py` plots annual values directly.

### Chord diagrams (`Fig6a.py` and `Fig6b.py`)

The scripts read parameter–phase matrices and divide the supplied t CO₂-eq values by \(10^6\) before plotting them in Mt CO₂-eq.


## Summary workbook

`Data_and_Code_Summary.xlsx` contains:

- an overview dashboard and key numerical results;
- a complete repository inventory with SHA-256 hashes;
- a figure/table reproduction map;
- the 294-model dataset;
- consolidated source data for main and supplementary figures;
- normalized sensitivity calculations;
- curve-fitting and holdout-test data; and
- Python/MATLAB requirements.

The workbook is intended as a navigation and verification aid. The individual files in `source data/` remain the figure-specific source records.

## Data and code availability

The public repository is:

<https://github.com/PJ6501/Emission>

## Contact

**Peng Jiang**  
Email: pengjiang@scu.edu.cn
