# Striational Antibody-Associated Myositis – Bridging the Gap between Thymoma and Myasthenia Gravis  
_A Systematic Review and Statistical Analysis (Nature Medicine submission)_

This repository contains the analysis code and figure-generation scripts accompanying the manuscript  
**Striational Antibody-Associated Myositis – Bridging the Gap between Thymoma and Myasthenia Gravis**.

All code is provided to support transparency and reproducibility once the data are available locally.

---

## Repository Structure

```
.
├── Concomitant IIM and MG/
│   ├── data1.csv          # Dataset for concomitant IIM and MG
│   └── data1.R            # Analysis script (Panel A)
│
├── Isolated IIM with TET/
│   ├── data3.csv          # Dataset for isolated IIM with thymectomy
│   └── data3.R            # Analysis script (Panel B)
│
├── Thymoma spontaneous regression/
│   ├── data4.csv          # Dataset for thymoma spontaneous regression
│   └── data4.R            # Analysis script (Panel C)
│
├── ICI-Induced IIM and/or MG/
│   ├── data2.csv          # Dataset for ICI-induced IIM and/or MG
│   └── data2.R            # Analysis script (Panel D)
│
├── Figures/
│   ├── Figure 1/
│   ├── Figure 2/
│   ├── Figure 3/
│   ├── Extended Data Figure 2/
│   ├── Extended Data Figure 3/
│   ├── Extended Data Figure 4/
│   └── Supplementary Figure 2/
│
├── Data Dictionary.pdf    # Variable definitions and coding
└── README.md
```

---

## How to Reproduce Results

All R scripts are intended to be run **interactively, line by line**, rather than as batch jobs.  
Scripts do **not** write intermediate output files; tables and figures are displayed in the R session.  
Inline comments indicate which code blocks correspond to specific manuscript results.

---

## 1. Cohort-Specific Analyses (Panels A–D)

Each cohort folder corresponds to one clinical scenario in the manuscript:

| Folder | Description |
|------|-------------|
| `Concomitant IIM and MG/` | Concomitant inflammatory myopathy and myasthenia gravis |
| `Isolated IIM with TET/` | Isolated IIM following thymectomy |
| `Thymoma spontaneous regression/` | Thymoma spontaneous regression cases |
| `ICI-Induced IIM and/or MG/` | Immune checkpoint inhibitor–induced IIM and/or MG |

### Workflow

1. Open the corresponding `.R` file in R or RStudio  
2. Set the working directory to the folder containing the script and data  
3. Run the script **line by line**

```r
# Example
setwd("/path/to/Concomitant IIM and MG/")
```

Comments in each script indicate which analyses correspond to reported results.

---

## 2. Figures

The `Figures/` directory contains all code and LaTeX components for generating manuscript figures.

Each figure folder typically contains:
- an R script for analysis and plotting
- a main `.tex` file assembling the full figure
- (if applicable) a `tex/` subfolder with panel-level LaTeX sources

### Figure compilation workflow

```bash
# Example: Figure 1
Rscript "Figures/Figure 1/Figure 1.R"

# Compile sub-panels (if applicable)
pdflatex Figures/Figure\ 1/tex/*.tex

# Compile composite figure
latexmk -pdf Figures/Figure\ 1/Figure\ 1.tex
```

Repeat for Extended Data and Supplementary Figures as needed.

---

## Software Requirements

- **R** (version ≥ 4.0)
- R packages listed in `library(...)` calls within each `.R` file
- **LaTeX** distribution (TeX Live or MiKTeX) with `pdflatex` or `latexmk`

(Optional) For reproducible environments:
```r
install.packages("renv")
renv::restore()
```

---

## Data Access

The datasets are available upon reasonable request for research purposes.

- **Data contact:** [luoj1129@gmail.com](mailto:luoj1129@gmail.com)  
  Please include the manuscript title and a brief description of intended use.

Refer to **Data Dictionary.pdf** for variable definitions and coding details.

---

## Questions & Support

For questions regarding code or analyses:  
📧 [luoj1129@gmail.com](mailto:luoj1129@gmail.com)

---

## Disclaimer

This repository is provided for academic and research use only.  
Results and analyses may evolve as the manuscript undergoes peer review.
