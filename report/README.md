# Dissertation Source

**Imperial College London** — Department of Computing  
**Degree**: MSc Computing (Individual Project)  
**Author**: Anas Khan (`ak7025@ic.ac.uk`)  
**Supervisor**: Dr. Konstantinos Gkoutzis  
**Second Marker**: Dr. Thomas Lancaster  
**Academic Year**: 2025–2026  
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


## 2. Submission Compliance and Ethics

* **Generative AI Assistance**: Disclosed in `report/frontmatter/declaration.tex` in compliance with Imperial College London policy.
* **Data Privacy & Ethics**: No identifying student data is collected or distributed. The CSEDM dataset is processed and evaluated strictly in anonymised aggregate under DataShop research agreements.