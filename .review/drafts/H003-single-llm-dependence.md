---
id: "H003"
title: "Dependence on a single LLM (GPT-4o) raises generalizability concerns"
type: logical
location:
  file: "writeup/optimize.tex"
  lines: []
source_job: "holistic"
models_flagged: []
---

# Dependence on a single LLM (GPT-4o) raises generalizability concerns

## Flagged text

> All simulations use GPT-4o with the temperature set to 1, though the approach is agnostic to the choice of model and hyperparameters.

## Problem

The claim of model-agnosticism is unsupported by evidence. Different LLMs have different training corpora and alignment procedures. The level-k prompts may work well with GPT-4o but not with other models. A robustness check with one or two alternative models would substantially strengthen the claims.
