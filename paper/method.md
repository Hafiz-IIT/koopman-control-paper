# Method

The v0.1 implementation maps a scalar state to the polynomial dictionary

`(1, x, x², ..., x^d)`

and fits a finite-dimensional EDMD-style operator from paired scalar transitions using ridge-regularized least squares. The constant observable is not penalized. The stored matrix convention is documented in the companion implementation.

The experiment compares persistence, degree-one EDMD (an affine linear baseline), and degree-two and degree-three dictionaries. Multi-step predictions iterate the fitted linear operator in lifted space without projecting back onto the nonlinear lifting manifold. This is a finite-dimensional empirical approximation, not a proof of Koopman invariance.
