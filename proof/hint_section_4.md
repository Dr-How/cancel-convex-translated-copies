## Overall Insight

The right way to attack the equality case is not by trying to collapse to two translates or by using only a coarse L²-count, because those arguments lose too much structure when |T+| and |T−| are both larger than 1. Instead, the key idea is to exploit the full rigidity of equality in the Lonely Points Lemma: if |supp(σ)|=|S|=n, then every nonzero point is lonely, hence uniquely represented. That uniqueness pins down, for each vertex of conv(S), a single translate that is exposed on the entire normal cone of that vertex.

Once that exposed-translate assignment is in place, the problem becomes a boundary-structure problem for the Minkowski sum P+Q. Each edge of P+Q reduces to a one-dimensional cancellation problem, forcing the T-points on the corresponding face of Q to form a full alternating arithmetic progression. The hard step is then global: showing that these alternating edge-chains cannot be made compatible around a polygon with three or more edge directions.

### Subproblem 4: One-dimensional alternating chains on exposed faces

**Statement**: Under the extremal equality, with vertices s_i of P, exposed translates t_i∈T, edge directions a_i=s_{i+1}−s_i, and face sets F_i=T∩[t_i,t_{i+1}]: for each i there exists a non-negative integer m_i such that F_i={t_i+k·a_i : 0≤k≤m_i}, t_{i+1}=t_i+m_i·a_i, and σ(t_i+k·a_i)=(−1)^k·σ(t_i) for 0≤k≤m_i.

**Approach**: Fix edge i. The edge of P+Q from x_i=s_i+t_i to x_{i+1}=s_{i+1}+t_{i+1} has direction a_i. A general point on this edge has the form x_i+λa_i for λ∈[0,m_i+1] (using the fact that |x_{i+1}−x_i|=(m_i+1)|a_i| once the chain is established). Any translate t∈F_i contributes to points s_i+t and s_{i+1}+t on or near this edge. Since all interior points of the P+Q edge must cancel (σ=0 by extremal equality) and only translates in F_i can reach points on this edge (they're on the exposed face of Q), the cancellation at each interior point gives a recurrence: σ(t+a_i)+σ(t)=0 for each interior translate t∈F_i\{t_{i+1}}. This forces alternating signs. The arithmetic-progression structure follows from the face description (all translates on the face [t_i,t_{i+1}] of Q that lie in T must have the same step a_i to be collinear in that direction).

**Difficulty**: medium

## Integration Sketch

Subproblem 1 gives the lower bound |supp(σ)|≥n and shows that equality means the support consists exactly of n lonely, uniquely represented points. Subproblem 2 then assigns to each vertex s_i of S a unique translate t_i exposed on the whole normal cone of s_i. Subproblem 3 upgrades that assignment to a boundary description of P+Q, where Q=conv(T): the support points are precisely the vertices x_i=s_i+t_i, and each edge of P corresponds to a face [t_i,t_{i+1}] of Q. Subproblem 4 shows that every such face is a full arithmetic progression with alternating signs. Subproblem 5 proves that these alternating face-chains cannot exist if P has at least three edge directions, so equality forces P to have only two edge directions. Finally, Subproblem 6 identifies the only convex-position set with exactly two edge directions as a 4-point parallelogram. Hence equality with both signs implies n=4 and S is the vertex set of a parallelogram.
