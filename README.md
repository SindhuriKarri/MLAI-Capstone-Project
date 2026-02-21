# MLAI-Capstone-Project
1. Project Overview 
This repository documents my Black-Box Optimisation (BBO) capstone project, which explores sequential optimisation of eight unknown functions. The goal of the project was not only to maximise performance but also to develop a principled strategy for balancing exploration and exploitation as information accumulated over time.

The project was designed to mirror real-world optimisation problems, where function structure is unknown, feedback is expensive and decisions must be justified using limited data. Over multiple iterations, the optimisation strategy evolved from broad exploratory sampling to structured, evidence-driven refinement informed by surrogate models, PCA-style reasoning and reinforcement learning concepts.

2. Initial Codebase and Design Choices 
The initial codebase was built largely from scratch, drawing inspiration from standard Bayesian optimisation workflows rather than copying a complete public implementation. This decision was intentional: starting with a minimal, transparent structure made it easier to reason about each design choice and adapt the pipeline week by week.
The early code focused on:
reliable ingestion of query inputs and outputs
basic surrogate modelling
global candidate sampling using Sobol sequences or uniform random sampling
This simplicity ensured that early failures or unexpected results could be traced back to specific assumptions rather than hidden implementation details.
3. Key Learnings
- Effective optimisation is driven by structure, not randomness
- Exploration is essential early, but costly late
- Identifying dominant directions of variation dramatically improves efficiency
- Bayesian optimisation and reinforcement learning share deep conceptual similarities
Mid rounds: acquisition parameters were tuned deliberately, and candidate sampling became more focused around promising regions.
4.Technical Highlights
Surrogate-based optimisation:
Implemented Gaussian Process (GP) surrogates to model unknown objective functions and guide query selection under a strict evaluation budget.
Adaptive acquisition strategies:
Used Expected Improvement / UCB-style acquisition functions with function-specific parameter tuning to dynamically balance exploration and exploitation as data accumulated.
Progressive exploration control:
Transitioned from global Sobol sampling in early rounds to increasingly localised candidate generation, reflecting diminishing uncertainty and stabilising surrogate confidence.
PCA-inspired directional refinement:
Analysed accumulated query data to identify dominant directions of variation, enabling targeted refinement along high-signal axes while reducing redundant exploration in low-impact dimensions.
ε-greedy final-stage refinement:
Incorporated a small stochastic perturbation in late iterations to preserve exploratory capacity and avoid premature convergence, inspired by reinforcement learning policies.
Function-specific strategy adaptation:
Adjusted optimisation behaviour per function based on observed volatility, dimensionality and clustering patterns rather than applying a uniform global strategy.
Uncertainty-aware decision making:
Explicitly leveraged surrogate uncertainty estimates to guide sampling, prioritising robustness and stability over aggressive but risky improvements in later rounds.
Interpretability-driven optimisation:
Favoured strategies that allowed post-hoc reasoning about why a query was chosen, improving transparency, reproducibility and alignment with professional ML practice.
Reinforcement learning perspective:
Framed the optimisation process as a sequential decision problem, drawing parallels to multi-armed bandits, Q-value updates and policy refinement over time.
Reproducible, modular workflow:
Structured the pipeline so that data ingestion, surrogate fitting, candidate generation and query refinement are clearly separated and reproducible across iterations.
Later rounds: PCA-inspired reasoning was introduced to identify dominant directions of variation, reducing redundancy across dimensions.

Final round: a small ε-greedy refinement step was added, allowing mostly exploitative behaviour with limited exploratory flexibility.

The most impactful change was the shift from treating all dimensions equally to prioritising directions that historically produced meaningful output variation.
