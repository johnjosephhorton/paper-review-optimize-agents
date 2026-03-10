---
id: "011"
title: "Potential Issues with Bootstrapping Methodology"
type: technical
location:
  file: "methodology_soundness"
  lines: []
source_job: "crosscut"
models_flagged: []
---

# Potential Issues with Bootstrapping Methodology

## Flagged text

> Bootstrapped standard errors are in parentheses. Green indicates ratios greater than zero, where the optimized AI has more predictive power, and red is the converse.

## Problem

While bootstrapping is a common method for estimating standard errors, the paper does not provide details on how the bootstrapping was implemented, such as the number of bootstrap samples or the resampling strategy. Without this information, it's difficult to assess the reliability of the standard errors reported. The paper should include a detailed explanation of the bootstrapping methodology to ensure the results are robust and reproducible.
