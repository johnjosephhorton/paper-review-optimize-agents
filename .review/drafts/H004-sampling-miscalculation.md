---
id: "H004"
title: "Sampling miscalculation in 1,500-game experiment deserves more discussion"
type: technical
location:
  file: "writeup/optimize.tex"
  lines: []
source_job: "holistic"
models_flagged: []
---

# Sampling miscalculation in 1,500-game experiment deserves more discussion

## Flagged text

> A very minor miscalculation in the deduplication process caused small deviations from uniformity: the seven bonus rules that do not use the gap parameter were each sampled with probability ≈ 0.086, while the four gap-using bonus rules were each sampled with probability ≈ 0.010.

## Problem

The ~8.6x difference in sampling probability between gap-using and non-gap bonus rules is described as "very minor" but is substantial. The estimand changes from the population average under uniform sampling to the average under the actual non-uniform distribution. While robustness checks show similar results across bonus rules, an inverse probability weighting analysis to recover the uniform-sampling estimand would be more convincing than the current dismissal.
