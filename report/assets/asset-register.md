# Report Asset Register

These are the files bundled with the report. Their hashes identify the bytes currently used by LaTeX. The source paths identify
where the files were produced or previously imported; they do not require that the experiment artefact directory is committed.

| Report asset | Role | Current SHA-256 | Status |
|---|---|---|---|
| `imperial-logo.eps` | University title-page logo | `0d21ab5e6eac43f893fde51dc495549571557db0bbcb4cb4336af94890824eb8` | Exact copy of the supplied template's `title/logo.eps`; converted during PDF build |
| `figures/ch03-measurement/external_study_design.pdf` | Sealed benchmark sequence | `d1fda1039b93689ec90488c5178c16f57202430cb03e0a4ff6655d5ec6766e79` | Complete sentences for execution counts. Reviewed export from `study-report-17552a1` |
| `figures/ch04-system/system_boundaries.pdf` | System boundaries | `a29b7bf851ab6ba3c262f5ea355e7f1336d91adfe01591c075e667ab89571a9d` | Complete sentences and runtime label from `system-report-5075d6f` |
| `figures/ch06-evaluation/harness_correction_result.pdf` | Harness correction result | `d2fab3b50ebb46df0ffcf18af162f4b5c61d57c4b0342ac303cd4d2194816e42` | Complete footnote sentence from `harness-report-a9111c2` |
| `figures/ch06-evaluation/tracker_study_canonical.pdf` | Bounded tracker result | `06212426cc056540c1ebeb64cedc863c66761074578537deb974d50ad2d06914` | Stacked panels from `tracker-report-c3285be` |
| `figures/ch06-evaluation/uncertainty_error_review.pdf` | CSEDM uncertainty result | `dcd3b33f1122b90f9c73fc64e01984fb6980cd8b3e54c76a79055282d6b22c11` | Corrected percentage-point units; reviewed local asset |
| `figures/ch06-evaluation/acquisition_result_report.pdf` | Acquisition result archive | `03e885014be2466808e33d462312d5714d9bda5cb176422991e8974532493e3d` | Corrected terminology; reviewed local asset |
| `figures/ch06-evaluation/acquisition_environment_effects_report.pdf` | Acquisition environment archive | `36169e5c328d9ffe3c843886ed7177135379ea89986fd4ace3e2405e28d39570` | Corrected terminology; reviewed local asset |
| `figures/ch06-evaluation/corrected_quality_and_resource_burden.pdf` | Resource-burden archive | `0c7f7dfffa65dbc1a2da7f2abfdf65a7394eddc61e7b98372372c2def91f1679` | Retained local asset |
| `figures/ch06-evaluation/benchmark_worked_example_report.pdf` | Worked benchmark example | `b8deed07a68f4e2b631a3084c3b4e4e58160a3a7282ff0bb4573f460196e068f` | Reviewed local asset |
| `tables/ch06-evaluation/acquisition_primary_result_table.tex` | Acquisition result table | `1f8722973f7441d6d1d6bb9d83d9cb8433445a097d7dd6a9e230f2eb1b9ca0b1` | Corrected terminology; reviewed local asset |
| `tables/ch06-evaluation/model_comparison.tex` | CSEDM model comparison | `a298765596ff749aca515a7af8a3aee17ddc85041816acec9f76d2446c94b216` | Caption spacing and complete footnote sentences from `publication-report-a9111c2` |

The system-boundary, acquisition, and CSEDM entries point to exports generated from committed revisions. Their numerical
source reports are unchanged; the updates correct layout, labels, units, and interpretation boundaries.

The architecture figure comes from `development/artifacts/publication/system-report-5075d6f/`, generated at revision
`5075d6f` with the current Pixi lock. The manifest records the source specification and implementation file hashes.
Its demo section describes the local template path; the live evaluation interface is described separately in Chapter 4.

The harness figure comes from `development/artifacts/publication/harness-report-a9111c2/`. Its generator and execution revision is
`a9111c2`. The experiment lock
was recovered from `6acc49d:development/pixi.lock` and verified against the source-plan hash. This identifies the experiment
dependencies; rendering used the current installed environment and does not claim a historical environment recreation.
The export manifest identifies the analysis and closure reports and the numerical CSV hashes.
The analysis source is `harness_correction_analysis_report.json` in
`development/artifacts/harness-correction/cerebras-gpt-oss-120b-20260903-001/analysis-v1/`, with report hash
`77bb970826c508de60e50ca272cb569bbe9c06c6c25819cf7652cc04585958a9`. It reports one additional correct prediction among
23 eligible cases (4.35 percentage points). The earlier probe-only correction reports a different result and is not the source
for this figure.

The tracker figure comes from `development/artifacts/publication/tracker-report-c3285be/`, generated at revision `c3285be`.
Its publication manifest links the canonical analysis and interpretation reports. The historical experiment lock was recovered
as described above; rendering used the current installed environment. No simulation was rerun for this layout update.
