1. Overview

Model name
Bayesian Optimisation with Adaptive Exploration (BO-AE)

Type
Surrogate-based black-box optimisation

Version
v1.0 (Ten-round iterative strategy)

2. Intended Use

Appropriate use cases

Optimising expensive, unknown objective functions

Low-sample, high-uncertainty optimisation problems

Educational demonstrations of Bayesian optimisation

Inappropriate use cases

High-frequency real-time optimisation

Deterministic or convex problems

Safety-critical decision-making without human oversight

3. Strategy Details (Across Ten Rounds)

Rounds 1–3

Broad exploration

Heuristic reasoning

Initial coverage of search space

Rounds 4–6

Introduction of surrogate models

Balance between exploration and exploitation

Early signs of nonlinearity and noise

Rounds 7–9

Explicit Bayesian optimisation

Gaussian Process surrogates per function

Function-specific exploration parameters

Recognition of scaling-law effects and emergent behaviour

Round 10

Fully BO-driven strategy

Expected Improvement acquisition

Trust-region awareness

Differentiated strategies per function based on observed behaviour

4. Performance Summary

Metrics used

Best-so-far output per function

Improvement per iteration

Stability vs volatility trends

Observed outcomes

Some functions show power-law convergence and saturation

Others exhibit multimodal or emergent behaviour

Higher-dimensional functions require sustained exploration

Performance gains diminish over time, consistent with scaling laws

5. Assumptions and Limitations

Key assumptions

Objective functions are reasonably smooth and stationary

Gaussian Process kernels can approximate local behaviour

Noise is moderate and not adversarial

Limitations

Sample inefficiency in high dimensions

Sensitivity to kernel and acquisition choices

Risk of premature convergence or boundary bias

Computational cost grows with dataset size

6. Ethical and Transparency Considerations

Transparency

Full documentation of strategy evolution

Reproducible code and fixed random seeds

Explicit discussion of assumptions and failures

Why this matters

Enables peer review and replication

Prevents overclaiming optimisation success

Encourages responsible application of black-box methods

7. Reflection on Model Card Sufficiency

This model card prioritises clarity over exhaustiveness.
While additional quantitative benchmarks could be added, the current structure sufficiently communicates:

How decisions are made

Why certain strategies were chosen

Where the approach may fail

This level of detail aligns with real-world ML practice, where interpretability and context often matter more than raw performance metrics.
