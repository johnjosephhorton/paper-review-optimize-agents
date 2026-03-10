---
agreement: 0.67
category: methodology
id: H006
location:
  file: paper/writeup/optimize.tex
  lines:
  - 1204
  - 1210
models_flagged: []
severity: major
source_job: holistic
title: Small number of human observations per game (~3) limits game-level inference
type: technical
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

## Severity votes

| Model | Severity | Reasoning |
|-------|----------|-----------|
| claude-sonnet-4-6 | moderate | ## Severity Rating: **3/5 (Moderate)** |
| gpt-4o | major | I would rate the severity of this issue as moderate. The small number of human observations per game significantly limits the reliability and precision of game-level inferences, which can undermine the validity of the study's conclusions. However, the issue could potentially be addressed by adding a simulation or power analysis to quantify the impact and guide future research, rather than requiring a complete redesign of the study. |
| gemini-2.5-pro | major | **Severity Rating: 4/5 (Substantial Issue)** |

**Consensus: major** (2/3 major, 1/3 moderate)

## Draft author response

**Recommended action**: rebut

**Response draft**:

We appreciate this concern, but we believe the paper's design already addresses it through the statistical framework in Section 4.1. The key insight is that inference is over the *population of games*, not over individual games. The population-level estimand $\bar\Lambda$ is estimated by averaging $\hat\Lambda_s$ across 1,500 games, and each $\hat\Lambda_s$ is an unbiased estimator of $\Lambda(s)$ regardless of $m_s$. The asymptotic variance in Proposition 1 explicitly decomposes into cross-game heterogeneity and within-game sampling noise, and the latter shrinks proportionally with $m_s$. As we note in the text (lines 978-981), "once a few human observations are obtained per setting, the precision of $\bar\Lambda_S$ is governed primarily by $n$." The design deliberately prioritizes breadth (1,500 games) over depth (~3 humans per game) because the population-level comparison—not game-level inference—is the estimand of interest. We already acknowledge (lines 1304-1306) that the proportion-of-games metric is attenuated toward 0.5 by within-game noise, making our reported proportions conservative. A simulation exercise could quantify this attenuation, but we believe the current discussion makes the tradeoff transparent.
