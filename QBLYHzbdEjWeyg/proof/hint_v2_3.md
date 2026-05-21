## Overall Insight

Reparameterize S^2 by (x, psi) around the x-axis. G_B = G_A(x, psi-pi/2) and w is pi/2-periodic. The proof reduces to a slice-by-slice anti-correlation argument on x-circles.

## Subproblem 3: Monotonicity and sign structure of the common profile F

**Statement**: With F(x,psi) = G_A(q(x,psi)) = -(1/(4pi)) * log P_A(x, sqrt(1-x^2)*cos(psi)) + C_A,
where P_A(x,z) = ((1-az)^2 - b^2x^2)((1+az)^2 - b^2x^2) with a=sqrt(2/3), b=1/sqrt(3):

For each fixed x in (0,1), prove that psi |-> F(x,psi) is:
  (a) Even in psi: F(x,-psi) = F(x,psi).
  (b) Pi-periodic: F(x, psi+pi) = F(x,psi).
  (c) Strictly decreasing on (0, pi/2): F_psi(x,psi) < 0 for psi in (0,pi/2).

Also prove that for psi in (0, pi/2):
  (d) F_x(x,psi) > 0.

**Approach for (a) and (b)**:
(a) z = sqrt(1-x^2)*cos(psi) is even in psi, so P_A(x,z) is even in psi. ✓
(b) z is pi-periodic in psi (cos(psi+pi) = -cos(psi)): P_A(x,-z) = P_A(x,z) since P_A involves z only through (az)^2 in (1-az)^2, and the product swaps factors but equals the same. ✓

**Approach for (c)**:
F_psi = -(1/(4pi)) * (partial_psi P_A) / P_A.
partial_psi z = -sqrt(1-x^2)*sin(psi).
partial_psi P_A = (partial_z P_A)(partial_psi z) = (partial_z P_A)(-sqrt(1-x^2)*sin(psi)).
From SP1: partial_z P_A = -4a^2 z (1 - a^2 z^2 + b^2 x^2).
So partial_psi P_A = 4a^2 z (1-a^2z^2+b^2x^2) * sqrt(1-x^2)*sin(psi).
= 4a^2 sqrt(1-x^2)*cos(psi)*(1-a^2z^2+b^2x^2)*sqrt(1-x^2)*sin(psi).

For psi in (0,pi/2): sin(psi)>0, cos(psi)>0, so partial_psi P_A > 0 (need 1-a^2z^2+b^2x^2 > 0: since a^2=2/3 and z^2 <= 1, a^2z^2 <= 2/3 < 1, so 1-a^2z^2 >= 1/3 > 0 ✓).
Hence F_psi = -(positive)/(positive) < 0. ✓

**Approach for (d)**:
F_x = partial_x G_A + (partial_z G_A)*(partial_x z) where partial_x z = -x*cos(psi)/sqrt(1-x^2).
From SP1: partial_x G_A = x(3+2z^2-x^2)/(9pi*P_A), partial_z G_A = 2z(3+x^2-2z^2)/(9pi*P_A).
F_x = (1/(9pi*P_A)) * [x(3+2z^2-x^2) + 2z(-x*cos(psi)/sqrt(1-x^2))*(3+x^2-2z^2)]
    = (x/(9pi*P_A)) * [(3+2z^2-x^2) - 2z*cos(psi)/sqrt(1-x^2)*(3+x^2-2z^2)].
With z = sqrt(1-x^2)*cos(psi): z*cos(psi)/sqrt(1-x^2) = cos^2(psi).
F_x = (x/(9pi*P_A)) * [(3+2z^2-x^2) - 2cos^2(psi)*(3+x^2-2z^2)].
Need to show this is positive for x>0, psi in (0,pi/2).
Substitute z^2 = (1-x^2)cos^2(psi):
3+2z^2-x^2 = 3+2(1-x^2)cos^2(psi)-x^2 = 3+2cos^2(psi)-x^2(1+2cos^2(psi)).
3+x^2-2z^2 = 3+x^2-2(1-x^2)cos^2(psi) = 3+x^2(1+2cos^2(psi))-2cos^2(psi).
The expression in brackets: A - 2cos^2(psi)*B where A = 3+2z^2-x^2, B = 3+x^2-2z^2.
Note A + B = 6, so B = 6-A. Need A - 2cos^2(psi)*(6-A) > 0, i.e., A(1+2cos^2(psi)) > 12cos^2(psi).
Since A = 3+2z^2-x^2 >= 3-x^2 >= 3-1 = 2 > 0 and... this needs careful analysis.

## Integration Sketch

Subproblem 3 provides the monotonicity and sign data needed in Subproblem 5.
