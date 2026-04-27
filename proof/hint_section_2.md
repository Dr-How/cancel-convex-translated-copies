## Overall Insight

The key insight for the equality case is **rigidity**: if |{p:σ(p)≠0}|=n, every other incidence cancels perfectly. The crucial geometric bound is that two distinct translates of a set in convex position can share at most two points. This sharply limits opposite-sign cancellation.

### Subproblem 2: Two distinct translates meet in at most two points

**Statement**: Let S⊂ℝ² be finite in convex position and let v∈ℝ²\{0}. Then |S∩(S+v)|≤2; equivalently, for any distinct t,t'∈ℝ², |(S+t)∩(S+t')|≤2. If |S∩(S+v)|=2, then the two coincidence pairs determine four distinct points of S that form a parallelogram.

**Approach**: Order the points of S cyclically along the boundary of its convex hull and study equal directed chords. Show that a convex polygon cannot contain three distinct vertex-pairs with the same translation vector; if two such pairs exist, they are the opposite sides of a parallelogram.

Concretely: if p₁,p₂,p₃ ∈ S∩(S+v) then S contains the 6 points p₁,p₂,p₃,p₁-v,p₂-v,p₃-v. Label the vertices of conv(S) as s₀<s₁<...<s_{n-1} cyclically. A chord from s_i to s_j with direction v forces s_j - s_i = v. Having three such chords with the same v means three parallel chords in a convex polygon. Use the cyclic order to show this is impossible in a strictly convex polygon (all vertices are extreme).

**Difficulty**: medium

## Integration Sketch

Subproblem 2 supplies the key geometric restriction: any two distinct translates can coincide at at most two points. Subproblem 3 uses that restriction together with the extremal equality to show that there can be only one positive translate and one negative translate. After translating, the problem is reduced to F=1_S - 1_{S+v}, and Subproblem 4 gives |{p:F(p)≠0}|=2n-2|S∩(S+v)|≥2n-4, forcing n≤4.
