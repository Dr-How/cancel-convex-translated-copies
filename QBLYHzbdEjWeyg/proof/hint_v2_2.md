## Overall Insight

Reparameterize S^2 by (x, psi) around the x-axis. G_B = G_A(x, psi-pi/2) and w is pi/2-periodic. The proof reduces to a slice-by-slice anti-correlation argument on x-circles.

## Subproblem 2: Reparameterize by x-circles and expose the quarter-shift relation

**Statement**: Parameterize S^2 \ {+/-(1,0,0)} by
  q(x,psi) = (x, sqrt(1-x^2)*sin(psi), sqrt(1-x^2)*cos(psi)),
  x in (-1,1), psi in R/2piZ.

Define F(x,psi) = G_A(q(x,psi)) and w(x,psi) = w(q(x,psi)). Prove that:
  (i)  G_B(q(x,psi)) = F(x, psi - pi/2),
  (ii) w(x, psi + pi/2) = w(x, psi),
  (iii) dA = dx dpsi (Jacobian is 1),
  (iv) partial_phi = -sqrt(1-x^2)*sin(psi)*partial_x + (x*cos(psi)/sqrt(1-x^2))*partial_psi.

**Approach for (i)**: The B-vertices are the image of A-vertices under R_x: (x,y,z) |-> (x,z,-y). Check that q(x,psi-pi/2) = R_x^{-1}(q(x,psi)):
  q(x,psi-pi/2) = (x, sqrt(1-x^2)*sin(psi-pi/2), sqrt(1-x^2)*cos(psi-pi/2))
                = (x, -sqrt(1-x^2)*cos(psi), sqrt(1-x^2)*sin(psi))
  R_x^{-1}(x,y,z) = (x,-z,y) [inverse of R_x(x,y,z)=(x,z,-y)].
  R_x^{-1}(q(x,psi)) = (x, -sqrt(1-x^2)*cos(psi), sqrt(1-x^2)*sin(psi)). Same. ✓
  So G_B(q(x,psi)) = G_A(R_x^{-1}(q(x,psi))) = G_A(q(x,psi-pi/2)) = F(x,psi-pi/2).

**Approach for (ii)**: The full 8-vertex cube is R_x-symmetric (R_x permutes B-vertices among themselves and A-vertices among themselves). So u and hence rho^pm and w are R_x-invariant. R_x sends q(x,psi) to q(x,psi+pi/2), giving w(x,psi+pi/2) = w(x,psi).

**Approach for (iii)**: Direct Jacobian computation. q_x = (1, -x*sin(psi)/sqrt(1-x^2), -x*cos(psi)/sqrt(1-x^2)), q_psi = (0, sqrt(1-x^2)*cos(psi), -sqrt(1-x^2)*sin(psi)). Area element |q_x x q_psi| = 1.

**Approach for (iv)**: partial_phi = -y*partial_x_coord + x*partial_y_coord. Express x_coord, y_coord, z_coord in (x,psi), then compute.

## Integration Sketch

This is the structural reduction step that enables the slice-wise argument.
