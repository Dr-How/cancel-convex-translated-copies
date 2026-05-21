## Overall Insight

This is an analysis/variational problem on S^2 with a heavy symmetry and representation-theoretic component. The Hessian formula is already reduced to a weighted integral of Green-function derivatives, so the real issue is to prove the sign of that integral for the specific T_{2g} deformation. A direct pointwise sign argument on (partial_phi G_A)(partial_phi G_B) is the wrong level of granularity here, because some individual cross-pairs are genuinely positive; likewise, a pair-by-pair matrix estimate obscures the cancellation.

The natural attack is to rotate the azimuth by pi/4, so the cube becomes the standard (±1,±1,±1)/sqrt(3) cube and the T_{2g} sign pattern becomes the checkerboard condition eps_1*eps_3 > 0 or < 0. Then write F_A = partial_psi G_A, F_B = F_A ∘ R_pi, and decompose into C := F_A + F_B and D := F_A - F_B. Using the quarter-turn invariance of the full cube and of the measures mu^pm, the original integral can be rewritten on one fundamental sector as the integral of a single "defect"
  -Xi,  Xi = (1/2)*D^2 + (1/2)*(D ∘ R_{pi/2})^2 - C^2.
So the problem becomes an explicit algebraic inequality for rational functions in x,y,z. This is the concrete, real-variable version of the Fourier-sector heuristic: instead of tracking many mixed terms, one compares the 4-fold symmetric part against the two quarter-turn-related T_{2g} companions all at once.

### Subproblem 1: Standardize the cube and write the T_{2g} mode explicitly

**Statement**: Let psi = phi - pi/4, let x = sin(theta)cos(psi), y = sin(theta)sin(psi), z = cos(theta), and let q_{eps1,eps2,eps3} = (eps1,eps2,eps3)/sqrt(3) in S^2 for eps_j in {±1}; prove that the eight cube vertices are exactly the q_{eps}, that A = {q_eps : eps_1*eps_3 = 1} and B = {q_eps : eps_1*eps_3 = -1}, and that, for G_q(z) = -(1/(2*pi)) log sin(dist(z,q)/2),
  F_A(theta,psi) := partial_psi sum_{q in A} G_q(theta,psi)
    = (1/(4*pi*sqrt(3))) * sum_{eps: eps_1*eps_3=1} (eps_2*x - eps_1*y) / (1 - (eps_1*x + eps_2*y + eps_3*z)/sqrt(3)),
so F_B(theta,psi) = F_A(theta,psi+pi), and therefore
  C(theta,psi) := F_A(theta,psi) + F_A(theta,psi+pi)
    = (1/(4*pi*sqrt(3))) * sum_{all eps} (eps_2*x - eps_1*y) / (1 - (eps_1*x + eps_2*y + eps_3*z)/sqrt(3)),
  D(theta,psi) := F_A(theta,psi) - F_A(theta,psi+pi)
    = (1/(4*pi*sqrt(3))) * sum_{all eps} eps_1*eps_3 * (eps_2*x - eps_1*y) / (1 - (eps_1*x + eps_2*y + eps_3*z)/sqrt(3)).

**Role**: This puts the geometry into the standard cube coordinates and converts the abstract Green-function sum into explicit rational functions F_A, C, and D, which are the inputs for the later sign computation.

**Approach**: Rotate the azimuth by pi/4, identify the cube with (±1,±1,±1)/sqrt(3), use sin^2(dist(z,q)/2) = (1/2)(1 - z.q), and differentiate G_q = -(1/(4*pi)) log(1 - z.q) + const with respect to psi. Note that partial_psi x = -y and partial_psi y = x.

## Integration Sketch

Subproblem 1 rotates the azimuth by pi/4, identifies the cube with the standard (±1,±1,±1)/sqrt(3) model, and gives explicit formulas for F_A, hence for the symmetric part C = F_A + F_B and the T_{2g} part D = F_A - F_B. Subproblem 2 uses the quarter-turn symmetry of the full cube and of the measures mu^pm to rewrite the desired integral as
  I = -integral Xi d(mu^+ + mu^-)
over one fundamental sector, where Xi = (1/2)*D^2 + (1/2)*(D ∘ R_{pi/2})^2 - C^2. Subproblem 3 is the hard algebraic step: it proves Xi >= 0 everywhere in that sector and Xi > 0 on a set of positive measure, with the singular terms cancelling so that Xi is integrable. Subproblem 4 then gives I < 0. Finally, the Hessian identity Q(v,v) = -16*pi^2 * I shows positivity on the chosen nonzero generator v in T_{2g}, and Subproblem 5 upgrades that by G-invariance and irreducibility to positive definiteness on all of T_{2g}.
