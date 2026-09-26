# This repository contains the code, source data, editable figure files, and summary materials supporting the manuscript



## Repository contents

```text
.
├── README.md
├── Data\_and\_Code\_Summary.xlsx
├── code/
│   ├── Fig1.m
│   ├── Fig2a.m
│   ├── Fig2a.xlsx
│   ├── Fig2b.m
│   ├── Fig3a.py
│   ├── Fig3b.py
│   ├── Fig4a.py
│   ├── Fig4a.xlsx
│   ├── Fig4b\_4c.m
│   ├── Fig5a.m
│   ├── Fig5b.py
│   ├── Fig5b.xlsx
│   ├── Fig5c.py
│   ├── Fig5c.xlsx
│   ├── SupplementaryFig1.vsdx
│   ├── SupplementaryFig2a.m
│   ├── SupplementaryFig2a.xlsx
│   ├── SupplementaryFig2b.m
│   ├── SupplementaryFig2b.xlsx
│   ├── SupplementaryFig3.xlsx
│   ├── SupplementaryFig4.py
│   ├── SupplementaryFig5.pptx
│   ├── SupplementaryTable5.xlsx
│   └── Table 1.xlsx
└── source data/
    ├── Source Data Fig.1.xlsx
    ├── Source Data Fig.2a.xlsx
    ├── Source Data Fig.2b.xlsx
    ├── Source Data Fig.3a.xlsx
    ├── Source Data Fig.3b.xlsx
    ├── Source Data Fig.4a.xlsx
    ├── Source Data Fig.4b\_4c.xlsx
    ├── Source Data Fig.5a.xlsx
    ├── Source Data Fig.5b.xlsx
    ├── Source Data Fig.5c.xlsx
    ├── Source Data for 294 LLMs.xlsx
    ├── Source Data Supplementary Fig.4.xlsx
    ├── Source Data SupplementaryFig.2a.xlsx
    └── Source Data SupplementaryFig.2b.xlsx
```

`Data\_and\_Code\_Summary.xlsx` consolidates the repository inventory, figure-to-file map, principal numerical results, source data samples, and code requirements.

## Quick start

### Python figures

A Python 3.10 or newer environment is recommended.

```bash
python -m venv .venv
source .venv/bin/activate          # macOS/Linux
# .venv\\Scripts\\activate           # Windows

pip install numpy pandas matplotlib openpyxl prophet pycirclize
cd code
```

Run the Python scripts from the `code/` directory because they use relative input and output paths:

```bash
python Fig3a.py
python Fig3b.py
python Fig4a.py
python Fig5b.py
python Fig5c.py
python SupplementaryFig4.py
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
run('Fig4b\_4c.m')
run('Fig5a.m')
run('SupplementaryFig2a.m')
run('SupplementaryFig2b.m')
```



## Figure and table reproduction map

|Target|Code or editable source|Input data|Main output or function|
|-|-|-|-|
|Main Fig. 1|`code/Fig1.m`|Values are embedded; full-precision values are in `source data/Source Data Fig.1.xlsx`|Seven-phase radial comparison; writes `figure.png`|
|Main Fig. 2a|`code/Fig2a.m`|`code/Fig2a.xlsx`; equivalent source data in `source data/Source Data Fig.2a.xlsx`|Release date and computing-demand ellipses by producer region|
|Main Fig. 2b|`code/Fig2b.m`|Regional values are embedded; shares are supplied in `source data/Source Data Fig.2b.xlsx`|Regional absolute, stacked, and percentage-stacked bars|
|Main Fig. 3a|`code/Fig3a.py`|Historical series embedded; final series in `source data/Source Data Fig.3a.xlsx`|`Fig3a.svg`, diagnostic plots, and `monthly\_diff\_all\_scenarios.xlsx`|
|Main Fig. 3b|`code/Fig3b.py`|Historical visit series embedded; final series in `source data/Source Data Fig.3b.xlsx`|`Fig3b.svg`|
|Main Fig. 4a|`code/Fig4a.py`|`code/Fig4a.xlsx`; full source in `source data/Source Data Fig.4a.xlsx`|`Fig4a.svg`|
|Main Fig. 4b–c|`code/Fig4b\_4c.m`|Values embedded; full source in `source data/Source Data Fig.4b\_4c.xlsx`|Annual phase emissions and shares|
|Main Fig. 5a|`code/Fig5a.m`|Values embedded; full source in `source data/Source Data Fig.5a.xlsx`|One-at-a-time parameter effects|
|Main Fig. 5b|`code/Fig5b.py`|`code/Fig5b.xlsx`; equivalent source data in `source data/Source Data Fig.5b.xlsx`|`Fig5b.svg`|
|Main Fig. 5c|`code/Fig5c.py`|`code/Fig5c.xlsx`; equivalent source data in `source data/Source Data Fig.5c.xlsx`|`Fig5c.svg`|
|Supplementary Fig. 1|`code/SupplementaryFig1.vsdx`|Editable Visio source|System-boundary diagram|
|Supplementary Fig. 2a|`code/SupplementaryFig2a.m`|`code/SupplementaryFig2a.xlsx`; equivalent source data in `source data/Source Data SupplementaryFig.2a.xlsx`|Pareto curve for computing demand|
|Supplementary Fig. 2b|`code/SupplementaryFig2b.m`|`code/SupplementaryFig2b.xlsx`; equivalent source data in `source data/Source Data SupplementaryFig.2b.xlsx`|Pareto curve for website visits|
|Supplementary Fig. 3|`code/SupplementaryFig3.xlsx`|Data and charts are contained in the workbook|Curve-fitting comparison|
|Supplementary Fig. 4|`code/SupplementaryFig4.py`|`code/Fig4a.xlsx`; full source in `source data/Source Data Supplementary Fig.4.xlsx`|`FigS4.svg`|
|Supplementary Fig. 5|`code/SupplementaryFig5.pptx`|Editable PowerPoint source|Innovating–Shifting–Disclosing–Rolling management cycle|
|Supplementary Table 5|`code/SupplementaryTable5.xlsx`|Data and formulas are contained in the workbook|Six-month out-of-sample comparison and MSE values|
|Table 1|`code/Table 1.xlsx`|Data and formulas are contained in the workbook|Normalized mitigation and exacerbation sensitivity|

## Main source datasets

### `Source Data for 294 LLMs.xlsx`

This is the core model-level dataset. It contains:

|Field|Description|
|-|-|
|`Model`|Model or model-version name|
|`Publication date`|Release/publication date|
|`Parameters`|Reported model parameter count where available|
|`Training compute (FLOPs)`|Publicly documented training-compute (Single training run)|
|`Country/Region`|Producer-attributed country or region|

### Figure-specific source files

The files named `Source Data Fig.\*.xlsx` contain the numerical values plotted in the corresponding main figures. The supplementary source files provide the Pareto distributions and annual nine-scenario series.

Important unit conventions are:

* Carbon emissions: t CO₂-eq or Mt CO₂-eq, as indicated in each header.
* Training compute: FLOPs, or (10^{26}) FLOPs in the projection workbooks.
* Online visits: billion visits per month in `Source Data Fig.3b.xlsx`; million visits in `Source Data SupplementaryFig.2b.xlsx`.
* Shares: stored as fractions in several source files and displayed as percentages in the manuscript.
* Dates: stored as Excel dates and should be displayed as `YYYY-MM-DD`.

## Method-specific code notes

### Computing-power demand projection (`Fig3a.py`)

### Online-visit projection (`Fig3b.py`)

### Emission trajectories (`Fig4a.py` and `SupplementaryFig4.py`)

### Chord diagrams (`Fig5b.py` and `Fig5c.py`)

## Summary workbook

`Data\_and\_Code\_Summary.xlsx` contains:

* a complete repository inventory;
* a figure/table reproduction map;
* Python/MATLAB requirements;
* the 294-LLM dataset;
* consolidated source data for main and supplementary figures;
* normalized sensitivity calculations; and
* curve-fitting and holdout-test data.

The workbook is intended as a navigation and verification aid. The individual files in `source data/` remain the figure-specific source records.

## Data and code availability

The public repository is:

[https://github.com/PJ6501/Emission](https://github.com/PJ6501/Emission)

