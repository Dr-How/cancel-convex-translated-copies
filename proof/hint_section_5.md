## Overall Insight

The right way to attack the equality case is not by trying to collapse to two translates or by using only a coarse L²-count, because those arguments lose too much structure when |T+| and |T−| are both larger than 1. Instead, the key idea is to exploit the full rigidity of equality in the Lonely Points Lemma: if |supp(σ)|=|S|=n, then every nonzero point is lonely, hence uniquely represented. That uniqueness pins down, for each vertex of conv(S), a single translate that is exposed on the entire normal cone of that vertex.

Once that exposed-translate assignment is in place, each edge of P+Q reduces to a one-dimensional cancellation problem, forcing the T-points on the corresponding face of Q to form a full alternating arithmetic progression. The hard step — this subproblem — shows that these alternating edge-chains cannot be made compatible around a polygon with three or more edge directions.

### Subproblem 5: Obstruction from three edge directions

**Statement**: Let S⊂ℝ² be a finite set of n≥3 points in convex position, T a finite signed set with both signs, σ defined as usual. Assume |supp(σ)|=n. From SP1–4 we have: vertices s_i of P=conv(S) in cyclic order, exposed translates t_i∈T, edge directions a_i=s_{i+1}−s_i, and face chains F_i={t_i+k·a_i : 0≤k≤m_i} with alternating signs. If P has at least three distinct edge-direction classes, then a contradiction arises (so no such T can exist).

**Approach**: Follow the sign propagation around the full boundary. Starting from σ(t_1)=ε_1∈{±1}, after traversing all n edges we have σ(t_1) again (since the t_i sequence is cyclic). The sign after going across edge i changes by (−1)^{m_i}, so returning to t_1 requires (−1)^{m_1+m_2+⋯+m_n}=1, i.e., Σm_i is even.

Now track the endpoint equation: summing t_{i+1}−t_i=m_i·a_i around the full cycle gives Σ_i m_i·a_i = 0 (since we return to t_1). The a_i are the edge vectors of P, and Σ_i a_i=0 as well (closed polygon). If all m_i were equal to some constant m, this would be automatic. But if the edge directions fall into at least three classes, the m_i must satisfy a non-trivial linear relation Σ_i m_i·a_i=0 with the a_i spanning at least a 2D subspace with at least three direction classes.

Key: In a convex polygon, opposite edges have directions a_i and −a_j for some j. The equation Σ m_i a_i=0 expresses a non-negative integer combination of the edge vectors summing to zero. With only two direction classes (parallelogram), this is solved by m_i constant on each class. With three or more direction classes, examine whether the system Σ m_i a_i=0, m_i≥0 integer, Σm_i even, has solutions that are also consistent with T being a SET (no repeated vectors). Show that any solution forces some two translates in T to coincide (contradicting T being a set) OR forces some point in S+T outside the n lonely vertices to have σ≠0 (contradicting equality). The key geometric ingredient: if two face chains share an endpoint (t_{i+1}=t_j for some non-consecutive i,j), the translate at that common point is counted in two chains and the alternating patterns impose contradictory sign requirements.

**Difficulty**: hard

## Integration Sketch

Subproblem 1 gives the lower bound |supp(σ)|≥n and shows that equality means the support consists exactly of n lonely, uniquely represented points. Subproblem 2 then assigns to each vertex s_i of S a unique translate t_i exposed on the whole normal cone of s_i. Subproblem 3 upgrades that assignment to a boundary description of P+Q, where Q=conv(T): the support points are precisely the vertices x_i=s_i+t_i, and each edge of P corresponds to a face [t_i,t_{i+1}] of Q. Subproblem 4 shows that every such face is a full arithmetic progression with alternating signs. Subproblem 5 proves that these alternating face-chains cannot exist if P has at least three edge directions, so equality forces P to have only two edge directions. Finally, Subproblem 6 identifies the only convex-position set with exactly two edge directions as a 4-point parallelogram. Hence equality with both signs implies n=4 and S is the vertex set of a parallelogram.
