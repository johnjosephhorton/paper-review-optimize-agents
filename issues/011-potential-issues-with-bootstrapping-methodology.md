---
id: "011"
title: "Bootstrap implementation details not reported"
type: technical
location:
  file: "paper/writeup/optimize.tex"
  lines: [1254, 1280]
source_job: "crosscut"
models_flagged: []
category: "reproducibility"
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
