## Overall Insight

This is a **geometric analysis / potential theory on the sphere** problem with a strong **finite-group symmetry** input. The object to control is a weighted integral of two azimuthal derivatives of Green-potential sums, and the weight \(d(\mu^++\mu^-)\) is itself built from the full 8-point cube configuration. The decisive structural fact in the new orientation is that the \(B\)-set is obtained from the \(A\)-set by a **quarter-turn about the \(x\)-axis**. That makes it natural to reparameterize \(S^2\) by the coordinate \(x\) and the angle \(\psi\) around the \(x\)-axis.

The key technique is therefore a **slice-by-slice anti-correlation argument on the circles \(x=\mathrm{const}\)**, not a raw global pointwise sign check in \((\theta,\phi)\). In \((x,\psi)\)-coordinates, \(G_B\) becomes a \(\pi/2\)-shift of \(G_A\), while the density of \(\mu^++\mu^-\) becomes \(\pi/2\)-periodic in \(\psi\). This lets one expand \(\partial_\phi\), cancel mixed terms by symmetry, and reduce the whole problem to a weighted comparison between a function and its quarter-period shift on each circle. That bypasses the core difficulty: \(\partial_\phi G_B\) does not have a uniformly usable pointwise sign on an entire quadrant, so the proof has to come from **orbitwise symmetry + monotonicity**, not from a naive everywhere-sign argument.

## Subproblem Decomposition

### Subproblem 1: Explicit formulas for \(G_A\), \(G_B\), and the \(\partial_\phi\)-derivatives

**Statement**: Let \(a=\sqrt{2/3}\), \(b=1/\sqrt3\), let \(q=(x,y,z)\in S^2\setminus\{p_1,\dots,p_8\}\), and define
\[
P_A(x,z):=((1-az)^2-b^2x^2)((1+az)^2-b^2x^2),\qquad
P_B(x,y):=((1-ay)^2-b^2x^2)((1+ay)^2-b^2x^2).
\]
Prove
\[
G_A(q)=-\frac1{4\pi}\log P_A(x,z)+C_A,\qquad
G_B(q)=-\frac1{4\pi}\log P_B(x,y)+C_B,
\]
and
\[
\partial_\phi G_A(q)= -\frac{xy\,(3+2z^2-x^2)}{9\pi\,P_A(x,z)},\qquad
\partial_\phi G_B(q)= \frac{xy\,(1+x^2-2y^2)}{3\pi\,P_B(x,y)}.
\]
Also prove that the density \(w:=d(\mu^++\mu^-)/dA\) is positive and invariant under the quarter-turn \(R_x(x,y,z)=(x,z,-y)\).

**Role**: This converts the geometric setup into exact algebraic formulas and records the symmetry of the measure that will drive the later reduction.

**Approach**: Use \(G_p(q)=-(4\pi)^{-1}\log(1-q\!\cdot\! p)+\text{const}\), pair opposite vertices in each of \(A\) and \(B\), and differentiate the resulting log-products.

**Difficulty**: medium

### Subproblem 2: Reparameterize by \(x\)-circles and expose the quarter-shift relation

**Statement**: Parameterize \(S^2\setminus\{\pm(1,0,0)\}\) by
\[
q(x,\psi)=\bigl(x,\sqrt{1-x^2}\sin\psi,\sqrt{1-x^2}\cos\psi\bigr),\qquad x\in(-1,1),\ \psi\in\mathbb{R}/2\pi\mathbb{Z},
\]
and define \(F(x,\psi):=G_A(q(x,\psi))\) and \(w(x,\psi):=w(q(x,\psi))\). Prove that
\[
G_B(q(x,\psi))=F(x,\psi-\pi/2),\qquad w(x,\psi+\pi/2)=w(x,\psi),\qquad dA=dx\,d\psi,
\]
and
\[
\partial_\phi=-\sqrt{1-x^2}\sin\psi\,\partial_x+\frac{x\cos\psi}{\sqrt{1-x^2}}\,\partial_\psi.
\]

**Role**: This is the structural reduction: it turns the sphere integral into an integral over \(x\)-slices where \(G_B\) is literally a quarter-period translate of \(G_A\).

**Approach**: Use cylindrical coordinates around the \(x\)-axis; the identity for \(G_B\) comes from \(B=R_x(A)\), and the formula for \(\partial_\phi\) follows by differentiating \(x,y,z\) in these coordinates.

**Difficulty**: medium

### Subproblem 3: Monotonicity and sign structure of the common profile \(F\)

**Statement**: For each fixed \(x\in(0,1)\), prove that the function \(\psi\mapsto F(x,\psi)\) is even and \(\pi\)-periodic, is strictly decreasing on \((0,\pi/2)\), and satisfies
\[
F_x(x,\psi)>0,\qquad F_\psi(x,\psi)<0\qquad\text{for }\psi\in(0,\pi/2).
\]

**Role**: These are exactly the one-dimensional sign/monotonicity facts needed to apply a quarter-shift anti-correlation argument on each \(x\)-circle.

**Approach**: Differentiate the explicit log-expression from Subproblem 1 after substituting \(z=\sqrt{1-x^2}\cos\psi\); the symmetry gives evenness/\(\pi\)-periodicity, and the derivative formulas give the signs.

**Difficulty**: medium

### Subproblem 4: Reduce each \(x\)-slice to a weighted quarter-shift correlation integral

**Statement**: For \(x\in(0,1)\), define
\[
J(x):=\int_0^{2\pi} (\partial_\phi G_A)(q(x,\psi))\,(\partial_\phi G_B)(q(x,\psi))\,w(x,\psi)\,d\psi.
\]
Prove the identity
\[
J(x)=\int_0^{2\pi}\Bigl((1-x^2)\sin^2\psi\,F_x(x,\psi)F_x(x,\psi-\pi/2)
+\frac{x^2\cos^2\psi}{1-x^2}\,F_\psi(x,\psi)F_\psi(x,\psi-\pi/2)\Bigr)\,w(x,\psi)\,d\psi.
\]

**Role**: This removes the mixed \(F_xF_\psi\) terms and isolates the exact one-dimensional expression whose sign must be controlled.

**Approach**: Substitute the formula for \(\partial_\phi\) from Subproblem 2 into both factors, expand, and use the \(\pi/2\)-periodicity of \(w\) together with the \(\pi\)-periodicity of \(F\) to cancel the mixed terms after integration.

**Difficulty**: medium

### Subproblem 5: Prove the slice-wise anti-correlation inequality

**Statement**: With \(F\), \(w\), and \(J(x)\) as in Subproblems 2–4, prove that for every \(x\in(0,1)\),
\[
\int_0^{2\pi}(1-x^2)\sin^2\psi\,F_x(x,\psi)F_x(x,\psi-\pi/2)\,w(x,\psi)\,d\psi
\le
-\int_0^{2\pi}\frac{x^2\cos^2\psi}{1-x^2}\,F_\psi(x,\psi)F_\psi(x,\psi-\pi/2)\,w(x,\psi)\,d\psi,
\]
and that the inequality is strict for \(x\) in a subset of \((0,1)\) of positive measure; equivalently, \(J(x)\le 0\) for all \(x\in(0,1)\) and \(J(x)<0\) on a positive-measure set.

**Role**: This is the core analytic step: it replaces the unavailable global pointwise sign argument by the correct orbitwise negativity statement.

**Approach**: Apply/adapt the paper’s quarter-shift monotonicity lemma on \((0,\pi/2)\) to the profile \(F(x,\cdot)\), using the sign and monotonicity data from Subproblem 3 and the positive \(\pi/2\)-periodic weight \(w(x,\cdot)\).

**Difficulty**: hard

### Subproblem 6: Integrate over \(x\) and conclude Hessian positivity

**Statement**: Prove that
\[
\int_{S^2}(\partial_\phi G_A)(\partial_\phi G_B)\,d(\mu^++\mu^-)
=\int_{-1}^{1}J(x)\,dx<0,
\]
and therefore
\[
\operatorname{Hess}_p\log J_8(v,v)
=-16\pi^2\int_{S^2}(\partial_\phi G_A)(\partial_\phi G_B)\,d(\mu^++\mu^-)>0.
\]

**Role**: This is the final assembly step from the slice estimates back to the original two-dimensional integral and then to the Hessian.

**Approach**: Use \(dA=dx\,d\psi\), Fubini, evenness in \(x\), positivity of the measure, and the strict negativity from Subproblem 5 on a positive-measure set.

**Difficulty**: easy

## Integration Sketch

Subproblem 1 turns the Green-potential sums into explicit rational/logarithmic formulas and records the quarter-turn symmetry of the weight. Subproblem 2 then picks the right coordinates: on each circle \(x=\text{const}\), the \(B\)-potential is just the \(\pi/2\)-shift of the \(A\)-potential, and \(\partial_\phi\) becomes an explicit combination of \(\partial_x\) and \(\partial_\psi\). Subproblem 3 provides the monotonicity and sign information for the common profile \(F(x,\psi)\). Subproblem 4 uses these coordinates to rewrite each slice contribution \(J(x)\) as a weighted quarter-shift correlation integral with the mixed terms eliminated by symmetry. Subproblem 5 proves that each slice contributes nonpositively, with strict negativity for a positive-measure set of \(x\)-values. Finally, Subproblem 6 integrates the slice inequality over \(x\) to obtain
\[
\int_{S^2}(\partial_\phi G_A)(\partial_\phi G_B)\,d(\mu^++\mu^-)<0,
\]
and the given Hessian identity then gives \(\operatorname{Hess}_p\log J_8(v,v)>0\) for the \(T_{2g}\) generator.