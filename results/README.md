# Results directory

No benchmark results are claimed yet. Store outputs from the protocol in paper/EXPERIMENT_PROTOCOL.md here.

Expected files:
- experiment_config.json — data-generating equations, seed, dictionary degree, ridge coefficient, and split boundary
- summary.csv — baseline and EDMD-style metrics by system and rollout horizon
- predictions/ — optional held-out predictions for reproducibility
- analysis.md — error trends, out-of-range failures, and protocol deviations

Required metrics include one-step RMSE, multi-step RMSE by horizon, maximum absolute error, and error growth. Do not describe a finite polynomial fit as a proven Koopman-invariant subspace.
