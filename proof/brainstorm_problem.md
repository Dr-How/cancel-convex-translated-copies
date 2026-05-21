## Overall Insight

This is a problem in **discrete/convex geometry with an additive-combinatorial flavor**. The right way to attack the equality case is **not** by trying to collapse to two translates or by using only a coarse \(L^2\)-count, because those arguments lose too much structure when \(|T_+|\) and \(|T_-|\) are both larger than \(1\). Instead, the key idea is to exploit the **full rigidity of equality in the Lonely Points Lemma**: if \(|\operatorname{supp}(\sigma)|=|S|=n\), then every nonzero point is lonely, hence uniquely represented. That uniqueness pins down, for each vertex of \(\operatorname{conv}(S)\), a single translate that is exposed on the entire normal cone of that vertex.

Once that exposed-translate assignment is in place, the problem becomes a **boundary-structure problem for the Minkowski sum** \(P+Q\), where \(P=\operatorname{conv}(S)\) and \(Q=\operatorname{conv}(T)\). Each edge of \(P+Q\) reduces to a one-dimensional cancellation problem, forcing the \(T\)-points on the corresponding face of \(Q\) to form a **full alternating arithmetic progression**. The hard step is then global: showing that these alternating edge-chains cannot be made compatible around a polygon with **three or more edge directions**. That bypasses the gap in the raw \(L^2\) bound and leads directly to the conclusion that only the **two-direction case** survives, i.e. a parallelogram.

## Subproblem Decomposition

### Subproblem 1: Lonely points and extremal rigidity

**Statement**: Let \(S\subset\mathbb{R}^2\) be a finite set of \(n\) points in convex position, let \(T\subset\mathbb{R}^2\) be a finite set of translating vectors with signs \(\sigma(t)\in\{+1,-1\}\), and define
\[
\sigma(p)=\sum_{\substack{t\in T\\ \exists\,s\in S:\,p=s+t}}\sigma(t).
\]
Then
\[
\bigl|\{p\in\mathbb{R}^2:\sigma(p)\neq 0\}\bigr|\ge n.
\]
Moreover, if
\[
\bigl|\{p\in\mathbb{R}^2:\sigma(p)\neq 0\}\bigr|=n,
\]
then for each \(s\in S\) there is a unique point \(\ell_s=s+t_s\) having no other representation \(s'+t'\) with \(s'\in S\), \(t'\in T\); the \(n\) points \(\ell_s\) are exactly \(\{p:\sigma(p)\neq 0\}\); each satisfies \(\sigma(\ell_s)=\sigma(t_s)\in\{\pm1\}\); and, writing \(T_\pm=\{t\in T:\sigma(t)=\pm1\}\), one has \(\bigl||T_+|-|T_-|\bigr|\le 1\).

**Role**: This establishes the lower bound and, more importantly, identifies the equality case as completely rigid: every support point is lonely and uniquely represented.

**Approach**: Apply the Lonely Points Lemma to each \(s\in S\); then in the equality case argue that there can be no additional support points beyond those lonely ones. The bound on \(\bigl||T_+|-|T_-|\bigr|\) comes from the first-moment identity \(\sum_p \sigma(p)=n(|T_+|-|T_-|)\).

**Difficulty**: medium

### Subproblem 2: One exposed translate per vertex cone

**Statement**: Assume the hypotheses and equality conclusion of Subproblem 1. Let \(P=\operatorname{conv}(S)\), list its vertices in cyclic order as \(s_1,\dots,s_n\), and for each \(i\) let \(C_i\) be the open cone of linear functionals \(u\in(\mathbb{R}^2)^*\) such that \(u\) is uniquely maximized on \(P\) at \(s_i\). Then for each \(i\) there exists a unique translate \(t_i\in T\) such that every \(u\in C_i\) is maximized on \(T\) at \(t_i\), and the corresponding lonely/support point is \(x_i=s_i+t_i\).

**Role**: This assigns a single translate \(t_i\) to each vertex \(s_i\) of \(S\), turning equality into a rigid boundary correspondence.

**Approach**: For each \(u\in C_i\), the lonely-points argument gives a lonely point \(s_i+t\) where \(t\) maximizes \(u\) on \(T\). If two different translates occurred for the same cone \(C_i\), they would produce two distinct lonely points associated with the same \(s_i\), contradicting \(|\operatorname{supp}(\sigma)|=n\).

**Difficulty**: medium

### Subproblem 3: Boundary realization in the Minkowski sum

**Statement**: Under the hypotheses of Subproblem 2, let \(Q=\operatorname{conv}(T)\). Then the \(n\) points \(x_i=s_i+t_i\) are the vertices of the Minkowski sum \(P+Q\) in cyclic order, and for each \(i\) (indices modulo \(n\)) the face of \(Q\) exposed by the outer normal of the edge \([s_i,s_{i+1}]\subset P\) is the segment \([t_i,t_{i+1}]\); in particular, \(t_i=t_{i+1}\) or \(t_{i+1}-t_i\) is a nonnegative scalar multiple of \(s_{i+1}-s_i\).

**Role**: This gives a rigorous replacement for the previously unjustified claim about \(\operatorname{conv}(S+T)\): in the equality case, the support points are exactly the boundary vertices coming from the normal-fan matching of \(P\) and \(Q\).

**Approach**: Use support functions and normal cones of Minkowski sums: a direction in \(C_i\) exposes \(s_i\) on \(P\) and \(t_i\) on \(Q\), hence exposes \(x_i=s_i+t_i\) on \(P+Q\). At an edge normal between \(C_i\) and \(C_{i+1}\), the exposed face of \(Q\) must contain both \(t_i\) and \(t_{i+1}\).

**Difficulty**: medium

### Subproblem 4: One-dimensional alternating chains on exposed faces

**Statement**: Assume the hypotheses of Subproblem 1, assume \(|\{p:\sigma(p)\neq0\}|=n\), and keep the notation \(P=\operatorname{conv}(S)\), \(Q=\operatorname{conv}(T)\), \(s_1,\dots,s_n\), \(t_1,\dots,t_n\) from Subproblems 2–3. For each \(i\), write \(a_i=s_{i+1}-s_i\) and let
\[
F_i=T\cap [t_i,t_{i+1}],
\]
where \([t_i,t_{i+1}]\) is the exposed face of \(Q\) corresponding to the edge \([s_i,s_{i+1}]\). Then there exists an integer \(m_i\ge 0\) such that
\[
F_i=\{t_i+k a_i:0\le k\le m_i\},\qquad t_{i+1}=t_i+m_i a_i,
\]
and
\[
\sigma(t_i+k a_i)=(-1)^k\,\sigma(t_i)\qquad (0\le k\le m_i).
\]

**Role**: This is the key local rigidity statement: every exposed face of \(Q\) is a full arithmetic progression with alternating signs, so the 2D problem is reduced edge-by-edge to a rigid 1D cancellation pattern.

**Approach**: Parameterize the corresponding edge of \(P+Q\). The only nonzero coefficients on that edge are its two endpoints \(x_i\) and \(x_{i+1}\); every interior point must cancel. This gives a 1D recurrence for the coefficients contributed by \(T\cap [t_i,t_{i+1}]\), forcing a full chain with step \(a_i\) and alternating signs.

**Difficulty**: medium

### Subproblem 5: Obstruction from three edge directions

**Statement**: Let \(S\subset\mathbb{R}^2\) be a finite set in convex position, let \(T\subset\mathbb{R}^2\) be a finite signed translate set containing both signs, define \(\sigma(p)\) as in Subproblem 1, and assume
\[
\bigl|\{p\in\mathbb{R}^2:\sigma(p)\neq 0\}\bigr|=|S|.
\]
If the boundary of \(P=\operatorname{conv}(S)\) has at least three distinct edge-parallelism classes, then such a signed set \(T\) cannot exist.

**Role**: This is the main exclusion step. It rules out every triangle, every non-parallelogram quadrilateral, and every convex \(n\)-gon with \(n\ge 5\), thereby proving \(n\le 4\) and separately excluding \(n=3\).

**Approach**: Use Subproblem 4 to view each exposed face of \(Q\) as an alternating chain. Two adjacent nonparallel chains force a checkerboard-type local pattern near their common vertex. Propagate that pattern along the boundary. The appearance of a third edge direction makes the propagated local patterns incompatible, or else creates an additional nonzero point of \(\sigma\) beyond the \(n\) lonely vertices.

**Difficulty**: hard

### Subproblem 6: Classification of the two-direction case

**Statement**: Let \(S\subset\mathbb{R}^2\) be a finite set in convex position. If the boundary of \(P=\operatorname{conv}(S)\) uses exactly two distinct edge-parallelism classes, then \(P\) is a parallelogram and \(S\) is exactly its four vertices; equivalently, \(|S|=4\) and \(S\) is the vertex set of a parallelogram.

**Role**: This finishes the classification once Subproblem 5 shows that the equality case cannot have three or more edge directions.

**Approach**: In a convex polygon whose every point of \(S\) is a vertex, consecutive edges cannot be parallel. With only two parallelism classes, the edge directions must alternate, so the polygon has exactly four edges, with opposite sides parallel.

**Difficulty**: easy

## Integration Sketch

Subproblem 1 gives the lower bound \(|\operatorname{supp}(\sigma)|\ge n\) and shows that equality means the support consists exactly of \(n\) lonely, uniquely represented points. Subproblem 2 then assigns to each vertex \(s_i\) of \(S\) a unique translate \(t_i\) exposed on the whole normal cone of \(s_i\). Subproblem 3 upgrades that assignment to a boundary description of \(P+Q\), where \(Q=\operatorname{conv}(T)\): the support points are precisely the vertices \(x_i=s_i+t_i\), and each edge of \(P\) corresponds to a face \([t_i,t_{i+1}]\) of \(Q\). Subproblem 4 shows that every such face is a full arithmetic progression with alternating signs. Subproblem 5 proves that these alternating face-chains cannot exist if \(P\) has at least three edge directions, so equality forces \(P\) to have only two edge directions. Finally, Subproblem 6 identifies the only convex-position set with exactly two edge directions as a 4-point parallelogram. Hence equality with both signs implies \(n=4\) and \(S\) is the vertex set of a parallelogram.