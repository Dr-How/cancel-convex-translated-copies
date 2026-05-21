## Overall Insight

Reparameterize S^2 by (x, psi) around the x-axis. G_B = G_A(x, psi-pi/2) and w is pi/2-periodic. The proof reduces to a slice-by-slice anti-correlation argument on x-circles.

## Subproblem 5: Prove the slice-wise anti-correlation inequality

**Statement**: With F(x,psi), w(x,psi) as in Subproblems 2-4, prove that for every x in (0,1):
  J(x) = integral_0^{2pi} [(1-x^2)sin^2(psi)*F_x(x,psi)*F_x(x,psi-pi/2)
          + x^2cos^2(psi)/(1-x^2)*F_psi(x,psi)*F_psi(x,psi-pi/2)] * w(x,psi) dpsi <= 0,
with J(x) < 0 for a positive-measure set of x in (0,1).

**Key signs from Subproblem 3**:
- F_psi(x,psi) < 0 for psi in (0,pi/2).
- F_psi(x,psi-pi/2) for psi in (0,pi/2): psi-pi/2 in (-pi/2,0). By evenness of F in psi,
  F(x,-eta) = F(x,eta), so F_psi(x,-eta) = -F_psi(x,eta) < 0... wait:
  F_psi(x,-eta) = -F_psi(x,eta), so for eta=pi/2-psi in (0,pi/2):
  F_psi(x,psi-pi/2) = F_psi(x,-(pi/2-psi)) = -F_psi(x,pi/2-psi).
  Since pi/2-psi in (0,pi/2), F_psi(x,pi/2-psi) < 0, so F_psi(x,psi-pi/2) > 0.
  Therefore: F_psi(x,psi)*F_psi(x,psi-pi/2) = (negative)*(positive) < 0 for psi in (0,pi/2). ✓

- F_x(x,psi) > 0 for psi in (0,pi/2) (from SP3 part d).
- F_x(x,psi-pi/2) for psi in (0,pi/2): psi-pi/2 in (-pi/2,0). F_x is even in psi (since F is even),
  so F_x(x,psi-pi/2) = F_x(x,pi/2-psi) > 0 (since pi/2-psi in (0,pi/2)).
  Therefore: F_x(x,psi)*F_x(x,psi-pi/2) > 0 for psi in (0,pi/2). -- THIS IS POSITIVE! ✗

So the two terms have OPPOSITE signs. The hard inequality is showing the F_psi term dominates.

**Strategy**:
Fold the integral over [0,2pi) into [0,pi/2) using pi/2-periodicity of all factors:
  J(x) = 4 * integral_0^{pi/2} [(1-x^2)sin^2(psi)*F_x*F_x(psi-pi/2)
                                  + x^2cos^2(psi)/(1-x^2)*F_psi*F_psi(psi-pi/2)] * w dpsi.

Within [0,pi/2), by the sign analysis: the second term is negative (good), the first is positive (bad).
We need to prove |second term| >= |first term|, i.e.,:
  x^2cos^2(psi)/(1-x^2)*|F_psi*F_psi(psi-pi/2)| >= (1-x^2)sin^2(psi)*F_x*F_x(psi-pi/2).

This might follow from a comparison of the sizes of F_x and F_psi.

**Alternative approach via the paper's Lemma**:
The paper's Lemma (in Section 3 of problem.tex) is:
  If f(theta,phi) is odd in phi, negative and strictly monotonically increasing in phi on (0,pi), and rho has the right symmetry, then:
    K_1 = integral f(theta,phi)*f(theta,phi-pi/2)*rho dA < 0.

We can try to apply this Lemma (or its proof technique) directly to J(x) on each circle.

On each circle x = const, the function psi |-> F_psi(x,psi) is:
- Odd in psi (since F is even).
- Negative for psi in (0,pi/2).
- Pi-periodic (since F is pi-periodic, its derivative is too).

The product F_psi(psi)*F_psi(psi-pi/2) is then like K_1 in the Lemma (with f = F_psi).

Similarly for F_x: it's even in psi (since F is even), not odd.

The key might be to write J(x) as a correlation of partial_phi G_A with itself shifted by pi/2.
Define h(x,psi) = partial_phi G_A(q(x,psi)) = -sqrt(1-x^2)*sin(psi)*F_x + x*cos(psi)/sqrt(1-x^2)*F_psi.
Then J(x) = integral h(x,psi)*h(x,psi-pi/2)*w(x,psi) dpsi.

By pi/2-periodicity of w: J(x) = integral h(psi)*h(psi-pi/2)*w(psi) dpsi.
This is a "quarter-shift correlator" of h with itself.

The question is: does h have a definite sign on (0,pi/2)?
h(x,psi) = -sqrt(1-x^2)*sin(psi)*F_x + x*cos(psi)/sqrt(1-x^2)*F_psi.
For psi in (0,pi/2): sin(psi) > 0, cos(psi) > 0, F_x > 0, F_psi < 0.
So both terms are negative! h(x,psi) < 0 for psi in (0,pi/2).

Similarly h(x,psi-pi/2) for psi in (0,pi/2) [psi-pi/2 in (-pi/2,0)]:
h is odd in psi (check: F_x is even, sin is odd, so first term is odd; F_psi is odd, cos is even, so second term is also odd). Wait:
- -sqrt(1-x^2)*sin(psi)*F_x: F_x is even, sin(psi) is odd -> this term is odd.
- x*cos(psi)/sqrt(1-x^2)*F_psi: F_psi is odd, cos(psi) is even -> this term is odd.
So h is ODD in psi! Therefore h(x,psi-pi/2) = h(x,-(pi/2-psi)) = -h(x,pi/2-psi).
For pi/2-psi in (0,pi/2): h(x,pi/2-psi) < 0, so h(x,psi-pi/2) > 0.

Therefore: h(x,psi)*h(x,psi-pi/2) = (negative)*(positive) < 0 for ALL psi in (0,pi/2)!

Combined with w > 0, this gives J(x) < 0 for all x in (0,1)! ✓

**CONCLUSION**: The proof IS a pointwise sign argument, just applied to h = partial_phi G_A, not to each factor separately. h is odd in psi, negative on (0,pi/2), and hence h*h(psi-pi/2) < 0 everywhere in (0,pi/2).

Please verify this carefully and write a rigorous proof of J(x) <= 0 based on:
1. h(x,psi) is odd in psi.
2. h(x,psi) < 0 for psi in (0,pi/2).
   (Need to verify: both -sqrt(1-x^2)*sin(psi)*F_x and x*cos(psi)/sqrt(1-x^2)*F_psi are negative.)
3. Therefore h(psi)*h(psi-pi/2) < 0 on (0,pi/2), giving J(x) < 0.

## Integration Sketch

The full argument: h = partial_phi G_A is odd in psi and negative in (0,pi/2), so h*h(shifted pi/2) < 0, giving J(x) < 0 for each x, hence the total integral is negative.
