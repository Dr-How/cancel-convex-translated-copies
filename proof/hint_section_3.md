## Overall Insight

The right way to attack the equality case is not by trying to collapse to two translates or by using only a coarse L²-count, because those arguments lose too much structure when |T+| and |T−| are both larger than 1. Instead, the key idea is to exploit the full rigidity of equality in the Lonely Points Lemma. Once that exposed-translate assignment is in place, the problem becomes a boundary-structure problem for the Minkowski sum P+Q, where P=conv(S) and Q=conv(T). Each edge of P+Q reduces to a one-dimensional cancellation problem, forcing the T-points on the corresponding face of Q to form a full alternating arithmetic progression.

### Subproblem 3: Boundary realization in the Minkowski sum

**Statement**: Under the extremal equality, with vertices s_1,…,s_n of P=conv(S) in cyclic order, Q=conv(T), and t_i∈T the unique exposed translate at s_i from SP2: (1) the n points x_i=s_i+t_i are the vertices of P+Q in cyclic order; (2) for each i the face of Q exposed by any outer normal to edge [s_i,s_{i+1}] of P is exactly the segment [t_i,t_{i+1}], and t_{i+1}−t_i is a non-negative scalar multiple of s_{i+1}−s_i (or t_i=t_{i+1}).

**Approach**: Use support functions: h_{P+Q}(u)=h_P(u)+h_Q(u). A direction u∈C_i exposes s_i on P and t_i on Q (by SP2), hence exposes x_i=s_i+t_i on P+Q. As u moves across the boundary between C_i and C_{i+1} (the outer normal direction to edge [s_i,s_{i+1}]), the exposed face of P transitions from {s_i} to {s_{i+1}} while the exposed face of Q transitions from {t_i} to {t_{i+1}}, sweeping out the segment [t_i,t_{i+1}] at the edge normal. The exposed face of P+Q for the edge normal to [s_i,s_{i+1}] is therefore [s_i,s_{i+1}]+[t_i,t_{i+1}], which is parallel to a_i=s_{i+1}−s_i. Since [t_i,t_{i+1}] is also a face of Q exposed by that normal, it must be parallel to a_i, giving the direction constraint. The x_i are vertices of P+Q because they are exposed by directions in C_i, and distinct since |supp|=n.

**Difficulty**: medium

## Integration Sketch

Subproblem 1 gives the lower bound |supp(σ)|≥n and shows that equality means the support consists exactly of n lonely, uniquely represented points. Subproblem 2 then assigns to each vertex s_i of S a unique translate t_i exposed on the whole normal cone of s_i. Subproblem 3 upgrades that assignment to a boundary description of P+Q, where Q=conv(T): the support points are precisely the vertices x_i=s_i+t_i, and each edge of P corresponds to a face [t_i,t_{i+1}] of Q. Subproblem 4 shows that every such face is a full arithmetic progression with alternating signs. Subproblem 5 proves that these alternating face-chains cannot exist if P has at least three edge directions, so equality forces P to have only two edge directions. Finally, Subproblem 6 identifies the only convex-position set with exactly two edge directions as a 4-point parallelogram. Hence equality with both signs implies n=4 and S is the vertex set of a parallelogram.
