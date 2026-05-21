## Overall Insight

Reparameterize S^2 by (x, psi) around the x-axis. G_B = G_A(x, psi-pi/2) and w is pi/2-periodic. The proof reduces to a slice-by-slice anti-correlation argument on x-circles.

## Subproblem 4: Reduce each x-slice to a weighted quarter-shift correlation integral

**Statement**: For x in (0,1), define
  J(x) = integral_0^{2pi} (partial_phi G_A)(q(x,psi)) * (partial_phi G_B)(q(x,psi)) * w(x,psi) dpsi.

Prove the identity:
  J(x) = integral_0^{2pi} [(1-x^2)*sin^2(psi)*F_x(x,psi)*F_x(x,psi-pi/2)
          + (x^2*cos^2(psi)/(1-x^2))*F_psi(x,psi)*F_psi(x,psi-pi/2)] * w(x,psi) dpsi.

**Approach**:
From Subproblem 2: partial_phi = -sqrt(1-x^2)*sin(psi)*partial_x + (x*cos(psi)/sqrt(1-x^2))*partial_psi.

So:
partial_phi G_A = -sqrt(1-x^2)*sin(psi)*F_x + (x*cos(psi)/sqrt(1-x^2))*F_psi,
partial_phi G_B = partial_phi G_A(x,psi-pi/2) [using G_B = F(x,psi-pi/2)]
               = -sqrt(1-x^2)*sin(psi)*F_x(x,psi-pi/2) + (x*cos(psi)/sqrt(1-x^2))*F_psi(x,psi-pi/2).

Wait, need to be careful: when we compute partial_phi G_B at q(x,psi), we use
partial_phi G_B = d/dphi G_B where phi is the original azimuth. But in (x,psi) coordinates,
partial_phi at fixed x changes psi (since phi and psi differ by a fixed rotation). Actually,
partial_phi in (x,psi) coordinates: since psi = phi - pi/2 + (angle of xz-plane), and actually
the x-circle parameterization has psi the angle in the yz-plane. We need:
partial_phi = partial_psi (in the (x,psi) parameterization).
So partial_phi acting on G_B(x,psi) = F(x,psi-pi/2) gives F_psi(x,psi-pi/2).

Actually, more carefully: partial_phi in the ORIGINAL (theta,phi) coordinates corresponds to
partial_psi in the (x,psi) coordinates (since psi = phi + const along each circle). So:
partial_phi G_A(q(x,psi)) = F_psi... NO, that's not right either because there is a constraint
x^2+y^2+z^2=1 and partial_phi moves on S^2.

Correct approach: From the formula in SP2:
partial_phi = -sqrt(1-x^2)*sin(psi)*partial_x + (x*cos(psi)/sqrt(1-x^2))*partial_psi.
This is the operator partial_phi expressed in (x,psi) coordinates.

So:
(partial_phi G_A)(q(x,psi)) = -sqrt(1-x^2)*sin(psi)*F_x(x,psi) + (x*cos(psi)/sqrt(1-x^2))*F_psi(x,psi).

For partial_phi G_B at q(x,psi): G_B(q(x,psi)) = F(x,psi-pi/2), so the same operator applies:
(partial_phi G_B)(q(x,psi)) = -sqrt(1-x^2)*sin(psi)*F_x(x,psi-pi/2) + (x*cos(psi)/sqrt(1-x^2))*F_psi(x,psi-pi/2).

Product:
(partial_phi G_A)(partial_phi G_B) = [(1-x^2)sin^2(psi) * F_x(x,psi)*F_x(x,psi-pi/2)]
  + [x^2cos^2(psi)/(1-x^2) * F_psi(x,psi)*F_psi(x,psi-pi/2)]
  - [sin(psi)cos(psi)*x * (F_x(x,psi)*F_psi(x,psi-pi/2) + F_psi(x,psi)*F_x(x,psi-pi/2))].

The mixed terms: integral_0^{2pi} sin(psi)cos(psi)*f(psi)*g(psi-pi/2)*w(x,psi) dpsi.
Use w(x,psi+pi/2)=w(x,psi) (pi/2-periodic). Substitute psi -> psi+pi/2 in part of the integral,
use F even and pi-periodic to see F_x(x,psi+pi/2)=F_x(x,psi+pi/2) and sin(psi+pi/2)=cos(psi),
cos(psi+pi/2)=-sin(psi). This shows the mixed term integral vanishes by the pi/2-periodicity of w
and a parity argument.

Key: F_x(x,psi) is even and pi-periodic in psi (since F is). So F_x(x,psi+pi/2)*w(x,psi) and similar
expressions, after the substitution, produce a cancellation.

## Integration Sketch

This algebraic reduction is crucial: it produces a sum of two terms, each with known sign from SP3.
