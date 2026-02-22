Motivation:
The dataset exists to support sequential black-box optimisation under a constrained query budget. It captures how optimisation strategies evolve when feedback is limited and expensive, reflecting realistic engineering and ML optimisation scenarios.
Composition:
The dataset consists of sequential input–output pairs collected across multiple rounds for eight independent functions, with varying dimensionality. The final version explicitly notes gaps in coverage, particularly in low-sensitivity regions that were intentionally deprioritised in later rounds.
Overview and intended use:
The final model card clearly frames the approach as a surrogate-driven, iterative optimisation strategy, suitable for problems with limited evaluations and structured search spaces, but not for adversarial or highly discontinuous objectives.
Strategy evolution:
Earlier versions focused mainly on Bayesian optimisation. The final model card documents the full progression:
early high-exploration behaviour,
mid-stage uncertainty-aware balancing,
late-stage PCA-inspired refinement,
and final ε-greedy exploitation with limited exploration.
Performance and limitations:
The updated card explicitly discusses diminishing returns, surrogate bias, sensitivity to early exploration and the absence of global optimality guarantees.
Transparency and interpretability:
Particular emphasis is placed on interpretability: how queries were chosen, what assumptions guided decisions and how another researcher could reproduce or critique the strategy using the documented code and data.
Ethical and professional considerations:
While the project does not involve sensitive data, the model card highlights how transparency, documentation and explicit assumptions are critical for responsible ML practice, especially in real-world optimisation settings.
