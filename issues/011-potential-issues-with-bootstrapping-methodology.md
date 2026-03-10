---
agreement: 0.67
category: reproducibility
id: '011'
location:
  file: paper/writeup/optimize.tex
  lines:
  - 1254
  - 1280
models_flagged: []
severity: moderate
source_job: crosscut
title: Bootstrap implementation details not reported
type: technical
---

# Bootstrap implementation details not reported

## Flagged text

> Bootstrapped standard errors are in parentheses.

## Problem

The paper reports bootstrapped standard errors and confidence intervals but does not specify the number of bootstrap resamples, the resampling unit, or the SE computation method.

## Evidence gathered

**Searched for:** Bootstrap implementation in analysis code
**Locations checked:** `analysis/bounds/prop_ll_stats_tables.R`, `analysis/bounds/prop_ll_plots.R`

- Code uses B=1000 resamples with standard with-replacement resampling of game-level log-likelihood differences
- SE computed as SD of bootstrap means (standard percentile bootstrap)
- Resampling unit is games (not individual observations), which is correct given the hierarchical structure
- None of these details appear in the manuscript

## Suggested fix

Add a brief note in the estimation section or a footnote specifying B=1000 bootstrap resamples over games, with SE computed as the standard deviation of bootstrap means.

## Severity votes

| Model | Severity | Reasoning |
|-------|----------|-----------|
| claude-sonnet-4-6 | minor | **Severity: Low** |
| gpt-4o | moderate | I would rate the severity of this issue as moderate. While the omission of bootstrap implementation details does not invalidate the results, it does hinder the reproducibility and transparency of the analysis. Including these details is essential for readers to fully understand and evaluate the robustness of the findings. |
| gemini-2.5-pro | moderate | **Severity Rating: Moderate** |

**Consensus: moderate** (1/3 minor, 2/3 moderate)

## Draft author response

**Recommended action**: fix

**Response draft**:

We have added a footnote specifying the bootstrap implementation details.

**Manuscript changes**:

- `writeup/optimize.tex` line 1254: After "We report bootstrapped confidence intervals for the five $\bar\Lambda_S$ values" add footnote: "\footnote{Bootstrap standard errors are computed from $B = 1{,}000$ resamples. In each resample, we draw $n$ games with replacement from $S$ and recompute $\bar\Lambda_S$. The standard error is the standard deviation of these $B$ bootstrap means.}"
