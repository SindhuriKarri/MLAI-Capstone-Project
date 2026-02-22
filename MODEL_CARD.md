 Overview

Model Name: Iterative Bayesian Optimisation with PCA-Guided Refinement
Model Type: Surrogate-based optimisation (Gaussian Process + acquisition strategy)
Version: Final capstone submission

This approach combines Bayesian optimisation principles with dimensionality-aware refinement and reinforcement learning-inspired exploration control.

Intended Use and Scope

Intended use:

sequential optimisation with limited evaluation budgets

black-box functions with moderate smoothness

engineering or ML hyperparameter tuning tasks

Not recommended for:

highly discontinuous or adversarial functions

problems requiring strict global guarantees

settings with extremely noisy or deceptive feedback

Performance Summary

Performance improved rapidly in early rounds and stabilised in later iterations, reflecting diminishing returns as uncertainty decreased. Rather than chasing large late-stage gains, the strategy prioritised stability and consistency.

Metrics were evaluated per function using:

best-observed value

convergence behaviour

sensitivity to exploratory steps

The final iterations showed controlled refinement rather than large jumps, consistent with a converged surrogate model.

Assumptions, Trade-offs and Limitations

Key assumptions:

functions exhibit some smoothness or local structure

dominant directions of variation exist

surrogate uncertainty is informative

Trade-offs:

exploration vs exploitation

simplicity vs sophistication

local refinement vs global search

Limitations:

PCA-style reasoning may miss non-linear interactions

manual tuning still played a role

surrogate quality depends heavily on early sampling decisions

Reinforcement Learning Perspective 

The optimisation process closely mirrors reinforcement learning dynamics:

early high exploration resembles high-ε bandit policies

later exploitation reflects stabilised Q-values

feedback gradually reduces update magnitude

ε-greedy refinement enables risk-aware final decisions

The final strategy represents a hybrid of model-free learning (trial and error) and model-based planning (surrogate-guided anticipation).

Ethical and Reproducibility Considerations

Transparency was a guiding principle throughout the project. All design decisions, assumptions and refinements are documented in the repository to support reproducibility. While this project does not involve human data, the emphasis on explainable decision-making and uncertainty awareness is directly relevant to real-world ML systems where accountability matters.

Key Lessons and Future Application

The most important lesson from the BBO capstone project is that effective optimisation is driven by structure, not randomness. As data accumulates, strategy should evolve toward identifying and exploiting informative directions while retaining enough exploration to remain robust.
