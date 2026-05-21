## Overall Insight

This is an analysis/variational problem on \(S^2\) with a heavy symmetry and representation-theoretic component. The Hessian formula is already reduced to a weighted integral of Green-function derivatives, so the real issue is to prove the sign of that integral for the specific \(T_{2g}\) deformation. A direct pointwise sign argument on \((\partial_\phi G_A)(\partial_\phi G_B)\) is the wrong level of granularity here, because some individual cross-pairs are genuinely positive; likewise, a pair-by-pair matrix estimate obscures the cancellation.

The natural attack is to rotate the azimuth by \(\pi/4\), so the cube becomes the standard \((\pm1,\pm1,\pm1)/\sqrt3\) cube and the \(T_{2g}\) sign pattern becomes the checkerboard condition \(xz\gtrless 0\). Then write \(F_A=\partial_\phi G_A\), \(F_B=F_A\circ R_\pi\), and decompose into \(C:=F_A+F_B\) and \(D:=F_A-F_B\). Using the quarter-turn invariance of the full cube and of the measures \(\mu^\pm\), the original integral can be rewritten on one fundamental sector as the integral of a single “defect”
\[
-\Xi,\qquad \Xi=\frac12 D^2+\frac12(D\circ R_{\pi/2})^2-C^2.
\]
So the problem becomes an explicit algebraic inequality for rational functions in \(x,y,z\). This is the concrete, real-variable version of the Fourier-sector heuristic: instead of tracking many mixed terms, one compares the \(4\)-fold symmetric part against the two quarter-turn-related \(T_{2g}\) companions all at once.

## Subproblem Decomposition

### Subproblem 1: Standardize the cube and write the \(T_{2g}\) mode explicitly

**Statement**: Let \(\psi=\phi-\pi/4\), let \(x=\sin\theta\cos\psi\), \(y=\sin\theta\sin\psi\), \(z=\cos\theta\), and let \(q_{\varepsilon_1,\varepsilon_2,\varepsilon_3}=(\varepsilon_1,\varepsilon_2,\varepsilon_3)/\sqrt3\in S^2\) for \(\varepsilon_j\in\{\pm1\}\); prove that the eight cube vertices are exactly the \(q_{\varepsilon_1,\varepsilon_2,\varepsilon_3}\), that \(A=\{q_\varepsilon:\varepsilon_1\varepsilon_3=1\}\) and \(B=\{q_\varepsilon:\varepsilon_1\varepsilon_3=-1\}\), and that, for \(G_q(z)=-(1/(2\pi))\log\sin(d(z,q)/2)\),
\[
F_A(\theta,\psi):=\partial_\psi \sum_{q\in A}G_q(\theta,\psi)
=\frac{1}{4\pi\sqrt3}\sum_{\substack{\varepsilon_1,\varepsilon_2,\varepsilon_3\in\{\pm1\}\\ \varepsilon_1\varepsilon_3=1}}
\frac{\varepsilon_2 x-\varepsilon_1 y}{1-(\varepsilon_1 x+\varepsilon_2 y+\varepsilon_3 z)/\sqrt3},
\]
so \(F_B(\theta,\psi)=F_A(\theta,\psi+\pi)\), and therefore
\[
C(\theta,\psi):=F_A(\theta,\psi)+F_A(\theta,\psi+\pi)
=\frac{1}{4\pi\sqrt3}\sum_{\varepsilon_1,\varepsilon_2,\varepsilon_3=\pm1}
\frac{\varepsilon_2 x-\varepsilon_1 y}{1-(\varepsilon_1 x+\varepsilon_2 y+\varepsilon_3 z)/\sqrt3},
\]
\[
D(\theta,\psi):=F_A(\theta,\psi)-F_A(\theta,\psi+\pi)
=\frac{1}{4\pi\sqrt3}\sum_{\varepsilon_1,\varepsilon_2,\varepsilon_3=\pm1}
\varepsilon_1\varepsilon_3\,
\frac{\varepsilon_2 x-\varepsilon_1 y}{1-(\varepsilon_1 x+\varepsilon_2 y+\varepsilon_3 z)/\sqrt3}.
\]

**Role**: This puts the geometry into the standard cube coordinates and converts the abstract Green-function sum into explicit rational functions \(F_A\), \(C\), and \(D\), which are the inputs for the later sign computation.

**Approach**: Rotate the azimuth by \(\pi/4\), identify the cube with \((\pm1,\pm1,\pm1)/\sqrt3\), use \(\sin^2(d(z,q)/2)=\frac12(1-z\cdot q)\), and differentiate \(G_q=-(1/4\pi)\log(1-z\cdot q)+\text{const}\) with respect to \(\psi\).

**Difficulty**: medium

### Subproblem 2: Rewrite the target integral as a quarter-turn defect

**Statement**: Let \(d(\mu^++\mu^-)=\rho(\theta,\psi)\sin\theta\,d\theta\,d\psi\), where \(\mu^\pm\) are the probability measures with densities \(e^{\pm u}/I^\pm\) and \(u=2\pi\sum_{i=1}^8 G_i\); with \(F_A,C,D\) as in Subproblem 1 define
\[
\Xi(\theta,\psi):=\frac12 D(\theta,\psi)^2+\frac12 D\!\left(\theta,\psi+\frac{\pi}{2}\right)^2-C(\theta,\psi)^2.
\]
Prove that \(\rho(\theta,\psi+\pi/2)=\rho(\theta,\psi)\), that \(C(\theta,\psi+\pi/2)=C(\theta,\psi)\), and that
\[
I:=\int_{S^2}F_A(\theta,\psi)F_A(\theta,\psi+\pi)\,d(\mu^++\mu^-)
=-\int_0^\pi\int_0^{\pi/2}\Xi(\theta,\psi)\,\rho(\theta,\psi)\sin\theta\,d\psi\,d\theta.
\]

**Role**: This is the key reduction: it replaces the original cross-term by a single defect \(\Xi\) on one fundamental sector, where the sign is much more tractable.

**Approach**: Use the \(\pi/2\)-invariance of the full cube and of \(u\), hence of \(\rho\); partition the \(\psi\)-circle into four quarter-turn intervals; then rewrite \(F_AF_B\) via \(F_B=F_A(\cdot+\pi)\) and the identities \(F_AF_B=\frac14(C^2-D^2)\) and \(C(\psi+\pi/2)=C(\psi)\).

**Difficulty**: medium

### Subproblem 3: Prove the defect is nonnegative and nontrivial

**Statement**: With \(F_A,C,D,\Xi\) as in Subproblems 1–2, prove that \(\Xi\) extends to a locally integrable function on the fundamental sector \((0,\pi)\times(0,\pi/2)\), satisfies
\[
\Xi(\theta,\psi)\ge 0
\]
for every \((\theta,\psi)\in(0,\pi)\times(0,\pi/2)\) away from the two vertex singularities \((\theta_0,\pi/4)\) and \((\pi-\theta_0,\pi/4)\), and is strictly positive on a subset of positive \((\theta,\psi)\)-measure.

**Role**: This is the decisive sign computation. Once \(\Xi\ge 0\) and not identically zero, the integral in Subproblem 2 is automatically negative.

**Approach**: Substitute the explicit rational formulas from Subproblem 1 into \(\Xi\), clear denominators, and simplify in the region \(x=\sin\theta\cos\psi>0\), \(y=\sin\theta\sin\psi>0\), \(x^2+y^2+z^2=1\). The goal is to make the cancellation of the singular leading terms explicit and factor the remaining numerator into manifestly nonnegative pieces; using a CAS to discover the factorization is fine, but the written proof should record the exact algebraic identity.

**Difficulty**: hard

### Subproblem 4: Convert the defect inequality into the target sign \(I<0\)

**Statement**: Let \(\rho>0\) almost everywhere and suppose
\[
I=-\int_0^\pi\int_0^{\pi/2}\Xi(\theta,\psi)\rho(\theta,\psi)\sin\theta\,d\psi\,d\theta,
\]
where \(\Xi\) is locally integrable, nonnegative almost everywhere, and positive on a set of positive measure. Prove that \(I<0\).

**Role**: This turns the local inequality from Subproblem 3 into the exact integral sign required by the Hessian formula.

**Approach**: View \(\rho(\theta,\psi)\sin\theta\,d\psi\,d\theta\) as a positive measure on the fundamental sector and integrate the nonpositive function \(-\Xi\), which is strictly negative on a set of positive measure.

**Difficulty**: easy

### Subproblem 5: Lift positivity from one generator to all of \(T_{2g}\)

**Statement**: Let \(Q\) be the quadratic form \(Q(w,w)=\operatorname{Hess}_p\log J_8(w,w)\) on
\[
V=\left(\bigoplus_{i=1}^8 T_{p_i}S^2\right)\!/SO(3),
\]
let \(T_{2g}\subset V\) be the irreducible \(3\)-dimensional \(G\)-subrepresentation generated by the deformation \(v_i=+\partial_\phi/\sin\theta|_{p_i}\) for \(i\in A\) and \(v_i=-\partial_\phi/\sin\theta|_{p_i}\) for \(i\in B\), and assume \(Q(v,v)=-16\pi^2 I>0\) for one nonzero \(v\in T_{2g}\). Prove that \(Q\) is positive definite on all of \(T_{2g}\).

**Role**: This upgrades the sign computation for a single convenient generator to the actual statement needed in the paper: positivity of the Hessian on the whole irreducible summand.

**Approach**: Choose a \(G\)-invariant inner product on \(T_{2g}\), represent \(Q\) by a self-adjoint \(G\)-equivariant endomorphism via polarization, and apply Schur’s lemma for irreducible real representations to conclude the endomorphism is a scalar multiple of the identity.

**Difficulty**: easy

## Integration Sketch

Subproblem 1 rotates the azimuth by \(\pi/4\), identifies the cube with the standard \((\pm1,\pm1,\pm1)/\sqrt3\) model, and gives explicit formulas for \(F_A\), hence for the symmetric part \(C=F_A+F_B\) and the \(T_{2g}\) part \(D=F_A-F_B\). Subproblem 2 uses the quarter-turn symmetry of the full cube and of the measures \(\mu^\pm\) to rewrite the desired integral as
\[
I=-\int \Xi\,d(\mu^++\mu^-)
\]
over one fundamental sector, where \(\Xi=\frac12D^2+\frac12(D\circ R_{\pi/2})^2-C^2\). Subproblem 3 is the hard algebraic step: it proves \(\Xi\ge 0\) everywhere in that sector and \(\Xi>0\) on a set of positive measure, with the singular terms cancelling so that \(\Xi\) is integrable. Subproblem 4 then gives \(I<0\). Finally, the Hessian identity \(Q(v,v)=-16\pi^2 I\) shows positivity on the chosen nonzero generator \(v\in T_{2g}\), and Subproblem 5 upgrades that by \(G\)-invariance and irreducibility to positive definiteness on all of \(T_{2g}\).