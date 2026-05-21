# Bug Report: sol_v2_2_parameterize.tex

**Verdict:** ISSUES_FOUND
**Verifier run:** standard (single run, verify_sol_v2_2_parameterize.txt)
**Total issues:** 7 (2 critical justification gaps from verifier, 5 additional gaps from adversarial inspection)

---

## Verifier-flagged issues

### Bug V1 — Part (ii): Jordan decomposition argument is incomplete
**Location:** "Therefore the measures μ± canonically associated to u are also Rx-invariant. (If one views μ± as the Jordan parts of a signed measure determined by u, this follows from uniqueness of the Jordan decomposition.)"

**Type:** Critical justification gap

The argument is conditional ("If one views…"), so the required premise is never established. Even accepting the Jordan decomposition framing, the proof never shows that the pushforward (Rx)_*(μ+ − μ−) is another Jordan decomposition of the same signed measure. The uniqueness of the Jordan decomposition yields invariance only if one first proves that (Rx)_* maps the measure to itself; that is exactly what needs to be shown and is not shown.

---

### Bug V2 — Part (ii): Radon-Nikodym derivative invariance is asserted, not proved
**Location:** "Since Rx is a rotation, it preserves the round area measure dA as well. Consequently the density W = d(μ+ + μ−)/dA is Rx-invariant."

**Type:** Critical justification gap

The step from "μ± are Rx-invariant and dA is Rx-invariant" to "the Radon-Nikodym density W ∘ Rx = W" is not justified. The correct argument requires the change-of-variables formula for Radon-Nikodym derivatives under a measure-preserving map: if (Rx)_*ν = ν and (Rx)_*λ = λ then (dν/dλ) ∘ Rx = dν/dλ a.e. Neither the statement of this fact nor a proof is given. As written, one can only conclude W ∘ Rx = W a.e., not pointwise; but the proof uses pointwise equality at q(x,ψ) in the final chain.

---

## Adversarially identified additional issues

### Bug A1 — Part (i): The identity G_B(q) = G_A(Rx^{−1}(q)) is asserted without proof
**Location:** "Now, because B = Rx(A), the corresponding Green functions satisfy G_B(q) = G_A(Rx^{−1}(q))."

**Type:** Justification gap

The proof does not derive this identity from the definition of the Green functions. B = Rx(A) means the singularities of G_B are at the image Rx(A). For the identity G_B = G_A ∘ Rx^{−1} to hold, one needs that the Green function is defined purely in terms of the geometry relative to the singularity set and the ambient sphere, and that the sphere is Rx-invariant. This is plausible but is a non-trivial step that requires citing (or proving) that the Green function transforms covariantly under isometries of S². The solution states it as obvious without any supporting argument.

---

### Bug A2 — Part (ii): Cube invariance under Rx is asserted without verification
**Location:** "The full cube configuration is invariant under the quarter-turn Rx."

**Type:** Justification gap

The proof does not verify that Rx maps the 8-vertex cube {(±1,±1,±1)/√3} to itself (as a set). This is a checkable arithmetic claim that should be proved, not asserted. In particular, one must verify that Rx permutes the set A and permutes the set B. "Clearly" is used implicitly here (the word "invariant" is introduced without computation), and the verifier's grading standard flags this.

---

### Bug A3 — Part (iii): Cross product computation is incomplete — j and k components are not derived
**Location:** "Computing the determinant gives (x sin²ψ + x cos²ψ, r sinψ, r cosψ)."

**Type:** Exposition/rigor gap

The proof shows the i-component cofactor implicitly (via the simplification x sin²ψ + x cos²ψ = x) but writes down the j- and k-components without any intermediate calculation. The j-component from the 3×3 determinant is −[(1)(−r sinψ) − (−x cosψ/r)(0)] = r sinψ and the k-component is (1)(r cosψ) − (−x sinψ/r)(0) = r cosψ. While both are correct, neither is derived in the text; the reader is expected to trust a "Computing the determinant gives" jump. Under the standard that "it follows" is not an acceptable justification, this is a gap.

---

### Bug A4 — Part (iv): The formula ∂_φ = −Y ∂_X + X ∂_Y is stated without derivation
**Location:** "The vector field corresponding to ∂_φ on S² is ∂_φ = −Y ∂_X + X ∂_Y."

**Type:** Justification gap

The proof imports this Cartesian representation of ∂_φ without derivation. From the spherical convention used (x = sinθ cosφ, y = sinθ sinφ, z = cosθ), one has ∂_φ(x,y,z) = (−sinθ sinφ, sinθ cosφ, 0) = (−y, x, 0) as a tangent vector, which corresponds to −Y ∂_X + X ∂_Y. However, the step from the spherical definition of φ to this Cartesian formula is not written out in the solution. This is an unjustified import of a formula; a skeptical reader has no proof within the document.

---

### Bug A5 — Part (iv): The chain-rule step from tangent-vector equality to operator equality is implicit
**Location:** "Thus, as an operator on functions of (x,ψ), ∂_φ = −r sinψ ∂_x + (x cosψ/r) ∂_ψ."

**Type:** Rigor gap

The proof shows that the tangent vector of ∂_φ at q(x,ψ) equals the linear combination −r sinψ · (∂_x q) + (x cosψ/r) · (∂_ψ q). The conclusion that ∂_φ f = −r sinψ ∂_x f + (x cosψ/r) ∂_ψ f for any smooth f requires the chain rule: if V = α ∂_x q + β ∂_ψ q as a tangent vector to S², then V(f ∘ q) = α ∂_x(f ∘ q) + β ∂_ψ(f ∘ q) as functions of (x,ψ). The solution uses the phrase "as an operator on functions of (x,ψ)" but does not explicitly invoke or cite the chain rule that justifies the step. This is a minor but real rigor gap given the adversarial standard.

---

## Summary table

| ID  | Part  | Type                       | Severity  |
|-----|-------|----------------------------|-----------|
| V1  | (ii)  | Jordan decomp. incomplete  | Critical  |
| V2  | (ii)  | Radon-Nikodym gap          | Critical  |
| A1  | (i)   | G_B = G_A ∘ Rx^{-1} unproved | Significant |
| A2  | (ii)  | Cube Rx-invariance unverified | Significant |
| A3  | (iii) | Cross product j,k not derived | Minor     |
| A4  | (iv)  | ∂_φ = −Y∂_X + X∂_Y unproved | Significant |
| A5  | (iv)  | Chain-rule step implicit   | Minor     |

The most critical issue is **V1/V2 combined**: the invariance of w under Rx (part ii) is never actually proved; the argument has two consecutive unjustified leaps that together constitute a logical gap in the core claim of part (ii).

---

## Appendix: Full verifier output

```
Bug report:

The solution is **not fully correct** under the stated grading standard. I found these issues:

1. **Location:**
   "Therefore the measures \(\mu^\pm\) canonically associated to \(u\) are also \(R_x\)-invariant.
   (If one views \(\mu^\pm\) as the Jordan parts of a signed measure determined by \(u\), this follows
   from uniqueness of the Jordan decomposition.)"

   **Description:** **Justification Gap.**
   This does not actually prove \(R_x\)-invariance of \(\mu^\pm\). The parenthetical argument is
   conditional ("If one views…"), so the needed premise is not established. Also, even under that
   interpretation, the proof does not show that pushing forward by \(R_x\) gives another Jordan
   decomposition of the same signed measure.

2. **Location:**
   "Since \(R_x\) is a rotation, it preserves the round area measure \(dA\) as well. Consequently
   the density W = d(μ+ + μ−)/dA is \(R_x\)-invariant."

   **Description:** **Justification Gap.**
   The passage from invariance of the measures to invariance of the Radon-Nikodym derivative is
   asserted without justification. This requires an explicit argument or theorem about how
   Radon-Nikodym derivatives behave under an area-preserving map. As written, the proof does not
   justify \(W\circ R_x = W\); absent extra regularity, one would at best get an almost-everywhere
   statement rather than the pointwise identity used later.
```
