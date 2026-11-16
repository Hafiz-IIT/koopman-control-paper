# Experiment protocol — scalar Koopman lifted-dynamics prediction, v0.1

## Research question

Does a finite-dimensional polynomial EDMD-style model improve one-step and multi-step prediction over persistence and a fitted affine linear baseline on controlled synthetic scalar systems?

## Synthetic systems

The experiment uses five deterministic maps:

- Cubic contraction: (f(x)=0.85x-0.12x^3)
- Sinusoidal contraction: (f(x)=0.75x+0.10\sin(2x))
- Tanh contraction: (f(x)=0.70x+0.08\tanh(2x))
- Quadratic-affine contraction: (f(x)=0.70x+0.12x^2+0.03)
- Piecewise regime shift: (f(x)=0.78x+0.06\sin(2x)+0.08\,\mathrm{sign}_+(x-0.25)), where the final term is (+0.08) for (x\geq0.25) and (-0.08) otherwise.

These are known synthetic functions, not measured physical systems.

## Data and splits

For each of ten independent seeds (0–9) and each system:

- 600 independent training state-transition pairs, with states sampled uniformly from [-1, 1].
- 300 independent in-distribution test pairs from a separate seed stream, also sampled from [-1, 1].
- 300 out-of-range test pairs from a separate seed stream, sampled uniformly from [-1.5, 1.5].
- 100 independent rollout initial states sampled from [-1, 1], each evaluated for 20 steps.

The state samples are independent draws, not a chronological time-series split. Train, test, OOD, and rollout streams use distinct deterministic seed offsets.

## Models

- Persistence baseline: \hat{x}_{t+1}=x_t.
- Affine linear baseline: EDMD with degree-1 dictionary.
- EDMD ablations: polynomial dictionaries of degrees 2 and 3.

The dictionary is φ_d(x)=(1,x,x^2,...,x^d). The constant observable is not ridge-penalized. Ridge is fixed at 1e-8 before test evaluation; no test-set tuning is performed.

## Metrics and aggregation

Report one-step RMSE and maximum absolute error, OOD one-step RMSE and maximum absolute error, and 20-step rollout RMSE and maximum absolute error. Report per-seed results and aggregate mean, sample standard deviation, and two-sided 95% t-intervals across seeds (df=9).

## Completed v0.1 evidence

The v0.1 runner completed 200 per-seed model evaluations (5 systems × 10 seeds × 4 methods) and generated machine-readable per-seed and aggregate CSVs. The aggregate summary is committed in the companion lab repository; the full CSV outputs are archived in the GitHub Actions artifact for the benchmark run.

## Not yet evaluated

- Ridge-coefficient sensitivity.
- Training-sample-size and training-coverage sweeps.
- Noisy observations or noisy transitions.
- Higher-dimensional systems.
- Closed-loop control or MPC.

These are follow-up experiments, not completed results.

## Scope and limitations

This is a scalar synthetic prediction study. It does not establish an invariant Koopman subspace, control/MPC utility, high-dimensional agent performance, physical-system validity, or safety. Multi-step lifted predictions are iterated in lifted space without projecting back to the nonlinear image of the lifting map.
