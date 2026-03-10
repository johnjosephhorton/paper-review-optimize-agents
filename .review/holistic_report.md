# Holistic Referee Report

## Summary

This paper proposes and empirically demonstrates an approach for constructing AI agents that better predict human behavior in novel settings. The key idea is to ground agent "prompts" (personas) in established social science theories, optimize them against training data from one experimental setting, and validate them on structurally distinct but theoretically related settings. The authors apply this to strategic reasoning games (building on Arad & Rubinstein's 11-20 game using level-k theory) and allocation games (building on Charness & Rabin using social preference theory). In a large-scale preregistered experiment with 883,320 novel games and 4,500 human subjects, they show that theory-grounded agents significantly outperform baseline AI, Nash equilibria, and the cognitive hierarchy model. The paper also develops a statistical framework for externally valid inference over a pre-committed family of experimental settings.

## Overall Assessment

### Importance
This is a highly important paper addressing a fundamental question: can AI agents serve as reliable proxies for predicting human behavior in novel settings? The answer has major implications for social science research, policy evaluation, and experimental design. The scale of the empirical exercise (883,320 games, 1,500 sampled, 4,500 human subjects) is impressive and provides unusually strong evidence.

### Novelty
The paper makes several novel contributions: (1) a principled methodology for constructing generalizable AI agents that combines theory-grounding with cross-setting validation, (2) the "construction method" for parameterizing prompts with continuous trait dimensions and optimizing via Bayesian optimization, (3) a formal statistical framework for externally valid inference over a population of experimental settings, and (4) large-scale empirical evidence across two distinct domains. The connection to invariant risk minimization is creative and well-motivated.

### Positioning
The paper is well-positioned in the growing literature on AI simulation of human behavior. It engages substantively with both the optimistic findings (Argyle et al., Binz & Schulz, Park et al.) and the critical findings (Gao et al., Santurkar et al.) and offers a principled resolution. The connection to the external validity literature (Hotz et al., Allcott & Mullainathan, Dehejia et al.) and the transfer learning framework of Andrews et al. (2025) is appropriate. The framing around the bias-variance tradeoff from machine learning is effective.

## Major Concerns

### M1: The theory-grounding requirement may be more restrictive than acknowledged

The paper argues that theory-grounded personas are essential for generalization, but the evidence primarily comes from settings where a well-established, clean theoretical model exists (level-k for strategic games, social preferences for allocation games). Many applied prediction problems in social science lack such clean theoretical structures. The paper should discuss more explicitly the limits of the approach when theories are vague, competing, or absent. The conclusion gestures at automation but does not grapple with the practical difficulty of operationalizing theories into prompts for more complex domains (labor markets, political behavior, health decisions).

### M2: The comparison to the cognitive hierarchy model may not be entirely fair

The cognitive hierarchy model is parameterized with τ = 1.5 from the literature, with no opportunity to be calibrated on the specific game family. By contrast, the AI agents were explicitly optimized on data from AR's 11-20 game, which shares the same strategic structure as the 883,320 game family. The paper acknowledges this asymmetry in passing but could do more to quantify its impact. For instance, what happens if τ is calibrated on even a small subset of the 1,500 games? If the cognitive hierarchy model with a re-estimated τ closes much of the gap, the advantage of AI agents would be more about flexibility than about theory-grounding per se.

### M3: Dependence on a single LLM (GPT-4o) raises generalizability concerns

All experiments use GPT-4o at temperature 1. The paper notes the approach is "agnostic to the choice of model" but provides no evidence for this claim. Given that different LLMs have different training corpora and alignment procedures, it is plausible that the specific level-k prompts work well with GPT-4o but not with other models. At minimum, a robustness check with one or two alternative models would strengthen the claims substantially.

### M4: The sampling miscalculation in the 1,500-game experiment deserves more discussion

The paper acknowledges a "very minor miscalculation" that caused non-uniform sampling: gap-using bonus rules were sampled with probability ~0.010 vs. ~0.086 for non-gap rules. This is roughly an 8.6x difference in sampling probability, which is not obviously "very minor." The estimand changes from the population average under uniform sampling to the average under the actual (non-uniform) distribution. While robustness checks show results are similar across bonus rules, the dismissal may be too quick. An inverse probability weighting analysis to recover the uniform-sampling estimand would be reassuring.

## Minor Concerns

### m1: The ε = 0.2 smoothing parameter is consequential and could be explored more

The smoothing parameter ε = 0.2 (agents follow their model 80% of the time, random 20%) is a strong assumption that disproportionately benefits models with concentrated predictions (like pure-strategy Nash equilibria or the AI agents) by adding support everywhere. While robustness checks with other ε values are provided, the main text could discuss more explicitly how this choice affects the relative rankings. Is there a principled way to select ε, or is it purely a robustness exercise?

### m2: Small number of human observations per game (1-5) limits game-level inference

The paper acknowledges this but could better quantify the implications. With only ~3 humans per game, the estimated human distribution for any single game is very noisy. The paper's approach of averaging across games mitigates this for the population-level estimand, but the game-level proportion analysis (Figure 8 bottom panel) is acknowledged to be attenuated. How much precision is being lost? A power analysis or simulation exercise would help.

### m3: The "Always Pick N" persona set is a somewhat strawman comparison

The atheoretical personas include agents literally instructed to always pick a specific number, which is designed to perfectly overfit. While this makes a clear pedagogical point, a more interesting atheoretical comparison would be personas generated by an LLM without theoretical guidance (e.g., "generate 10 diverse personas for this game"). This would better isolate the contribution of theory-grounding vs. simply having diverse, thoughtful prompts.

### m4: Chain-of-thought prompting is used for strategic agents but not clearly for all agents

The paper mentions using chain-of-thought (CoT) prompting for the level-k agents (footnote 23) with a two-step procedure. It is unclear whether baseline agents and atheoretical agents also receive CoT prompting. If not, the performance difference could partly reflect the benefit of CoT rather than the theory-grounding of the personas.

### m5: The construction method (Appendix) deserves more prominence

The construction method (parameterizing prompts with continuous traits and optimizing via Bayesian optimization) appears to be a genuinely novel contribution with broad applicability. Its relegation to the appendix, applied only to the Charness-Rabin allocation games, undersells its potential. A brief discussion in the main text of when to prefer the selection vs. construction method would help practitioners.

### m6: Limited discussion of when AI agents might systematically fail

The paper focuses on success cases. A more balanced treatment would discuss systematically when the approach is likely to fail — for example, when human behavior is driven by context-specific cultural norms, when the relevant theory is misspecified, or when the LLM's training data creates systematic biases in certain domains.

## Questions for the Authors

1. Have you tested the approach with any LLM other than GPT-4o? Even a brief comparison with Claude or Gemini would substantially strengthen the generalizability claim.

2. For the cognitive hierarchy comparison: what τ would minimize prediction error on the 1,500 games, and how close would this calibrated model come to the AI agents?

3. Could you provide inverse probability weights to recover the uniform-sampling estimand for the 1,500-game experiment?

4. Was chain-of-thought prompting applied consistently across all agent types (baseline, atheoretical, and strategic)?

5. The paper mentions that the approach could be applied to "any domain where relevant human data exists." Are there domains where you have tried and the approach failed? Such negative results would be informative.

6. How sensitive are the results to the specific operationalization of level-k theory into natural language? If you rephrased the personas substantially while preserving their theoretical content, would the results hold?
