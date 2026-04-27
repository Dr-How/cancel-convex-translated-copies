## Overall Insight

This is a discrete/combinatorial geometry problem about a signed superposition of translated copies of a finite convex-position set \(S\subset \mathbb{R}^2\). The universal lower bound \(|\operatorname{supp}(\sigma)|\ge n\) comes from the Lonely Points Lemma: each vertex \(s\in S\) forces at least one uniquely exposed point \(s+t\) in the union \(S+T\), and a uniquely exposed point can never cancel. The real issue is therefore the **equality case**. Once \(|\operatorname{supp}(\sigma)|=n\), those forced lonely points already account for the whole support, so every surviving point is lonely and has coefficient exactly \(\pm1\). That turns the problem from a messy many-translate cancellation problem into a boundary-geometry problem on exposed arcs of \(\operatorname{conv}(S)+\operatorname{conv}(T)\).

The key geometric move is to cut the polygon \(S\) between two surviving vertices of opposite sign and study the two boundary chains between them. On a long strictly convex chain, opposite-sign exposed translates cannot cancel “perfectly”: the exposed envelope contributes strictly more than one surviving point per chain vertex. This is what forces \(n\le 4\). The remaining small cases are then settled by elementary Minkowski-sum geometry: a nontrivial addend always increases the number of vertices of a triangle, and of any non-parallelogram quadrilateral. One caveat: as written, the conjecture has a degenerate counterexample for \(n=2\), e.g. \(S=\{0,a\}\) and \(T=\{0^{+},a^{-}\}\), so the decomposition below targets the intended non-collinear case \(n\ge 3\).

## Subproblem Decomposition

### Subproblem 1: Lower bound and rigidity of the equality case

**Statement**: Let \(S\subset \mathbb{R}^2\) be a finite set of \(n\) points in convex position, let \(T\subset \mathbb{R}^2\) be a finite signed set of translation vectors, let \(\sigma\) be the induced signed counting function, and write \(P=\operatorname{conv}(S)\), \(Q=\operatorname{conv}(T)\); prove \(|\operatorname{supp}(\sigma)|\ge n\), and if \(|\operatorname{supp}(\sigma)|=n\), then for each \(s\in S\) there is a unique point \(\ell_s=s+t(s)\in \operatorname{supp}(\sigma)\) covered by exactly one translate \(S+t(s)\), hence \(\sigma(\ell_s)=\sigma(t(s))\in\{\pm1\}\), and every vertex of \(P+Q\) belongs to \(\operatorname{supp}(\sigma)\).

**Role**: This re-establishes the known lower bound and gives the crucial rigidity needed later: in the extremal case, every nonzero point is lonely, so the support is a boundary object with no higher multiplicities.

**Approach**: Apply the Lonely Points Lemma to \(S\) against the whole family \(T\); in the equality case, the \(n\) lonely points exhaust the support. For the last clause, expose vertices of \(P+Q\) by linear functionals.

**Difficulty**: medium

### Subproblem 2: Find opposite-sign endpoints and split \(S\) into two boundary chains

**Statement**: Assume the equality case of Subproblem 1, assume \(n\ge 3\), and assume \(T\) contains at least one \(+\)-signed and at least one \(-\)-signed vector; prove that the lonely support points \(\ell_s\) are not all of the same sign, so there exist vertices \(s_a,s_b\in S\) with \(\sigma(\ell_{s_a})=+1\) and \(\sigma(\ell_{s_b})=-1\), and after an affine change of coordinates making \(s_a\) the leftmost and \(s_b\) the rightmost vertex of \(S\), the boundary of \(P=\operatorname{conv}(S)\) decomposes into an upper chain \(U\) and a lower chain \(L\), each a strictly convex \(x\)-monotone chain with endpoints \(s_a,s_b\), and the exposed translate set of \(Q=\operatorname{conv}(T)\) on the normal interval of each chain is nontrivial.

**Role**: This converts the global problem into two one-sided boundary-chain problems, each forced to see both signs through its endpoints.

**Approach**: First rule out the possibility that all lonely support points have the same sign; then choose opposite-sign vertices and use a generic affine normalization so the two boundary arcs become upper/lower strictly convex chains.

**Difficulty**: medium

### Subproblem 3: Long chains force extra surviving points

**Statement**: With \(U\) and \(L\) as in Subproblem 2, let \(C\in\{U,L\}\), let \(m=|C|\), let \(I_C\) be the open interval of outer normal directions corresponding to the interior of \(C\), and let
\[
E_C=\Bigl\{p\in \partial(P+Q): \exists\,u\in I_C \text{ with } u\cdot p=\max_{x\in P+Q}u\cdot x\Bigr\};
\]
prove that if \(m\ge 4\), then \(|E_C\cap \operatorname{supp}(\sigma)|>m\), and therefore both chains satisfy \(|U|\le 3\) and \(|L|\le 3\), so \(n=|U|+|L|-2\le 4\).

**Role**: This is the main extremal step: it upgrades the lower bound to a strict bound on any long strictly convex boundary arc, yielding \(n\le 4\).

**Approach**: Study the exposed envelope arc as a signed sum of translates of a strictly convex chain. Use the linear order along the chain, the monotonicity of exposed translates on \(Q\), and the fact from Subproblem 1 that every surviving point is lonely; once both signs appear on a chain of length at least \(4\), perfect cancellation along that envelope is impossible.

**Difficulty**: hard

### Subproblem 4: Rule out triangles and force a quadrilateral extremizer to be a parallelogram

**Statement**: Let \(P=\operatorname{conv}(S)\) and \(Q=\operatorname{conv}(T)\), with \(Q\) nontrivial because \(T\) contains at least two distinct translation vectors; prove (i) if \(P\) is a triangle, then \(P+Q\) has at least \(4\) vertices, and (ii) if \(P\) is a convex quadrilateral that is not a parallelogram, then \(P+Q\) has at least \(5\) vertices, and hence, since every vertex of \(P+Q\) lies in \(\operatorname{supp}(\sigma)\) by Subproblem 1, the equality case with \(n\ge 3\) excludes \(n=3\) and forces any \(n=4\) extremal set \(S\) to be the vertex set of a parallelogram.

**Role**: This finishes the small cases after Subproblem 3 has reduced the problem to \(n\le 4\).

**Approach**: Use the edge-direction description of Minkowski sums of convex polygons: a nontrivial addend always contributes a new edge direction to a triangle, and contributes at least one new edge to any non-parallelogram quadrilateral; then combine with Subproblem 1’s “vertices of \(P+Q\) survive” fact.

**Difficulty**: medium

## Integration Sketch

Subproblem 1 gives the Lonely Points lower bound and, in the extremal case \(|\operatorname{supp}(\sigma)|=n\), shows that every surviving point is lonely and every vertex of \(P+Q\) survives. Subproblem 2 then finds opposite-sign surviving vertices and cuts \(S\) into two strictly convex boundary chains \(U\) and \(L\) whose endpoint signs differ. Subproblem 3 proves that a chain of length at least \(4\) would force strictly more than one surviving point per chain vertex on its exposed envelope arc, contradicting equality; hence \(|U|,|L|\le 3\) and therefore \(n\le 4\). Finally, Subproblem 4 handles the remaining possibilities: a triangle cannot be extremal because \(P+Q\) would already have at least \(4\) vertices, and a non-parallelogram quadrilateral cannot be extremal because \(P+Q\) would have at least \(5\) vertices. Thus, for the intended non-collinear version of the theorem (\(n\ge 3\)), equality with both signs forces \(n=4\) and \(S\) to be a parallelogram.