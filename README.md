# Koopman-Based Linear Embeddings for Control of Automated Agents

**Status: manuscript in preparation; not submitted or published.**

This repository contains the LaTeX source and evaluation protocol for a study of finite-dimensional lifted models learned from transition data.

## Files
- paper/main.tex — manuscript source
- paper/EXPERIMENT_PROTOCOL.md — systems, baselines, splits, metrics, and ablations
- modular notes in paper/ — abstract, method, claims, limitations, reproducibility
- Makefile — local PDF build target

## Build
Requires LaTeX with geometry, AMS math, booktabs, and hyperref packages.

    make pdf
    make clean

## Evidence boundary
The companion lab implements a scalar polynomial lifting and regularized EDMD-style fit. It does not establish an invariant Koopman subspace, physical-system validity, or control performance. No benchmark results are claimed until the protocol is executed.

Companion code: https://github.com/Hafiz-IIT/koopman-control-lab
