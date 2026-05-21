## Overall Insight

Rotate azimuth by pi/4 to get cube in standard form. Write F_A = partial_psi G_A, F_B = F_A(psi+pi). Decompose C = F_A+F_B, D = F_A-F_B. Use quarter-turn (pi/2) symmetry of the full cube to fold the phi-integral over [0,2pi) down to [0,pi/2), obtaining I = -integral Xi dmu where Xi = (1/2)D^2 + (1/2)(D circ R_{pi/2})^2 - C^2.

### Subproblem 2: Rewrite the target integral as a quarter-turn defect

**Statement**: Let d(mu^+ + mu^-) = rho(theta,psi)*sin(theta) d theta d psi where mu^pm are probability measures with densities exp(±u)/I^pm and u = 2*pi * sum_{i=1}^8 G_i; with F_A, C, D as in Subproblem 1, define
  Xi(theta,psi) = (1/2)*D(theta,psi)^2 + (1/2)*D(theta, psi+pi/2)^2 - C(theta,psi)^2.
Prove that rho(theta, psi+pi/2) = rho(theta, psi), that C(theta, psi+pi/2) = C(theta, psi), and that
  I = integral_{S^2} F_A(theta,psi) * F_A(theta,psi+pi) d(mu^+ + mu^-)
    = -integral_0^pi integral_0^{pi/2} Xi(theta,psi) * rho(theta,psi) * sin(theta) d psi d theta.

**Role**: This is the key reduction: it replaces the original cross-term by a single defect Xi on one fundamental sector, where the sign is much more tractable.

**Approach**: Use the pi/2-invariance of the full cube and of u, hence of rho; partition the psi-circle into four quarter-turn intervals; then rewrite F_A*F_B via F_B = F_A(psi+pi) and the identities F_A*F_B = (1/4)(C^2-D^2) and C(psi+pi/2) = C(psi). Key steps:
  - F_A = (C+D)/2, F_B = (C-D)/2, so F_A*F_B = (C^2-D^2)/4.
  - integral_0^{2pi} D(psi)^2 * rho(psi) dpsi = integral_0^{pi/2} [D(psi)^2 + D(psi+pi/2)^2 + D(psi+pi)^2 + D(psi+3pi/2)^2] * rho(psi) dpsi.
  - Note D(psi+pi) = -D(psi) (pi-antiperiodicity), so D(psi)^2 = D(psi+pi)^2.
  - Similarly D(psi+pi/2+pi) = -D(psi+pi/2), so D(psi+pi/2)^2 = D(psi+3pi/2)^2.
  - Therefore integral_0^{2pi} D^2 rho dpsi = 2*integral_0^{pi/2} [D^2 + D(psi+pi/2)^2] rho dpsi.
  - integral_0^{2pi} C^2 rho dpsi = 4*integral_0^{pi/2} C^2 rho dpsi (pi/2-periodicity of C and rho).
  Combining: I = (1/4)*(4 int C^2 rho dpsi - 2 int [D^2 + D(psi+pi/2)^2] rho dpsi) / (4) ... actually work carefully.

## Integration Sketch

[Same as hint_section_1.md]
Subproblem 1 gives explicit formulas for C, D. Subproblem 2 rewrites I = -int Xi dmu. Subproblem 3 proves Xi >= 0. Subproblem 4 gives I < 0. Subproblem 5 uses Schur's lemma to conclude positivity on all of T_{2g}.
