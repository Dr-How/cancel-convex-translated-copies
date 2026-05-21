## Overall Insight

Reparameterize S^2 by (x, psi) around the x-axis. G_B = G_A(x, psi-pi/2) and w is pi/2-periodic. The proof reduces to a slice-by-slice anti-correlation argument on x-circles.

## Subproblem 6: Integrate over x and conclude Hessian positivity

**Statement**: Using J(x) < 0 for all x in (0,1) (from Subproblem 5), prove:
  integral_{S^2} (partial_phi G_A)(partial_phi G_B) d(mu^+ + mu^-) = integral_{-1}^{1} J(x) dx < 0,
and therefore:
  Hess_p log J_8(v,v) = -16pi^2 * integral_{S^2} (partial_phi G_A)(partial_phi G_B) d(mu^++mu^-) > 0.

**Approach**:
- From SP2: dA = dx dpsi, so integral_{S^2} ... dA = integral_{-1}^{1} integral_0^{2pi} ... dpsi dx.
- The density w = d(mu^++mu^-)/dA.
- integral_{S^2} (partial_phi G_A)(partial_phi G_B) w dA = integral_{-1}^{1} J(x) dx.
- J(x) < 0 for x in (0,1) [the x in (-1,0) case follows by symmetry: partial_phi G_A is odd in x (check from formula), partial_phi G_B is odd in x, so their product is even in x, and w is even in x (by cube symmetry under x->-x). So J(-x) = J(x)].
- At x=0: the integrand (partial_phi G_A)(partial_phi G_B) may be zero or nonzero. Since J is continuous and negative on (0,1), the integral is strictly negative.

**Final step**: Apply the Hessian formula:
  Hess_p log J_8(v,v) = -16pi^2 * (negative quantity) > 0.
This proves positive definiteness of the Hessian on T_{2g} for the given generator v.

By Schur's lemma (proved separately in Subproblem 5 of the first brainstorm), positive definiteness on one nonzero generator implies positive definiteness on all of T_{2g}.

## Integration Sketch

This is the final assembly step.
