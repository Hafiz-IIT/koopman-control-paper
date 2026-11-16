# Limitations

The v0.1 study is limited to five deterministic synthetic scalar maps and ten fixed seeds. It uses independent state-transition pairs, a fixed ridge coefficient, and a constant-augmented monomial dictionary through degree three.

The study does not include observation or transition noise, parameter uncertainty, ridge-coefficient sensitivity, sample-size/coverage sweeps, higher-dimensional systems, chronological trajectory splits, or closed-loop control/MPC. Multi-step lifted predictions are iterated without projection back onto the nonlinear image of the lifting map. The implementation uses regularized normal equations, which can amplify conditioning problems as dictionary dimension grows.

No physical-system, robotic, safety, or invariant-subspace claim is established.
