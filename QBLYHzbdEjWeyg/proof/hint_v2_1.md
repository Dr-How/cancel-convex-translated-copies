## Overall Insight

Reparameterize S^2 by (x, psi) around the x-axis. In these coordinates G_B = G_A(x, psi-pi/2) and the weight w is pi/2-periodic. The proof reduces to a slice-by-slice anti-correlation argument: on each x-circle, the mixed terms cancel by symmetry and the remaining quarter-shift correlators have a controlled sign via monotonicity of F = G_A(x,·).

## Subproblem 1: Explicit formulas for G_A, G_B, and partial_phi-derivatives

**Statement**: Let a = sqrt(2/3), b = 1/sqrt(3). Let q = (x,y,z) in S^2 \ {p_1,...,p_8}. Define
  P_A(x,z) = ((1-az)^2 - b^2 x^2)((1+az)^2 - b^2 x^2),
  P_B(x,y) = ((1-ay)^2 - b^2 x^2)((1+ay)^2 - b^2 x^2).

Prove:
  G_A(q) = -(1/(4pi)) * log P_A(x,z) + C_A,
  G_B(q) = -(1/(4pi)) * log P_B(x,y) + C_B,

and:
  partial_phi G_A(q) = -xy(3 + 2z^2 - x^2) / (9pi * P_A(x,z)),
  partial_phi G_B(q) = xy(1 + x^2 - 2y^2) / (3pi * P_B(x,y)).

Also prove that the density w = d(mu^+ + mu^-)/dA is positive and invariant under the quarter-turn R_x(x,y,z) = (x, z, -y).

**Approach**: Use G_p(q) = -(4pi)^{-1} log(1 - q.p) + const, pair opposite vertices in A and B, differentiate the log-products. For partial_phi G_A: G_A depends only on (x,z), so partial_y G_A = 0, and partial_phi G_A = -y * partial_x G_A. For partial_phi G_B: both partial_x G_B and partial_y G_B contribute.

Key calculation: partial_x P_A = -4b^2 x(1 + a^2 z^2 - b^2 x^2), giving partial_x G_A = b^2 x(1+a^2z^2-b^2x^2)/(pi P_A) = x(3+2z^2-x^2)/(9pi P_A).

## Integration Sketch

This subproblem provides the algebraic foundation for the entire proof.
