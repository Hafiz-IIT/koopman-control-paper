# Experiment protocol — Koopman-based lifted dynamics

## Claim under test
A finite-dimensional polynomial lifting may improve held-out prediction over simple baselines on selected nonlinear scalar systems.

## Systems
Start with declared synthetic maps (stable nonlinear contraction, weakly nonlinear map, and a map with a regime change). Publish exact equations and parameter ranges before evaluation.

## Splits and baselines
Use chronological transition splits. Compare persistence, fitted linear-in-state regression, and EDMD-style polynomial dictionaries at degrees 1–3. Keep out-of-range states as a separate stress test.

## Metrics
One-step RMSE, multi-step RMSE at fixed horizons, maximum absolute error, and error growth across rollout horizon.

## Ablations
Dictionary degree, ridge coefficient, sample count, and training-state coverage.

## Current evidence
The current implementation fits a small scalar model. It does not establish an invariant Koopman subspace or control utility; no benchmark result is claimed.
