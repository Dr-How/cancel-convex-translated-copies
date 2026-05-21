## Overall Insight

The core difficulty is Subproblem 3: proving Xi = (1/2)D^2 + (1/2)(D circ R_{pi/2})^2 - C^2 >= 0, where C and D are explicit rational functions of (x,y,z) on S^2. The strategy is to substitute the explicit formulas from Subproblem 1, clear denominators to get a polynomial inequality, and then factor the polynomial into a manifestly nonneg expression. A CAS (SageMath, Mathematica, or sympy) can help discover the factorization; the written proof should record the exact algebraic identity.

### Subproblem 3: Prove the defect is nonnegative and nontrivial

**Statement**: With F_A, C, D, Xi as in Subproblems 1-2, prove that Xi extends to a locally integrable function on the fundamental sector (0,pi) x (0,pi/2), satisfies
  Xi(theta,psi) >= 0
for every (theta,psi) in (0,pi) x (0,pi/2) away from the two vertex singularities, and is strictly positive on a subset of positive (theta,psi)-measure.

**Role**: This is the decisive sign computation. Once Xi >= 0 and not identically zero, the integral in Subproblem 2 is automatically negative.

**Approach**: Substitute the explicit rational formulas from Subproblem 1 into Xi, clear denominators, and simplify in the region x = sin(theta)cos(psi) > 0, y = sin(theta)sin(psi) > 0. The goal is to make the cancellation of the singular leading terms explicit and factor the remaining numerator into manifestly nonneg pieces.

Concretely:
1. C(theta,psi) = (1/(4*pi*sqrt(3))) * sum_{eps in {±1}^3} (eps_2*x - eps_1*y) / (1 - (eps_1*x+eps_2*y+eps_3*z)/sqrt(3)).
   Note: the numerator (eps_2*x - eps_1*y) can be written as the i-th component of a cross product or as the azimuthal derivative of the dot product eps.z.

2. D(theta,psi) = (1/(4*pi*sqrt(3))) * sum_{eps} eps_1*eps_3 * (eps_2*x - eps_1*y) / (1 - eps.z_vec/sqrt(3)).

3. D(theta,psi+pi/2) is obtained by substituting (x,y) -> (-y,x):
   D(theta,psi+pi/2) = (1/(4*pi*sqrt(3))) * sum_{eps} eps_1*eps_3 * (-eps_2*y - eps_1*x) / (1 - (eps_1*(-y)+eps_2*x+eps_3*z)/sqrt(3)).
   = -(1/(4*pi*sqrt(3))) * sum_{eps} eps_1*eps_3 * (eps_2*y + eps_1*x) / (1 - (-eps_1*y+eps_2*x+eps_3*z)/sqrt(3)).

4. Let Delta_eps = 1 - (eps_1*x+eps_2*y+eps_3*z)/sqrt(3) and Delta = product_{eps} Delta_eps.
   Then C, D, D' = D(psi+pi/2) are rational functions with denominator product of Delta_eps.

5. The key algebraic identity to prove:
   (Delta_product)^2 * Xi = (nonneg expression).

   Alternative: Factor Xi by grouping terms. The full 8x8 sum has a lot of symmetry.

   Key simplification: Let's pair up terms. In C:
     pair (+,eps_2,+) with (-,eps_2,-) and pair (+,eps_2,-) with (-,eps_2,+).
   These groups simplify dramatically.

   Specifically, for eps_3 = +1 and eps_3 = -1 contributions, with eps_1 = eps_1':
     Term with (eps_1, eps_2, +1): (eps_2*x - eps_1*y) / (1 - (eps_1*x+eps_2*y+z)/sqrt(3))
     Term with (eps_1, eps_2, -1): (eps_2*x - eps_1*y) / (1 - (eps_1*x+eps_2*y-z)/sqrt(3))
   Their sum is (eps_2*x - eps_1*y) * [(Delta_{eps,-1} + Delta_{eps,+1}) / (Delta_{eps,+1} * Delta_{eps,-1})]
     = (eps_2*x - eps_1*y) * 2 / ((1-(eps_1*x+eps_2*y)/sqrt(3))^2 - (z/sqrt(3))^2).

   Similarly the eps_1*eps_3 factor in D:
     eps_1*(+1): (eps_1, eps_2, +1) contributes +eps_1 weight
     eps_1*(-1): (eps_1, eps_2, -1) contributes -eps_1 weight
   Their D-combination: (eps_2*x - eps_1*y) * eps_1 * [(Delta_{eps,-1} - Delta_{eps,+1}) / (Delta_{eps,+1} * Delta_{eps,-1})]
     = (eps_2*x - eps_1*y) * eps_1 * (2z/sqrt(3)) / (denominator).

6. After this eps_3-pairing, both C and D become sums over only (eps_1, eps_2) in {±1}^2:
   Define a_ij = (eps_2*x - eps_1*y) and b_ij = (1 - (eps_1*x+eps_2*y)/sqrt(3)) and c = z/sqrt(3):
   C = (1/(2*pi*sqrt(3))) * sum_{eps_1,eps_2} a_{eps} * b_{eps} / (b_{eps}^2 - c^2)
   D = (1/(2*pi*sqrt(3))) * sum_{eps_1,eps_2} a_{eps} * eps_1 * c / (b_{eps}^2 - c^2)

   Then Xi = D^2/2 + D'^2/2 - C^2 where D' = D(psi+pi/2).

7. The positive contribution to C^2 should be cancelled or dominated by D^2 + D'^2 in the sector x>0, y>0.

**Suggestion**: Use a CAS to verify Xi >= 0 numerically on a grid first, then look for an algebraic certificate.

## Integration Sketch

Subproblem 1 gives C, D as explicit rational functions. Subproblem 2 rewrites I = -integral Xi dmu. Subproblem 3 (this subproblem) proves Xi >= 0. Subproblem 4 then gives I < 0. Subproblem 5 concludes by Schur's lemma.
