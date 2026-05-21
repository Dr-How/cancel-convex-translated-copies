## Overall Insight

This is a problem in analysis and potential theory on the sphere, specifically concerning the definiteness of a quadratic form (the Hessian of a functional) evaluated on a symmetric subspace $T_{2g}$. The problem demands proving that a certain cross-integral involving the derivatives of Green's functions, $\int (\partial_\phi G_A)(\partial_\phi G_B) d\mu$, is strictly negative. 

The key insight is to exploit the rotational symmetry relating the point sets $B = R_\pi(A)$. This shifts the problem into the Fourier domain in $\phi$: we can decompose the derivative $\partial_\phi G_A$ into its even and odd parity components with respect to the $\pi$-shift. This exactly diagonalizes the cross-integral into a difference of two positive-definite quantities, $F_{even}^2 - F_{odd}^2$, bypassing the intractable sum of 16 individual cross-point interactions. Because the Green's function has logarithmic singularities, its Fourier coefficients decay exponentially with the mode number $m$. The odd component is supported on modes $m \equiv 1, 3 \pmod 4$ (starting at $m=1$), while the even component is supported on modes $m \equiv 0 \pmod 4$ (starting at $m=4$). The exponential decay ensures that the lowest active mode $m=1$ dominates the entire series, allowing us to rigorously prove that the negative odd-parity term globally outweighs the positive even-parity term.

## Subproblem Decomposition

### Subproblem 1: Parity Decomposition of the Hessian Form

**Statement**: Let $F_{even}(\theta, \phi) = \frac{1}{4\pi} \partial_\phi u(\theta, \phi)$ and $F_{odd}(\theta, \phi) = \frac{1}{2} \partial_\phi (G_A - G_B)(\theta, \phi)$. Prove that the cross-integral takes the exact form $\int_{S^2} (\partial_\phi G_A)(\theta, \phi) (\partial_\phi G_A)(\theta, \phi+\pi) d\mu^\pm = \int_{S^2} \left( F_{even}^2 - F_{odd}^2 \right) d\mu^\pm$.

**Role**: Transforms the cross-integral into a clean difference of two positive-definite integrals, isolating the even and odd $\phi$-parity components. This shifts the burden to proving that the odd parity modes strictly dominate the even parity modes.

**Approach**: Write $\partial_\phi G_A = F_{even} + F_{odd}$ with respect to the parity shift $\phi \mapsto \phi+\pi$. Use the geometric relationship $G_B(\theta, \phi) = G_A(\theta, \phi+\pi)$ and the potential identity $u = 2\pi(G_A + G_B)$ to identify $F_{even}$ and $F_{odd}$. Expand the product $(\partial_\phi G_A)(\phi) (\partial_\phi G_A)(\phi+\pi) = F_{even}^2 - F_{odd}^2$. Conclude by observing that the cross-term $\int F_{even} F_{odd} d\mu^\pm$ integrates to zero because the measure $\mu^\pm$ depends only on $u$, making it invariant under $\phi \mapsto \phi+\pi$.

**Difficulty**: Easy

### Subproblem 2: Fourier Expansion of the Green's Functions

**Statement**: Prove that the Fourier decomposition of $G_A(\theta, \phi)$ in $\phi$ yields $F_{even}(\theta, \phi) = \sum_{j=1}^\infty c_{4j}(\theta) e^{i 4j \phi}$ and $F_{odd}(\theta, \phi) = \sum_{k=0}^\infty c_{2k+1}(\theta) e^{i (2k+1) \phi}$, where the exact coefficients are given by $c_{4j} = \frac{2i}{\pi} (\alpha^{4j} + \bar{\alpha}^{4j})$ and $c_{2k+1} = \frac{1}{\pi}(1 - i(-1)^k)(\alpha^{2k+1} - \bar{\alpha}^{2k+1})$. Here, $\bar{\alpha}(\theta) = \alpha(\pi-\theta)$, and $\alpha(\theta) = \frac{1 - \cos\theta\cos\theta_0 - |\cos\theta-\cos\theta_0|}{\sin\theta\sin\theta_0}$.

**Role**: Provides the exact closed-form Fourier coefficients required to strictly compute and bound the integrals of $F_{even}^2$ and $F_{odd}^2$ on each constant-$\theta$ slice.

**Approach**: Expand the individual Green's function $G_1(\theta, \phi) = -\frac{1}{2\pi} \log(1 - (\cos\theta\cos\theta_0 + \sin\theta\sin\theta_0\cos\phi))$ using the standard Fourier series for $-\log(A - B\cos\phi)$. Simplify the resulting geometric parameter $\alpha$. Then, sum the translated series over the four points of $A$ located at $(\theta_0, 0), (\theta_0, \pi/2), (\pi-\theta_0, \pi), (\pi-\theta_0, 3\pi/2)$ to cancel the missing modes and isolate the surviving $c_m$ expressions.

**Difficulty**: Medium

### Subproblem 3: Dominance of the Odd Parity Modes

**Statement**: Prove that $\int_{S^2} F_{even}^2 d\mu^\pm < \int_{S^2} F_{odd}^2 d\mu^\pm$ globally on the sphere by demonstrating that $\int_0^\pi \left( \sum_{k=0}^\infty |c_{2k+1}(\theta)|^2 - \sum_{j=1}^\infty |c_{4j}(\theta)|^2 \right) \sin\theta d\theta > 0$, and that this strict positivity holds when integrated against the full symmetric measure $d\mu^\pm(\theta, \phi)$.

**Role**: Completes the proof that the Hessian is positive definite on $T_{2g}$ by showing that the negative terms (the $m=1, 3, 5\dots$ modes) strictly outweigh the positive terms (the $m=4, 8, 12\dots$ modes).

**Approach**: Use Parseval's identity on the unweighted $\phi$-integrals to express them as $\sum |c_{4j}|^2$ and $\sum |c_{2k+1}|^2$. Sum these explicit geometric series to get closed-form rational functions of $\alpha(\theta)$ and $\bar{\alpha}(\theta)$. Show that near the singularities $\theta \to \theta_0$ (where $\alpha \to 1$ and $\bar{\alpha} \ll 1$), the odd mode sum $\sim \frac{2\alpha^2}{1-\alpha^4}$ dominates the even mode sum $\sim \frac{4\alpha^8}{1-\alpha^8}$ via the strictly positive algebraic difference $\frac{2\alpha^2(1+\alpha^4-2\alpha^6)}{1-\alpha^8}$. Integrate over $\theta$ to show the strong singular peaks overcome the small intervals near the equator. Finally, incorporate bounds on the oscillation of the density $\mu^\pm$ to preserve the strict inequality.

**Difficulty**: Hard

## Integration Sketch

The proof flows by translating a geometric property into a spectral one. Subproblem 1 proves that the Hessian criterion is exactly equivalent to whether the squared $L^2$-norm of the odd $\phi$-modes of the derivative strictly exceeds that of the even $\phi$-modes. Subproblem 2 provides the exact analytical engine to test this, establishing the exponential decay parameter $\alpha(\theta)$ and proving the even sum begins at $m=4$ while the odd sum begins at $m=1$. Because $\alpha < 1$ almost everywhere, the $m=1$ mode fundamentally dwarfs the $m=4$ mode. Subproblem 3 synthesizes these analytical sums, confirming that the pointwise dominance of the odd geometric series near the charges easily integrates to a global strict inequality against the bounded density $\mu^\pm$. Together, these establish the cross-integral is strictly negative, proving positive definiteness of the Hessian on $T_{2g}$.