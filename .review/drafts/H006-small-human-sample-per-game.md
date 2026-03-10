---
id: "H006"
title: "Small number of human observations per game (1-5) limits game-level inference"
type: technical
location:
  file: "writeup/optimize.tex"
  lines: []
source_job: "holistic"
models_flagged: []
---

# Small number of human observations per game (1-5) limits game-level inference

## Flagged text

> Each Prolific worker was randomly assigned one of the 1,500 sampled games such that each game had approximately three human players.

## Problem

With only ~3 humans per game, the estimated human distribution for any single game is very noisy. The population-level estimand benefits from averaging across games, but the game-level proportion analysis (Figure 8 bottom panel) is acknowledged to be attenuated toward 0.5. A power analysis or simulation exercise quantifying how much precision is lost would strengthen the paper.
