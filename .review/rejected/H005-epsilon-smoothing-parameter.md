---

id: "H005"
title: "ε = 0.2 smoothing parameter is consequential and could be explored more"
type: technical
location:
  file: "writeup/optimize.tex"
  lines: []
source_job: "holistic"
models_flagged: []
verdict: rejected---


# ε = 0.2 smoothing parameter is consequential and could be explored more

## Flagged text

> Setting ε=0.2 implies that players follow their model 80% of the time and choose uniformly at random the remaining 20%.

## Problem

The smoothing parameter ε = 0.2 disproportionately benefits models with concentrated predictions (pure-strategy Nash equilibria, AI agents) by adding support everywhere. While robustness checks with ε ∈ {0.05, 0.1, 0.3} are provided, there is no principled method for selecting ε. The asymmetric treatment (cognitive hierarchy model is not smoothed because it already has ~22% random play built in) further complicates interpretation.
