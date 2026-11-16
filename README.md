# Koopman-Lifted Prediction of Scalar Nonlinear Dynamics

**Status: research manuscript in preparation; not submitted or published.**

This repository contains the manuscript and protocol for a reproducible synthetic pilot evaluating finite-dimensional polynomial EDMD-style prediction on five scalar nonlinear maps.

## Files
- `paper/main.tex` — manuscript source and preliminary results
- `paper/EXPERIMENT_PROTOCOL.md` — executed v0.1 systems, data splits, baselines, and metrics
- `paper/claims.md` — claim ledger and evidence boundaries
- `paper/reproducibility.md` — exact companion experiment commands
- `results/manifest.json` — result status, code revision, and workflow provenance

## Build
Requires LaTeX with geometry, AMS math, booktabs, hyperref, and microtype packages.

    make pdf
    make clean

## Evidence boundary
The v0.1 pilot compares persistence, affine linear, and polynomial EDMD models on synthetic scalar maps. It does not establish an invariant Koopman subspace, physical-system validity, or control/MPC performance. The complete machine-readable outputs are generated and archived by the companion lab's GitHub Actions workflow.

Companion code and results: https://github.com/Hafiz-IIT/koopman-control-lab
