# Reproducibility

The canonical implementation and experiment runner are maintained in the companion repository:

https://github.com/Hafiz-IIT/koopman-control-lab

From a clone of that repository:

```bash
python -m unittest discover -s tests -v
python demo.py
python experiment.py
```

The experiment runner uses only the Python standard library. It writes:
- `results/koopman_scalar_per_seed.csv`
- `results/koopman_scalar_summary.csv`
- `results/manifest.json`

The GitHub Actions workflow runs the tests, demo, and experiment and uploads the machine-readable outputs as the `koopman-scalar-benchmark` artifact. The committed result summary and configuration are in the companion lab's `results/` directory.

The v0.1 experiment used ten fixed seeds, five deterministic scalar maps, a fixed ridge coefficient of 1e-8, separate train/test/OOD seed streams, and 20-step rollouts. The exact configuration and output SHA-256 hashes are recorded in the lab result manifest.

This evidence does not establish physical-system validity, Koopman invariance, or control utility.
