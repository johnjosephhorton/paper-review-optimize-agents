---
id: "004"
title: "Unexplained unanimous decision in setting 8"
type: logical
location:
  file: "paper/writeup/optimize.tex"
  lines: [1692, 1692]
source_job: "section"
models_flagged: []
category: "exposition"
---

# Unexplained unanimous decision in setting 8

## Flagged text

> Human responses generally reflect a fairly even split between options, except for the extreme setting 8, where participants unanimously select Option A.

## Problem

The paper notes that participants unanimously select Option A in setting 8 but labels it only as "extreme" without explaining why.

## Evidence gathered

**Searched for:** Setting 8 payoff structure in experimental code
**Locations checked:** `experiments/charness_rabin/baseline_novel.py`

- Setting 8 payoffs: Option A = ($0.45 to Selected, $0.65 to each other player), Option B = ($0.00 to all). Option B is strictly dominated — it gives $0.00 to everyone. The unanimous result is trivially predictable from the payoff structure.
- The paper provides no mention of this dominance. A reader without access to the experimental code cannot understand why this setting is "extreme."
- This trivial setting may inflate the appearance of predictive success since any model recognizing $0 < $0.45 gets it right.

## Suggested fix

Add a note acknowledging that setting 8 has a dominated Option B ($0.00 to all players), making unanimous selection unsurprising. Consider flagging this in the MAE comparison.
