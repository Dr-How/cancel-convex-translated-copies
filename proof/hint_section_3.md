## Overall Insight

The key insight for the equality case is **rigidity**: if |{p:σ(p)≠0}|=n, every other incidence cancels perfectly. The crucial geometric bound is that two distinct translates of a convex set can share at most two points. This sharply limits opposite-sign cancellation and is what collapses the general configuration to a two-translate situation.

### Subproblem 3: Extremal equality forces exactly one positive and one negative translate

**Statement**: Let S⊂ℝ² be a finite set of n≥3 points in convex position, let T⊂ℝ² be finite with |T|≥2, let ε:T→{+1,-1} attain both signs, and define F(p)=Σ_{t∈T,p∈S+t} ε(t). Assume |{p∈ℝ²:F(p)≠0}|=n.

The following two facts may be used as given:
- (Lonely Points Lemma) Each s∈S has a lonely point ℓ_s=s+t_s∈S+T with F(ℓ_s)=ε(t_s)≠0; in the equality case {p:F(p)≠0}={ℓ_s:s∈S}.
- (Overlap Bound) For any v≠0, |S∩(S+v)|≤2.

Prove: |T⁺|=|T⁻|=1.

**Approach**:

Write T⁺={t₁,...,t_k} and T⁻={u₁,...,u_m}.

Key counting argument:
1. By the Lonely Points Lemma in the equality case, every point p∈S+T with F(p)=0 must have incidences from BOTH positive and negative translates that cancel. Any point in S+t_i (for some t_i∈T⁺) that is NOT lonely must also lie in some S+u_j (for some u_j∈T⁻) to cancel.

2. The total count of points in ∪_{t∈T}(S+t) is at most n·|T| - (number of overlaps). By the Overlap Bound, each pair (t_i,u_j) contributes at most 2 cancellations.

3. Count total incidences: the sum Σ_p |{t∈T: p-t∈S}|=n|T|. For the support to have size n, we need n|T|-n points to "cancel" (in the sense of not contributing to the support), which requires n(|T|-1) cancellations total. But each pair of translates can create at most 2 cancellations, giving at most 2·|T⁺|·|T⁻| cancellations total. So n(|T|-1) ≤ 2|T⁺|·|T⁻|.

4. Since |T|=|T⁺|+|T⁻|≥2 and n≥3, analyze when this inequality forces |T⁺|=|T⁻|=1.

**Difficulty**: hard

## Integration Sketch

Subproblem 3 uses the Lonely Points Lemma and Overlap Bound to show T has exactly one positive and one negative translate. After translating, the problem reduces to F=1_S - 1_{S+v}. Subproblem 4 gives |{p:F(p)≠0}|=2n-2|S∩(S+v)|≥2n-4, forcing n≤4. Subproblem 5 excludes n=3, so n=4. Subproblem 6 shows that |S∩(S+v)|=2 for a convex quadrilateral forces a parallelogram.
