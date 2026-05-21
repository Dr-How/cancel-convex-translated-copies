## Overall Insight

The right way to attack the equality case is not by trying to collapse to two translates or by using only a coarse L²-count, because those arguments lose too much structure when |T+| and |T−| are both larger than 1. Instead, the key idea is to exploit the full rigidity of equality in the Lonely Points Lemma: if |supp(σ)|=|S|=n, then every nonzero point is lonely, hence uniquely represented. That uniqueness pins down, for each vertex of conv(S), a single translate that is exposed on the entire normal cone of that vertex.

Once that exposed-translate assignment is in place, the problem becomes a boundary-structure problem for the Minkowski sum P+Q, where P=conv(S) and Q=conv(T). Each edge of P+Q reduces to a one-dimensional cancellation problem, forcing the T-points on the corresponding face of Q to form a full alternating arithmetic progression.

### Subproblem 2: One exposed translate per vertex cone

**Statement**: Assume the extremal equality |supp(σ)|=n. Let P=conv(S), vertices s_1,…,s_n in cyclic order, and let C_i be the open normal cone of P at s_i (i.e. the set of directions u∈ℝ² such that u·s_i > u·s_j for all j≠i). Then for each i there is a unique t_i∈T such that t_i = argmax_{t∈T} u·t for every u∈C_i. Moreover t_i is the lonely translate of s_i (from Subproblem 1), so ℓ_{s_i}=s_i+t_i.

**Approach**: For each u∈C_i, the lonely-points argument gives a lonely point s_i+t where t maximizes u on T. If two different translates t, t' both maximized some u∈C_i (for different values of u within C_i), then one of them, say t, is not the maximizer for some u'∈C_i and t' is. But then s_i+t would also be a lonely point for direction u (since s_i is the unique max of u on S and t is the unique max of u on T at that direction). If t≠t', then s_i+t and s_i+t' are both in the support, and both are distinct lonely points associated with s_i — but lonely points are indexed by s∈S, and each s has exactly one lonely point. This contradicts |supp|=n (we would get more than n support points, or two lonely points for the same s). Therefore t_i is uniquely determined for the whole cone C_i, and must equal t_{s_i} from Subproblem 1.

**Difficulty**: medium

## Integration Sketch

Subproblem 1 gives the lower bound |supp(σ)|≥n and shows that equality means the support consists exactly of n lonely, uniquely represented points. Subproblem 2 then assigns to each vertex s_i of S a unique translate t_i exposed on the whole normal cone of s_i. Subproblem 3 upgrades that assignment to a boundary description of P+Q, where Q=conv(T): the support points are precisely the vertices x_i=s_i+t_i, and each edge of P corresponds to a face [t_i,t_{i+1}] of Q. Subproblem 4 shows that every such face is a full arithmetic progression with alternating signs. Subproblem 5 proves that these alternating face-chains cannot exist if P has at least three edge directions, so equality forces P to have only two edge directions. Finally, Subproblem 6 identifies the only convex-position set with exactly two edge directions as a 4-point parallelogram. Hence equality with both signs implies n=4 and S is the vertex set of a parallelogram.
