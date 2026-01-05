1. Motivation

Why was this dataset created?
This dataset was created to support an iterative black-box optimisation (BBO) task in which the true objective functions are unknown and expensive to evaluate. The dataset enables experimentation with surrogate modelling, acquisition strategies and exploration–exploitation trade-offs under uncertainty.

What task does it support?
The dataset supports:

Bayesian optimisation research and practice

Analysis of scaling laws and diminishing returns

Study of emergent behaviour in optimisation landscapes

Comparison of exploration vs exploitation strategies across iterations

2. Composition

What does the dataset contain?
The dataset consists of:

Inputs: Query points submitted to eight unknown black-box functions

Outputs: Scalar performance values returned by the evaluation system

Each iteration (week) provides:

1 query per function

8 functions total

Input dimensionality varies per function (2D to 8D)

Size and format

Approximately 10–18 samples per function (growing weekly)

Stored as:

inputs.txt (lists of NumPy arrays per week)

outputs.txt (lists of scalar outputs per week)

Derived CSV files per function for analysis

Are there gaps or missing values?
Yes:

Early iterations have very sparse coverage relative to dimensionality

Some regions of the input space remain completely unexplored

Outputs are noisy for certain functions, leading to uneven data density

3. Collection Process

How was the data collected?
Data was collected iteratively through a controlled submission process:

A query point was proposed for each function

Queries were evaluated by a hidden oracle

Outputs were returned one week later and appended to the dataset

Query generation strategy

Early rounds: heuristic and exploratory sampling

Mid rounds: surrogate-guided refinement

Later rounds: Bayesian optimisation using Gaussian Processes

Matern kernels with noise terms

Expected Improvement (EI), UCB, and exploration parameters (ξ, β)

Sobol sampling for candidate generation

Time frame

Data collected over ten weekly iterations

One evaluation per function per week

4. Preprocessing and Intended Uses

Preprocessing

Outputs standardised for surrogate modelling

No dimensionality reduction applied

No synthetic data augmentation

Intended uses

Studying Bayesian optimisation under limited budgets

Analysing convergence, stagnation, and emergent behaviour

Educational demonstration of black-box optimisation concepts

Inappropriate uses

Benchmarking deterministic optimisers

Drawing conclusions about real-world physical systems

Training supervised models without acknowledging sparsity and bias

5. Distribution and Maintenance

Where is the dataset available?

Public GitHub repository (linked in README)

Terms of use

Educational and research use only

No guarantee of completeness or representativeness

Maintenance

Maintained by the repository owner (capstone author)

Updated weekly as new iterations are completed
