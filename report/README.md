# Dissertation Source and Artifact Repository

**Imperial College London** — Department of Computing  
**Degree**: MSc Computing  
**Author**: Anas Khan (`ak7025@ic.ac.uk`)  
**Project Title**: *When More Evidence Hurts: Evaluating Executable Evidence for Performance Prediction in AI Programming Tutors*  
**Submission Date**: September 2026  

---

## 1. Executive Summary and Epistemic Scope

This repository contains the complete LaTeX source, verified figure assets, tables, and bibliography for the MSc Computing dissertation.

The research investigates the utility and reliability of **executable evidence** (targeted code execution checks / probes) when predicting subsequent programming performance in an AI tutoring environment. The central findings establish that:
1. **Model Mismatch & Evidence Harm**: Under misspecified observational models, adding executable evidence can degrade prediction accuracy relative to dialogue-only tracking or simpler heuristic baselines.
2. **Harness Defect Discovery**: Post-hoc verification revealed a sequence-comparison defect in the initial evaluation harness, altering 19 of 48 execution outcomes and adjusting the apparent empirical advantage to $1/23$ ($+4.35$ percentage points, 95% paired bootstrap interval $[0.00, 13.04]$).
3. **Bounded Updating vs. Active Selection**: Bounded Bayesian updates provide robust protection against contaminated evidence, whereas active probe selection policies fail to reliably outperform random or greedy baselines under realistic uncertainty.

> **Epistemic Scope & Boundary**: The empirical evaluations assess predictive instrument accuracy under fixed language models and historical data (CSEDM 2019). They do not evaluate classroom interventions or claim human learning gains.

---

## 2. Getting Started and Build Instructions

### Clone the Repository
```bash
# Clone the dissertation source repository
git clone https://github.com/thekhananas/msc-dissertation-source.git
cd <repo-name>/report
```

### Prerequisites
* **TeX Live 2023+** (or MacTeX) with `latexmk`, `pdflatex`, and `biber` on `PATH`.
* Installed CTAN packages: `biblatex` (Vancouver style), `csquotes`, `microtype`, `hyperref`, `cleveref`, `booktabs`, `tabularx`, `placeins`.

### Primary Build (Recommended)
From within the `report/` directory:

```bash
cd report

# Build complete PDF with automated multi-pass dependency resolution
latexmk -pdf main.tex
```

`latexmk` automatically manages the compilation sequence:
$$\text{pdflatex} \longrightarrow \text{biber} \longrightarrow \text{pdflatex} \longrightarrow \text{pdflatex}$$
resolving all cross-references (`\cref`), bibliography citations, and table/figure lists.

### Out-of-Source Build (Clean Working Tree)
If you prefer building in an isolated subfolder, ensure the mirror subdirectories exist for `\include`:

```bash
cd report

# 1. Pre-create mirror directories for chapter auxiliary files
mkdir -p build/chapters build/appendices build/frontmatter

# 2. Compile into build directory
latexmk -pdf -outdir=build main.tex

# Output PDF:
open build/main.pdf
```

### Housekeeping / Clean Targets
To remove intermediate LaTeX auxiliary files (`.aux`, `.bbl`, `.bcf`, `.log`, `.toc`, etc.) while retaining `main.pdf`:

```bash
cd report
latexmk -c
```

To purge all generated files including the output PDF:

```bash
cd report
latexmk -C
```

---

## 3. Repository Architecture

```text
report/
├── main.tex                       # Master LaTeX report configuration and layout
├── references.bib                 # Canonical 65-entry bibliography (Vancouver style)
├── README.md                      # Academic submission documentation and build guide
├── frontmatter/                   # Title, abstract (written last), and formal declaration
│   ├── title.tex
│   ├── abstract.tex
│   └── declaration.tex
├── chapters/                      # Eight core dissertation chapters
│   ├── 01-introduction.tex
│   ├── 02-related-work.tex
│   ├── 03-measurement-design.tex
│   ├── 04-system-design.tex
│   ├── 05-evidence-tracking-and-acquisition.tex
│   ├── 06-evaluation.tex
│   ├── 07-discussion.tex
│   └── 08-conclusion.tex
├── appendices/                    # Reproducibility and claim boundary specifications
│   ├── reproducibility.tex
│   └── claim-boundaries.tex
└── assets/                        # Standalone figures, tables, and asset register
    ├── asset-register.md          # Cryptographic provenance register with SHA-256 hashes
    ├── figures/                   # Vector PDF figures organised by chapter
    │   ├── ch03-measurement/
    │   ├── ch04-system/
    │   └── ch06-evaluation/
    └── tables/                    # Standalone LaTeX tables organised by chapter
        └── ch06-evaluation/
```


---

## 4. Submission Compliance and Ethics

* **Generative AI Assistance**: Disclosed in `frontmatter/declaration.tex` in compliance with Imperial College policy.
* **Data Privacy**: No private student submissions or identifying telemetry are redistributed. The CSEDM dataset is evaluated strictly in aggregate under DataShop research agreements.
