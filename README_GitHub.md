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
    └── Source Data for 294 LLMs.xlsx
```

`Data_and_Code_Summary.xlsx` consolidates the repository inventory, figure-to-file map, principal numerical results, source data, code requirements, integrity hashes, and quality-control notes in one workbook.

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

### `Source Data for 294 LLMs.xlsx`

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
4. applies scenario-specific tipping points at the end of 2028, 2030, and 2032;
5. updates post-tipping monthly demand using a rolling 12-month mean;
6. runs 30 deterministic Monte Carlo trials using seeds 0–29; and
7. reports mean paths and 5th–95th percentile simulation intervals.

The script is deterministic because the random seeds are fixed.

### Online-visit projection (`Fig3b.py`)

The script uses Prophet to decompose the monthly visit series into trend and annual-seasonal components. It then applies a staged growth pattern and scenario factors of 1.000, 1.229, and 1.458. Thirty seeded simulations are used to construct the reported mean trajectories and percentile intervals.

### Emission trajectories (`Fig4a.py` and `SupplementaryFig2.py`)

Both scripts read the same annual nine-scenario workbook. `Fig4a.py` cumulatively sums annual emissions, while `SupplementaryFig2.py` plots annual values directly.

### Chord diagrams (`Fig6a.py` and `Fig6b.py`)

The scripts read parameter–phase matrices and divide the supplied t CO₂-eq values by \(10^6\) before plotting them in Mt CO₂-eq.

## Reproducibility and quality-control notes

The repository was inspected for file completeness, cross-file consistency, and executable Python syntax. The summary workbook contains a detailed `QA_Log` sheet. The following version-specific points should be noted:

1. **Relative paths.** Run scripts from `code/`; otherwise, input workbooks may not be found and outputs may be written to an unexpected directory.
2. **Fixed submission cutoff.** `Fig2a.m` uses `datetime('today')` as the y-axis endpoint. To reproduce a figure fixed at the manuscript cutoff, replace that expression with a fixed date such as `datetime(2025,12,31)`.
3. **Pre-2020 model.** The full model dataset includes one model released in 2019 (AlphaStar). `Fig2a.m` intentionally filters observations before 2020.
4. **Embedded versus workbook data.** Several scripts embed data directly. For data reuse, the source-data workbooks should be treated as the full-precision records.
5. **Regional-share labels.** In the supplied `Source Data Fig.2b.xlsx`, the phase labels in the first column are offset by one row. `Data_and_Code_Summary.xlsx` transparently re-aligns the unchanged numerical values to the seven-phase order used in `Fig2b.m`.
6. **Supplementary Fig. 4b unit label.** `code/SupplementaryFig4b.xlsx` labels the vector as `visit(billion)`, whereas the MATLAB axis and source-data workbook use **million visits**. The summary workbook uses million visits.
7. **Fig. 3a transition row.** `Fig3a.py` writes zero for the initial December 2025 row in its generated differenced workbook because it is the transition baseline. The source-data workbook retains the observed December 2025 value. The generated and supplied projection values match from January 2026 onward.
8. **Software-specific outputs.** The MATLAB scripts that lack explicit export commands generate display figures only. The Visio and PowerPoint files are editable artwork rather than programmatically generated outputs.
9. **Third-party data.** The repository compiles data from public databases, papers, technical reports, and websites cited in the manuscript and Supplementary Information. Reuse of third-party data remains subject to the original providers' terms.

## Summary workbook

`Data_and_Code_Summary.xlsx` contains:

- an overview dashboard and key numerical results;
- a complete repository inventory with SHA-256 hashes;
- a figure/table reproduction map;
- the 294-model dataset;
- consolidated source data for main and supplementary figures;
- normalized sensitivity calculations;
- curve-fitting and holdout-test data;
- Python/MATLAB requirements; and
- a quality-control log documenting cross-file checks and known version-specific issues.

The workbook is intended as a navigation and verification aid. The individual files in `source data/` remain the figure-specific source records.

## Data and code availability

The public repository is:

<https://github.com/PJ6501/Emission>

## Contact

**Peng Jiang**  
Department of Industrial Engineering and Management  
Sichuan University  
Email: pengjiang@scu.edu.cn
