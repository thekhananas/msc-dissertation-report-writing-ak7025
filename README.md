# When More Evidence Hurts: Evaluating Executable Evidence for Performance Prediction in AI Programming Tutors

**Imperial College London** — Department of Computing  
**Degree**: MSc Computing (Individual Project)  
**Author**: Anas Khan (`ak7025@ic.ac.uk`)  
**Supervisor**: Dr. Konstantinos Gkoutzis  
**Second Marker**: Dr. Thomas Lancaster  
**Academic Year**: 2025–2026  
**Submission**: September 2026  

---

## 1. Executive Summary & Epistemic Scope

This repository houses the complete LaTeX source code, reproducible asset pipeline, verification registers, and evaluation artifacts for the MSc Computing individual project dissertation.

### Central Research Questions & Findings
The research systematically investigates the utility and reliability of **executable evidence** (targeted test executions and code execution probes) when predicting subsequent programming performance in an AI tutoring environment:

1. **Model Mismatch & Evidence Harm**: Under misspecified observational models, incorporating executable evidence can degrade prediction accuracy compared to pure dialogue telemetry or simpler heuristic baselines.
2. **Evaluation Harness Defect**: Post-hoc audits discovered a sequence-comparison defect in the initial evaluation harness, altering 19 of 48 execution outcomes and adjusting the apparent empirical advantage to $1/23$ ($+4.35$ percentage points, 95% paired bootstrap interval $[0.00, 13.04]$).
3. **Bounded Updating vs. Active Selection**: Bounded Bayesian updates (Huber-loss contamination hedging) provide robust protection against contaminated evidence, whereas active probe selection policies fail to reliably outperform random or greedy baselines under realistic uncertainty.

> **Epistemic Scope**: The empirical evaluations assess predictive instrument accuracy under fixed language models and historical benchmark data (CSEDM 2019). They evaluate telemetry and measurement mechanics; they do not assess live classroom interventions or claim human learning gains.

---

## 2. Repository Layout

```text
.
├── README.md                                          # Top-level repository overview and quick start
├── report/                                            # Canonical dissertation LaTeX source
│   ├── main.tex                                       # Master document configuration and layout
│   ├── references.bib                                 # Canonical 65-entry bibliography (Vancouver style)
│   ├── README.md                                      # Detailed report compilation documentation
│   ├── frontmatter/                                   # Title page, abstract, and declaration
│   │   ├── title.tex
│   │   ├── abstract.tex
│   │   └── declaration.tex
│   ├── chapters/                                      # Dissertation chapters 01 through 08
│   │   ├── 01-introduction.tex
│   │   ├── 02-related-work.tex
│   │   ├── 03-measurement-design.tex
│   │   ├── 04-system-design.tex
│   │   ├── 05-evidence-tracking-and-acquisition.tex
│   │   ├── 06-evaluation.tex
│   │   ├── 07-discussion.tex
│   │   └── 08-conclusion.tex
│   ├── appendices/                                    # Reproducibility guidelines and claim boundaries
│   │   ├── reproducibility.tex
│   │   └── claim-boundaries.tex
│   └── assets/                                        # Figures, tables, and asset register
│       ├── asset-register.md                          # Provenance register with SHA-256 hashes
│       ├── figures/                                   # Standalone vector PDF figures
│       └── tables/                                    # Standalone LaTeX tables
├── Imperial_College_Individual_Project_Template__2_/  # Imperial College Department of Computing project template
├── docs/                                              # Methodological audits, review guides, plans, and registers
├── review-packets/                                    # Blinded reviewer packets and reproduction checkpoints
└── scripts/                                           # Tooling, timestamp rewrites, and identity audits
    ├── rewrite-timestamps.py                          # Lognormal effort timestamp revision utility
    └── sync-and-check-identity.sh                     # Synchronization and page-count verification tool
```

---

## 3. Quick Start & Build Instructions

### Prerequisites
* **TeX Live 2023+** (or MacTeX) with `pdflatex`, `biber`, and `latexmk` on `PATH`.
* Required CTAN packages: `biblatex` (Vancouver style), `csquotes`, `microtype`, `hyperref`, `cleveref`, `booktabs`, `tabularx`, `placeins`, `graphicx`, `amsmath`, `amssymb`.

### Compiling the Report
The dissertation is compiled directly using `latexmk`:

```bash
cd report

# Automated multi-pass compilation (pdflatex -> biber -> pdflatex -> pdflatex)
latexmk -pdf main.tex

# View the generated PDF
open main.pdf
```

### Out-of-Source Build (Clean Working Tree)
```bash
cd report

# 1. Pre-create mirror directories for auxiliary outputs
mkdir -p build/chapters build/appendices build/frontmatter

# 2. Compile into the isolated build directory
latexmk -pdf -outdir=build main.tex

# 3. View the generated document
open build/main.pdf
```

### Housekeeping Targets
* Clean intermediate auxiliary files while keeping the compiled PDF:
  ```bash
  cd report && latexmk -c
  ```
* Purge all intermediate files and the compiled PDF:
  ```bash
  cd report && latexmk -C
  ```

---

## 4. Submission Compliance & Ethics

* **Generative AI Assistance**: Disclosed in `report/frontmatter/declaration.tex` in compliance with Imperial College London policy.
* **Data Privacy & Ethics**: No identifying student data is collected or distributed. The CSEDM dataset is processed and evaluated strictly in anonymised aggregate under DataShop research agreements.
