## Overall Insight

This is a problem in harmonic analysis and representation theory on the sphere. The Hessian has already been reduced to an \(L^2(\mu^++\mu^-)\) pairing of azimuthal derivatives of Green-function sums, so the remaining issue is purely spectral: determine the sign of that pairing for the deformation generating the real irreducible \(T_{2g}\)-module. The right tool is not a pointwise sign argument—those fail here because some pair interactions are genuinely positive—but the \(C_4\)-symmetry of the cube around the \(z\)-axis. One should decompose the eight vertices into the upper and lower 4-cycles, take the discrete Fourier transform in the ring index \(k\in \mathbb Z/4\), and then combine that with the ordinary Fourier series in \(\phi\) of each single-vertex Green kernel.

The key subtlety is that the weight \(d\mu:=d\mu^++d\mu^-\) is **not** uniform in \(\phi\), so naive orthogonality of ordinary \(\phi\)-Fourier modes is not the correct organizing principle. What *is* orthogonal is the decomposition into \(C_4\)-characters, because \(d\mu\) is invariant under \(\phi\mapsto \phi+\pi/2\). This packages all positive and negative pairwise contributions into a small number of symmetry blocks. The \(T_{2g}\) deformation becomes exactly the height-odd \(m=1\) block, and the original cross term becomes the difference between the \(L^2(\mu)\)-energies of that block and the height-even \(m=0\) block coming from the all-plus sum.

## Subproblem Decomposition

### Subproblem 1: Rewrite the target integral as a difference of two \(L^2\)-energies

**Statement**: Let \(p_{+,k}=(\theta_0,k\pi/2)\) and \(p_{-,k}=(\pi-\theta_0,k\pi/2)\) for \(k=0,1,2,3\), let \(g_{\varepsilon,k}:=\partial_\phi G_{p_{\varepsilon,k}}\), let \(d\mu:=d\mu^++d\mu^-\), and for any coefficient array \(a=(a_{\varepsilon,k})\in \mathbb C^{\{+,-\}\times\{0,1,2,3\}}\) define \(f_a:=\sum_{\varepsilon,k} a_{\varepsilon,k}g_{\varepsilon,k}\) and \(q(a):=\int_{S^2}|f_a|^2\,d\mu\); if \(\mathbf 1\) is the all-ones array and \(\sigma_{T_{2g}}\) is the real sign pattern with upper signs \((+,+,-,-)\) and lower signs \((-,-,+,+)\), corresponding to \(A=\{p_{+,0},p_{+,1},p_{-,2},p_{-,3}\}\), then
\[
\int_{S^2} (\partial_\phi G_A)(\theta,\phi)\,(\partial_\phi G_A)(\theta,\phi+\pi)\,d\mu
=\frac14\bigl(q(\mathbf 1)-q(\sigma_{T_{2g}})\bigr).
\]

**Role**: This replaces the original cross-term sign problem by the cleaner inequality \(q(\sigma_{T_{2g}})>q(\mathbf 1)\).

**Approach**: Use \(1_A=(\mathbf 1+\sigma_{T_{2g}})/2\) and \(1_B=(\mathbf 1-\sigma_{T_{2g}})/2\), with \(B=R_\pi(A)\), so that \(f_{1_A}=(f_{\mathbf 1}+f_{\sigma_{T_{2g}}})/2\) and \(f_{1_B}=(f_{\mathbf 1}-f_{\sigma_{T_{2g}}})/2\).

**Difficulty**: easy

### Subproblem 2: Decompose by \(C_4\)-characters of the quarter-turn symmetry

**Statement**: With \(g_{\varepsilon,k}\) and \(d\mu\) as in Subproblem 1, define for each \(m\in\{0,1,2,3\}\) and \(\eta\in\{+1,-1\}\)
\[
F_{m,\eta}:=\sum_{k=0}^3 i^{-mk}\bigl(g_{+,k}+\eta\,g_{-,k}\bigr).
\]
Then \(F_{m,\eta}(\theta,\phi+\pi/2)=i^m F_{m,\eta}(\theta,\phi)\), and
\[
\int_{S^2} F_{m,\eta}\,\overline{F_{m',\eta'}}\,d\mu=0
\qquad\text{whenever }m\not\equiv m' \pmod 4.
\]

**Role**: This block-diagonalizes the eight-vertex interaction into independent angular character sectors, which is the symmetry reduction that replaces the failed pairwise sign argument.

**Approach**: Apply the quarter-turn \((\theta,\phi)\mapsto(\theta,\phi+\pi/2)\) to the inner product, use \(d\mu\)-invariance, and compare the resulting character factor \(i^{m-m'}\).

**Difficulty**: medium

### Subproblem 3: Identify the all-plus mode and the \(T_{2g}\) mode in the character basis

**Statement**: With \(f_a\) as in Subproblem 1 and \(F_{m,\eta}\) as in Subproblem 2,
\[
f_{\mathbf 1}=F_{0,+1},
\qquad
f_{\sigma_{T_{2g}}}=\frac{1+i}{2}F_{1,-1}+\frac{1-i}{2}F_{3,-1},
\]
and since the \(g_{\varepsilon,k}\) are real-valued, \(F_{3,-1}=\overline{F_{1,-1}}\); therefore
\[
q(\mathbf 1)=\|F_{0,+1}\|_{L^2(\mu)}^2,
\qquad
q(\sigma_{T_{2g}})=\|F_{1,-1}\|_{L^2(\mu)}^2.
\]
Hence the desired inequality is equivalent to
\[
\|F_{1,-1}\|_{L^2(\mu)}^2>\|F_{0,+1}\|_{L^2(\mu)}^2.
\]

**Role**: This isolates the single comparison that matters: the height-odd \(m=1\) block against the height-even \(m=0\) block.

**Approach**: Compute the discrete Fourier transform of the sign vectors \((1,1,1,1)\) and \((1,1,-1,-1)\) on the 4-cycle, then use Subproblem 2.

**Difficulty**: easy

### Subproblem 4: Compute the circle-Fourier expansions of the single-vertex Green derivatives

**Statement**: For each fixed \(\theta\in(0,\pi)\), there exist unique \(\rho_+(\theta),\rho_-(\theta)\in(0,1)\) and \(C_+(\theta),C_-(\theta)>0\) such that
\[
1-\cos\theta\cos\theta_0-\sin\theta\sin\theta_0\cos\psi
= C_+(\theta)\bigl(1-2\rho_+(\theta)\cos\psi+\rho_+(\theta)^2\bigr),
\]
\[
1+\cos\theta\cos\theta_0-\sin\theta\sin\theta_0\cos\psi
= C_-(\theta)\bigl(1-2\rho_-(\theta)\cos\psi+\rho_-(\theta)^2\bigr),
\]
and consequently
\[
g_{+,0}(\theta,\phi)=\frac{1}{2\pi}\sum_{n\ge1}\rho_+(\theta)^n\sin(n\phi),
\qquad
g_{-,0}(\theta,\phi)=\frac{1}{2\pi}\sum_{n\ge1}\rho_-(\theta)^n\sin(n\phi).
\]
After summing over \(k\) with the character weights from Subproblem 2, \(F_{0,+1}\) has only circle frequencies \(n\equiv0\pmod 4\), with coefficient \(\frac{2}{\pi}\bigl(\rho_+(\theta)^n+\rho_-(\theta)^n\bigr)\), while \(F_{1,-1}\) has only frequencies \(n\equiv1,3\pmod 4\), and each such frequency has coefficient equal to a fixed nonzero phase times \(\frac{2}{\pi}\bigl(\rho_+(\theta)^n-\rho_-(\theta)^n\bigr)\).

**Role**: This turns the two relevant symmetry modes into explicit, computable geometric-series kernels.

**Approach**: Rewrite each logarithmic factor in the form \(1-2r\cos\psi+r^2\), use \(\log(1-2r\cos\psi+r^2)=-2\sum_{n\ge1}r^n\cos(n\psi)/n\), and differentiate in \(\phi\).

**Difficulty**: medium

### Subproblem 5: Prove the \(m=1\), height-odd block has larger \(L^2(\mu)\)-energy than the \(m=0\), height-even block

**Statement**: Let \(F_{0,+1}\) and \(F_{1,-1}\) be the functions from Subproblems 2–4; then
\[
\|F_{1,-1}\|_{L^2(\mu)}^2>\|F_{0,+1}\|_{L^2(\mu)}^2.
\]

**Role**: This is the decisive inequality; together with Subproblems 1–3 it yields the strict negativity of the original integral.

**Approach**: Insert the explicit geometric-series formulas from Subproblem 4, use only \(C_4\)-character orthogonality (not naive \(\phi\)-Fourier orthogonality), reduce both norms to explicit positive kernels depending on \(\rho_\pm(\theta)\), and then compare those kernels—either term-by-term or after summing the series to closed forms; using the symmetry exchanging upper and lower rings lets one reduce to a half-sphere where the comparison is monotone.

**Difficulty**: hard

## Integration Sketch

Assuming the subproblems are solved, the proof is straightforward to assemble. Subproblem 1 rewrites the target integral as \(\frac14(q(\mathbf 1)-q(\sigma_{T_{2g}}))\), so negativity is equivalent to \(q(\sigma_{T_{2g}})>q(\mathbf 1)\). Subproblem 2 gives the orthogonal \(C_4\)-character decomposition of the eight-vertex interaction, and Subproblem 3 identifies the two relevant pieces exactly: the all-plus reference is \(F_{0,+1}\), while the \(T_{2g}\) deformation is the height-odd \(m=1\) mode \(F_{1,-1}\). Subproblem 4 computes these modes explicitly by Fourier expansion of the single-vertex Green kernels, reducing them to concrete geometric-series expressions in \(\rho_\pm(\theta)\). Subproblem 5 then proves \(\|F_{1,-1}\|_{L^2(\mu)}^2>\|F_{0,+1}\|_{L^2(\mu)}^2\). Therefore \(q(\sigma_{T_{2g}})>q(\mathbf 1)\), so the original integral is strictly negative. Since the chosen deformation generates the irreducible real representation \(T_{2g}\) and the Hessian is \(G\)-invariant, this gives positive definiteness of the Hessian on all of \(T_{2g}\).