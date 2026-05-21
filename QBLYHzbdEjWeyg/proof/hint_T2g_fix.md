# Hint: Fix the T₂g Section of problem.tex

## The Error

Lines 820–829 of problem.tex claim (via Schur's lemma) that

$$\int \partial_\phi G_A \cdot \partial_\phi G_B \, d(\mu^++\mu^-) = \int \partial_\phi G_{A'} \cdot \partial_\phi G_{B'} \, d(\mu^++\mu^-),$$

where $A = \{\varepsilon_1\varepsilon_3=+1\}$ and $A' = \{\varepsilon_1\varepsilon_2=+1\}$ (standard cube). This is **wrong**.

**Why it fails.** The map $\sigma:(X,Y,Z)\mapsto(X,Z,Y)$ is a cube symmetry
satisfying $\sigma_*(\partial_\phi) = \partial_\chi$ (rotation about $Y$), NOT
$\partial_\phi$. Hence the correct change of variables gives

$$\int \partial_\phi G_A \cdot \partial_\phi G_B \, d\mu = \int \partial_\chi G_{A'} \cdot \partial_\chi G_{B'} \, d\mu,$$

not an equality with $\partial_\phi G_{A'}\cdot\partial_\phi G_{B'}$. The three T₂g generators use **three different** Killing fields:
- $e_{xz}$: partition $\{\varepsilon_1\varepsilon_3=\pm1\}$ with Killing field $\partial_\phi$ (rotation about $Z$)
- $e_{xy}$: partition $\{\varepsilon_1\varepsilon_2=\pm1\}$ with Killing field $\partial_\chi$ (rotation about $Y$)
- $e_{yz}$: partition $\{\varepsilon_2\varepsilon_3=\pm1\}$ with Killing field $\partial_\psi$ (rotation about $X$)

Lines 831–888 prove $\int\partial_\phi G_{A'}\cdot\partial_\phi G_{B'}\,d\mu < 0$, but this is a **different** integral (not the T₂g Hessian).

---

## The Correct Proof

### Setup: 45°-tilted cube orientation

Use the cube orientation from the decomposition section (lines 579–633 of problem.tex), with vertices at angles $(\theta_0,0),(\theta_0,\pi/2),\ldots$ where $\theta_0 = \arccos(1/\sqrt{3})$. The T₂g generator is:

$$A = \{p_1,p_2,p_7,p_8\} = \{(\theta_0,0),\,(\theta_0,\tfrac\pi2),\,(\pi-\theta_0,\pi),\,(\pi-\theta_0,\tfrac{3\pi}2)\},$$

$$B = \{p_3,p_4,p_5,p_6\} = R_{-\pi/2}(A),$$

where $R_{-\pi/2}$ is the rotation $\phi\mapsto\phi-\pi/2$ (i.e.\ $B$ is obtained from $A$ by a $-\pi/2$ rotation about the $Z$-axis).

**Key formula.** In Cartesian coordinates, the $A$-vertices lie at $(b,0,a),(0,b,a),(-b,0,-a),(0,-b,-a)$ (all in the $XZ$ and $YZ$ planes), so $G_A$ depends only on $(X,Z)$:
$$G_A(X,Y,Z) = -\tfrac{1}{4\pi}\log P_A(X,Z) + C_A, \qquad P_A(X,Z) = \bigl((Z-a)^2+b^2Y^2\bigr)\bigl((Z+a)^2+b^2Y^2\bigr).$$
(Here the cube has the **tilted** orientation; this $P_A$ is the same as in the prior subproblems.)

Because $G_B(q) = G_A(R_{-\pi/2}(q))$ (i.e.\ the $B$-vertices are the $R_{-\pi/2}$-images of the $A$-vertices), and $R_{-\pi/2}$ commutes with $\partial_\phi$ (both involve rotations about $Z$), we get:

$$\partial_\phi G_B(q) = \partial_\phi G_A\!\big(R_{-\pi/2}(q)\big).$$

### The $(x,\psi)$ parametrization

Write $q = q(x,\psi)$ with $x\in(-1,1)$, $\psi\in[0,2\pi)$, via
$$X = x,\quad Y = r\sin\psi,\quad Z = r\cos\psi,\quad r = \sqrt{1-x^2}.$$

Set $h(x,\psi) := (\partial_\phi G_A)(q(x,\psi))$. The explicit formula (established in subproblem 1 of the v2 series, file `sol_v2_1_formulas.tex`) is
$$h(x,\psi) = -\frac{x\,r\sin\psi\,(3+2r^2\cos^2\psi - x^2)}{9\pi\,P_A(x,\,r\cos\psi)}.$$

Since $R_{-\pi/2}$ sends $q(x,\psi)$ to $q(x,\psi-\pi/2)$:
$$\partial_\phi G_B(q(x,\psi)) = h(x,\psi-\tfrac\pi2).$$

Therefore, the T₂g integral becomes
$$\int_{S^2} \partial_\phi G_A \cdot \partial_\phi G_B\,d(\mu^++\mu^-)
= \int_{-1}^{1} dx \int_0^{2\pi} h(x,\psi)\,h(x,\psi-\tfrac\pi2)\,w(x,\psi)\,d\psi,$$
which has the form of $K_1$ from the Lemma already proved in problem.tex.

### Applying the Lemma

The Lemma (lines 678–740 of problem.tex) states: if $f(\theta,\phi)$ is odd in $\phi$, negative on $(0,\pi)$, and strictly monotone increasing in $\phi$ on $(0,\pi)$, with $\rho$ being positive and satisfying $\rho(\theta,\phi+\pi/2)=\rho(\theta,\phi)$ and $\rho(\pi-\theta,\phi)=\rho(\theta,\phi)$, then
$$K_1 = \int_{S^2} f(\theta,\phi)\,f(\theta,\phi-\tfrac\pi2)\,\rho\,dA < 0.$$

For $f = h(x,\psi)$ (viewing $x=\cos\theta$) and $\rho = w(x,\psi)$:

1. **Oddness** $h(x,-\psi)=-h(x,\psi)$: immediate from the formula ($\sin(-\psi)=-\sin\psi$, denominator even in $\psi$). [Part A of sign lemma, proved in `sol_v2_5_sign.tex`]

2. **Sign** $h(x,\psi)<0$ for $x\in(0,1)$, $\psi\in(0,\pi)$: the numerator is $x\cdot r\sin\psi\cdot(\text{positive})$ with $x>0$, $\sin\psi>0$, and the denominator $P_A>0$ away from the $A$-vertices. [Part B, proved in `sol_v2_5_sign.tex`; indeed $h<0$ for all $\psi\in(0,\pi)$]

   *For $x\in(-1,0)$: by the reflection symmetry $h(-x,\psi)=-h(x,\psi)$ and evenness of the weight in $x$, the contribution from $x<0$ mirrors the $x>0$ contribution (factor of 2 in the integral, same sign).*

3. **Monotonicity** of $h$ in $\psi$ on $(0,\pi)$ for fixed $x\in(0,1)$: proved in `sol_v2_3_monotonicity.tex`.

4. **Weight properties** $w(x,\psi+\pi/2)=w(x,\psi)$ and $w(-x,\psi)=w(x,\psi)$: the full weight $(e^u+e^{-u})/(I^++I^-)$ inherits these symmetries from the $C_4$ symmetry of the cube about the $Z$-axis and the equatorial symmetry. These were established in prior subproblems.

By the Lemma, the integral is $< 0$, completing the T₂g proof.

---

## What to Write

Replace lines 780–888 of problem.tex with a clean section that:

1. States that the cube is oriented in the 45°-tilted position (vertices at $(\theta_0,k\pi/2)$ and $(\pi-\theta_0,k\pi/2+\pi)$, matching the decomposition section), with T₂g generator $A=\{1,2,7,8\}$ and $B=\{3,4,5,6\}$.

2. Establishes $G_B(q) = G_A(R_{-\pi/2}(q))$ (since $B = R_{-\pi/2}(A)$) and hence $\partial_\phi G_B(q) = (\partial_\phi G_A)(R_{-\pi/2}(q))$.

3. Introduces the $(x,\psi)$ parametrization and writes $h(x,\psi) = (\partial_\phi G_A)(q(x,\psi))$ with its explicit formula.

4. Writes the T₂g integral as $\int h(x,\psi)\,h(x,\psi-\pi/2)\,w\,d\psi\,dx$ and cites the Lemma (already proved).

5. Verifies the Lemma hypotheses (odd, sign, monotone, weight symmetry) by citing the relevant proved results.

The resulting proof should be about 1–2 pages of LaTeX, largely self-contained, and use no new ideas beyond those already in the paper.

---

## Summary of Changes to problem.tex

- **Remove** lines 820–829 (wrong Schur's lemma group averaging).
- **Remove** lines 831–888 (computation of $\partial_\phi G_{A'}\cdot\partial_\phi G_{B'}$, which addresses the wrong quantity).
- **Replace** the entire T₂g subsection (lines 780–888) with the clean proof sketched above, in the tilted-cube orientation.
- **Keep** the Lemma (lines 678–740) and all preceding content.
