## Overall Insight

This is a problem in discrete convex geometry with an additive-combinatorial flavor. The natural starting point is the **Lonely Points Lemma**. Because every s∈S is an exposed vertex, one can choose a linear functional that uniquely maximizes at s, and this produces a point s+t_s∈S+T with a unique preimage. Hence there are always at least n=|S| nonzero points in the signed sum.

The key insight for the equality case is **rigidity**. If |{p:σ(p)≠0}|=n, then the n lonely points already account for every nonzero point, so every other incidence must cancel perfectly.

### Subproblem 1: Lonely-points lower bound

**Statement**: Let S⊂ℝ² be a finite set of n points in convex position, let T⊂ℝ² be finite, let ε:T→{+1,-1}, and define F(p)=Σ_{t∈T, p∈S+t} ε(t). Then for every s∈S there exists a point ℓ_s∈S+T with a unique representation ℓ_s=s+t_s for some t_s∈T; the points ℓ_s are distinct and satisfy F(ℓ_s)=ε(t_s)≠0, hence |{p∈ℝ²:F(p)≠0}|≥n.

**Approach**: Apply the Lonely Points Lemma: for each s∈S, choose a linear functional uniquely maximized at s (this exists since s is a vertex of conv(S)), then maximize it over s+T to obtain a point that cannot come from any other s'∈S.

**Difficulty**: easy

## Integration Sketch

Subproblem 1 gives the universal lower bound |{p:σ(p)≠0}|≥n. If equality holds, those n lonely points exhaust the entire support, so every other point must cancel completely. (The remaining subproblems use this to force S to be a parallelogram.)
