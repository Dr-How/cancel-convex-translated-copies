## Overall Insight

Once Xi >= 0 a.e. and not identically zero, and the density rho is strictly positive a.e., the integral I = -integral Xi rho dA is strictly negative. This is a one-line application of the positivity of a positive measure times a nonneg nontrivial function.

### Subproblem 4: Convert the defect inequality into the target sign I < 0

**Statement**: Let rho > 0 a.e. and suppose
  I = -integral_0^pi integral_0^{pi/2} Xi(theta,psi) * rho(theta,psi) * sin(theta) d psi d theta,
where Xi is locally integrable, nonneg a.e., and positive on a set of positive measure. Prove I < 0.

**Role**: Turns the local inequality from Subproblem 3 into the exact integral sign.

**Approach**: The measure rho(theta,psi)*sin(theta) d psi d theta is a positive measure. The integrand Xi is a nonneg nontrivial function. The integral is strictly positive, so I is strictly negative.

## Integration Sketch

Subproblems 1-3 establish that I = -integral Xi dmu with Xi >= 0 and Xi not identically zero. Subproblem 4 concludes I < 0. Subproblem 5 uses Schur's lemma to get positivity on all of T_{2g}.
