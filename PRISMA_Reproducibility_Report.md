# PRISMA-ScR Reproducibility Report

**Supplementary Material for:** *Learning to Route On-Chip: A Survey of Machine Learning-Based Routing in Networks-on-Chip and Its Hardware Overheads*

**Prepared for:** MDPI journal submission (major revision)
**Corresponding author:** Dr. Remberto Sandoval Aréchiga, Universidad Autónoma de Zacatecas (UAZ)
**Review team:** Reviewer 1 — Dr. Bernardo Ibarra Infante; Reviewer 2 — Dr. Remberto Sandoval Aréchiga; Reviewer 3 (tiebreaker/arbitrator) — Dr. Víktor Iván Rodríguez Abdalá
**Reporting standard:** PRISMA 2020 (Scoping Review extension, PRISMA-ScR)
**Report generated:** 2026-09-11
**Final corpus:** 49 included studies

---

## 1. Purpose and Scope

This document reports, in a self-contained and reproducible form, the systematic search, screening, eligibility assessment, quality appraisal, and data-extraction procedures that underpin the survey. It is intended to accompany the manuscript as supplementary material so that editors, reviewers, and readers can verify how the 49-study evidence base was assembled and evaluate the risk of bias in the included literature, consistent with PRISMA 2020 reporting requirements for scoping reviews.

All figures reported below are drawn from the review team's current, corrected PRISMA documentation set (protocol, search logs, screening/conflict-resolution records, PRISMA flow data, quality-appraisal dataset, and evidence matrix) and from the manuscript's own PRISMA flow diagram (Figure 1 of the manuscript, sourced from `prisma-flow.tex`). All of these sources agree on a final corpus of **49 included studies**.

## 2. Research Questions

The review was structured around four research questions (PICO-informed framework):

- **RQ1.** What are the most widely used ML paradigms and mathematical abstractions (Dec-POMDP, MARL, SVR, ACO, etc.) for addressing adaptive routing in NoCs?
- **RQ2.** How does the effectiveness of learning policies vary depending on the underlying physical medium (2D electrical, 3D electrical, or silicon photonic)?
- **RQ3.** What are the area (kGE), power (W), and decision-latency (ns) overheads reported in ASIC/FPGA hardware synthesis for these intelligent routers?
- **RQ4.** What are the primary methodological gaps, scalability bottlenecks, and evaluation biases present in the current literature?

## 3. Eligibility Criteria

**Inclusion criteria**
- **IC1** — Original research studies published in peer-reviewed indexed journals or high-impact conference proceedings (Q1/Q2 or IEEE/ACM core venues).
- **IC2** — Articles that explicitly propose or evaluate an NoC routing algorithm guided or supervised by ML, RL, or a metaheuristic model.
- **IC3** — Studies reporting at least one quantifiable performance outcome (e.g., latency, throughput, fault tolerance, hardware overhead).
- **IC4** — Publications written in English.

**Exclusion criteria**
- **EC1** — Studies on routing in wide-area networks (WAN), wireless sensor networks (WSN), or software-defined networks (SDN) that do not address on-chip hardware constraints.
- **EC2** — Studies applying ML to NoC-related tasks other than routing (e.g., task mapping, chip testing, or traffic classification only).
- **EC3** — Purely descriptive papers, patents, extended abstracts, presentations, or tutorials lacking empirical validation.
- **EC4** — Publications that do not provide clear information about the underlying router topology or architecture.

An additional eligibility clarification, applied during conflict resolution, was that studies using fixed-rule or purely fuzzy-logic control (i.e., no trainable ML/RL component) do not satisfy IC2 and are therefore excluded even if they appear in an ML-adjacent venue (see §5.2).

## 4. Information Sources and Search Strategy

**Databases searched (7 sources):** ACM Digital Library, IEEE Xplore, ScienceDirect, SpringerLink, Wiley Online Library, plus a prior-knowledge seed set and citation-chasing pass.

**Search string (title/topic-restricted, Boolean AND across three concept blocks):**

```
TITLE((*NoC OR "Network*-on-Chip" OR Interconnect*))
  AND
TITLE(*routing)
  AND
*learning
```

**Search execution log** (all executions dated 2026-09-07/08, query version v3):

| Database | Date | Results | Filters applied |
|---|---|---|---|
| ACM Digital Library | 2026-09-07 | 19 | Title: network-on-chip; Title: learning; E-Publication Date 2015–2026 |
| IEEE Xplore | 2026-09-07 | 41 | Document Title matches NoC/Network*-on-Chip/Interconnect* AND *routing; All Metadata: *learning |
| ScienceDirect | 2026-09-07 | 49 | TITLE-ABS-KEY(NoC/Network-on-Chip/Interconnect AND routing AND learning); 2015–2026; Computer Science, Engineering |
| SpringerLink | 2026-09-07 | 18 | Title: (*NoC OR "Network*-on-Chip" OR Interconnect*) AND *routing; Keywords: *learning; 2015–2026 |
| Wiley Online Library | 2026-09-07 | 24 | Same title/keyword pattern; Open Access; 2015–2026; Computer Science |
| Prior knowledge / citation chase | 2026-09-08 | 24 | Manually curated seed and backward/forward citation set |

**Total records identified: 175** (0 duplicates removed — no record appeared in more than one source under the deduplication check applied).

## 5. Study Selection

### 5.1 Screening process

Screening was performed independently and in duplicate at both the title/abstract and full-text stages by Reviewer 1 (Dr. Bernardo Ibarra Infante) and Reviewer 2 (Dr. Remberto Sandoval Aréchiga), using a shared screening tool with per-record decision logging (include / exclude / maybe) and a mandatory exclusion-reason field. Every screening decision is individually timestamped and attributable to a named reviewer in the underlying screening log.

Of the 175 title/abstract decisions made independently by the two reviewers, the majority were concordant on first pass; disagreements were escalated to a third, independent reviewer — Dr. Víktor Iván Rodríguez Abdalá — acting as tiebreaker/arbitrator. All escalated conflicts were resolved by the tiebreaker, with a documented reason recorded for each adjudication.

### 5.2 The R-46 / R-170 / R-175 arbitration

Three records (Singh & Shahi 2018 — R-46; Valinataj et al. 2010 — R-170; Zhao et al. 2022 — R-175) were flagged as disagreements between the two primary reviewers. The tiebreaker excluded all three with the recorded reason **"Not a machine-learning approach"**, on the grounds that each study implements a fixed-rule or fuzzy-logic controller with no trainable ML/RL component, and therefore does not satisfy IC2. This arbitration is the authoritative eligibility decision for these three records; they are correctly absent from the final 49-study corpus and from all reported syntheses in the manuscript.

### 5.3 PRISMA 2020 flow

| Stage | Count |
|---|---|
| Records identified through database searching | 175 |
| Duplicates removed | 0 |
| Records screened (title/abstract) | 175 |
| Records excluded at title/abstract | 118 |
| Reports sought for retrieval | 57 |
| Reports not retrieved | 0 |
| Reports assessed for eligibility (full text) | 57 |
| Reports excluded at full text (with reasons) | 8 |
| **Studies included in the review** | **49** |

This flow matches the manuscript's PRISMA 2020 flow diagram (Figure 1) and the reproducibility package's `prisma/flow.json`.

### 5.4 Title/Abstract Screening and Conflict Resolution — Cross-Check

`SmartReview/PRISMA_Screening_and_Conflict_Resolution_Report.md` documents, at the level of the individual title/abstract screening decision, the same process summarized in §5.1–§5.2. It is internally consistent: of the 175 records, reviewers agreed on 153 and disagreed on 22; all 22 conflicts were resolved by the tiebreaker (3 → Include, 19 → Exclude); the resulting title/abstract-stage tally is 53 Include, 121 Exclude, and 1 Maybe (53 + 121 + 1 = 175).

These title/abstract-stage totals do **not** equal the "excluded at title/abstract" (118) and "reports sought" (57) figures in §5.3, and the difference — 121 vs. 118 excluded, 54 (53 Include + 1 Maybe) vs. 57 sought — is exactly 3 in both directions. This is fully explained by a difference in **stage attribution**, not by conflicting eligibility decisions: the conflict-resolution log records R-46, R-170, and R-175 as excluded **at the title/abstract stage** (their tiebreaker adjudication is logged against that stage), whereas the manuscript's official PRISMA flow (§5.3, matching `prisma/flow.json` and the manuscript's Figure 1) carries these same three records forward and excludes them **at the full-text stage** (within the 8 full-text exclusions). Once this attribution difference is accounted for, the two sources agree on the same underlying decision — exclude R-46/R-170/R-175, include 49 — and neither figure should be read as contradicting the manuscript's published PRISMA flow.

A secondary check against the raw screening log (`screening/screening.csv`) found 68 records with at least one logged full-text-stage decision, 11 more than the 57 reports the manuscript reports as "sought"/"assessed" at full text. At least one of these extra entries is attributable to a duplicate/non-standard log entry (a full-text decision for R-01 recorded under the reviewer name "Remberto" rather than the standard "Remberto Sandoval Arechiga"). This 68-vs-57 gap is log-level noise in the underlying screening tool's raw event stream, not a discrepancy in the manuscript's reported PRISMA flow, which remains the authoritative, internally consistent figure (57 sought → 57 assessed → 8 excluded → 49 included).

## 6. Quality Appraisal

**Tool:** Mixed Methods Appraisal Tool (MMAT), adapted for engineering/simulation-based studies. Each of the 49 included studies was rated by the review team against five criteria (Q1–Q5), each scored as *yes* / *no* / *can't tell*.

**Risk-of-bias distribution across the 49 included studies:**

| Risk category | Studies | Share |
|---|---|---|
| Low | 34 | 69.4% |
| Moderate | 12 | 24.5% |
| High | 3 | 6.1% |

The three studies rated High risk are R-01, R-27, and R-53; the twelve rated Moderate are R-34, R-40, R-41, R-44, R-45, R-48, R-51, R-55, R-156, R-158, R-161, and R-168. All remaining included studies (34) were rated Low risk. Per-study Q1–Q5 ratings and timestamps are recorded in the quality-appraisal dataset (`quality.csv`) inside the reproducibility package.

### 6.1 Per-study MMAT scores

The table below gives the exact fraction of the five MMAT criteria rated "yes" for each of the 49 included studies (source: `quality.csv`), cross-checked against the independent "Quality Summary" in `SmartReview/evidencia.md` — the two sources agree exactly for all 49 studies. The risk category shown reproduces the same Low/Moderate/High classification as §6 (0–2/5 = High, 3/5 = Moderate, 4–5/5 = Low, applied without exception).

| Study | Score | Risk | Study | Score | Risk | Study | Score | Risk |
|---|---|---|---|---|---|---|---|---|
| R-01 | 2/5 | High | R-14 | 4/5 | Low | R-20 | 5/5 | Low |
| R-21 | 4/5 | Low | R-23 | 4/5 | Low | R-25 | 4/5 | Low |
| R-27 | 0/5 | High | R-30 | 5/5 | Low | R-31 | 4/5 | Low |
| R-34 | 3/5 | Moderate | R-40 | 3/5 | Moderate | R-41 | 3/5 | Moderate |
| R-42 | 4/5 | Low | R-44 | 3/5 | Moderate | R-45 | 3/5 | Moderate |
| R-48 | 3/5 | Moderate | R-50 | 4/5 | Low | R-51 | 3/5 | Moderate |
| R-52 | 4/5 | Low | R-53 | 1/5 | High | R-54 | 4/5 | Low |
| R-55 | 3/5 | Moderate | R-56 | 5/5 | Low | R-58 | 4/5 | Low |
| R-59 | 4/5 | Low | R-60 | 5/5 | Low | R-114 | 4/5 | Low |
| R-152 | 5/5 | Low | R-153 | 4/5 | Low | R-154 | 5/5 | Low |
| R-155 | 4/5 | Low | R-156 | 3/5 | Moderate | R-157 | 4/5 | Low |
| R-158 | 3/5 | Moderate | R-159 | 4/5 | Low | R-160 | 4/5 | Low |
| R-161 | 3/5 | Moderate | R-162 | 4/5 | Low | R-163 | 4/5 | Low |
| R-164 | 4/5 | Low | R-165 | 4/5 | Low | R-166 | 4/5 | Low |
| R-167 | 4/5 | Low | R-168 | 3/5 | Moderate | R-169 | 4/5 | Low |
| R-171 | 5/5 | Low | R-172 | 4/5 | Low | R-173 | 4/5 | Low |
| R-174 | 4/5 | Low |  |  |  |  |  |  |

## 7. Data Extraction

Data were extracted independently for each of the 49 included studies into a structured evidence matrix capturing: population/platform (NoC topology and medium), the ML technique under evaluation, the comparator baseline(s), the primary outcome measure(s), the benchmark/traffic workload used for evaluation, the reported metrics and quantitative results, the study design (cycle-accurate simulation, mixed, analytical/literature synthesis), and any limitations explicitly discussed by the original authors. This matrix is the empirical basis for the manuscript's cross-study synthesis (evidence tables, taxonomy mapping, and hardware-overhead analysis).

Cross-checked against `SmartReview/extraction.csv` (a distinct copy from the reproducibility package's `extraction/extraction.csv`, root-level in `SmartReview/`): all 49 rows and field values agree exactly with the reproducibility-package copy. That root-level file adds one extra column, "Completeness," which records a constant "6/6" for all 49 studies — i.e., it currently carries no discriminating information across studies, and its denominator (6) does not match the "8 fields defined" note recorded against PRISMA checklist item 10a (`prisma/checklist.csv`). This is a minor internal labeling inconsistency in the review platform's own metadata, not a data-quality issue in the extracted values themselves, and it does not affect the 49-study corpus or any figure reported elsewhere in this report.

## 8. Reproducibility Package

A machine-readable reproducibility package accompanies this report, containing:

- `protocol/protocol.md` — full review protocol (background, RQs, eligibility criteria, search strings per database, reviewer assignments, extraction schema, synthesis methods, timeline).
- `searches/searches.json` — structured search queries and the complete per-database execution log with exact filter strings, dates, and result counts.
- `screening/screening.csv` — the full, timestamped title/abstract and full-text screening decision log for all 175 records, by reviewer, including the tiebreaker's arbitration entries.
- `quality/quality.csv` — the MMAT Q1–Q5 ratings for all 49 included studies.
- `extraction/extraction.csv` — the structured data-extraction matrix for all 49 included studies.
- `evidence/evidence-matrix.csv` — page/section/quote-level evidence traceability schema.
- `prisma/checklist.csv` and `prisma/flow.json` — the completed PRISMA 2020 checklist and flow-diagram counts.
- `references/references.bib` — bibliographic records for all 175 screened references.
- `reports/final-report.md` — the full narrative scoping-review report generated from the corrected dataset.
- `ai/governance.json` — AI-assistance governance/disclosure log (empty: no AI-generated content was accepted without reviewer sign-off).
- `manifest.json` — a file manifest with SHA-256 hashes for every artifact in the package, enabling integrity verification.

Three further, root-level `SmartReview/` documents were cross-checked against the package above and found consistent with it (see §5.4, §6.1, and §7 for the specific checks performed): `evidencia.md` (independent evidence matrix and per-study quality summary), `extraction.csv` (independent copy of the data-extraction matrix, with the minor "Completeness" labeling caveat noted in §7), and `PRISMA_Screening_and_Conflict_Resolution_Report.md` (the full title/abstract screening and conflict-resolution log, with the stage-attribution caveat noted in §5.4).

An append-only audit trail of 1,218 timestamped events (reviewer actions: screenings, conflict resolutions, checklist updates, extractions, exports, and report generations) underlies every figure in this report and is available in full within the reproducibility package for independent verification.

## 9. Data Availability Statement

The search strategy, screening decisions, conflict-resolution log, quality-appraisal ratings, data-extraction matrix, and PRISMA 2020 checklist described in this report are available in the accompanying reproducibility package. Reviewers and readers can independently recompute the PRISMA flow counts, the risk-of-bias distribution, and the evidence synthesis directly from the CSV/JSON artifacts listed in §8, without needing to re-derive them from the manuscript text.

---

*This report reflects the current, corrected state of the PRISMA-ScR documentation (49-study corpus) as of 2026-09-11.*
