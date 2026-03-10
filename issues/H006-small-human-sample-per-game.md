---
id: "H006"
title: "Small number of human observations per game (~3) limits game-level inference"
type: technical
location:
  file: "paper/writeup/optimize.tex"
  lines: [1204, 1210]
source_job: "holistic"
models_flagged: []
category: "methodology"
---

# Small number of human observations per game (~3) limits game-level inference

## Flagged text

> Each Prolific worker was randomly assigned one of the 1,500 sampled games such that each game had approximately three human players.

## Problem

With only ~3 humans per game, the estimated human distribution for any single game is very noisy. The game-level proportion analysis is acknowledged to be attenuated toward 0.5. No power analysis quantifies how much precision is lost.

## Evidence gathered

**Searched for:** Power analysis, precision discussion
**Locations checked:** Sections 4.5, 4.6, appendix

- Lines 978-981: Theoretical discussion noting precision governed by n (games)
- Lines 1304-1306: Acknowledges attenuation but calls estimates "highly conservative" without quantification
- No power analysis or simulation exercise in the paper

## Suggested fix

Add a simulation or power analysis showing how the proportion metric converges as humans per game increases.
