---

id: "H002"
title: "Comparison to cognitive hierarchy model may not be entirely fair"
type: logical
location:
  file: "writeup/optimize.tex"
  lines: []
source_job: "holistic"
models_flagged: []
verdict: rejected---


# Comparison to cognitive hierarchy model may not be entirely fair

## Flagged text

> Since our goal is to make predictions in the 1,500 games where we have no prior human data, we have no compelling value to choose for τ other than that from the literature.

## Problem

The cognitive hierarchy model uses τ = 1.5 from the literature with no calibration opportunity, while the AI agents were explicitly optimized on AR's 11-20 game data sharing the same strategic structure as the 883,320-game family. The asymmetry means the comparison partly reflects calibration advantage rather than model superiority. Calibrating τ on even a small subset of games would quantify how much of the gap is due to this.
