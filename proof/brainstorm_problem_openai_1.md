## Overall Insight

This is an extremal problem in combinatorial geometry / additive geometry: one studies the support of a signed translate-sum
\[
f=\mathbf 1_S * \mu,
\]
where \(S\) is the vertex set of a convex polygon and \(\mu\) is a finitely supported signed measure on translating vectors. The Lonely Points Lemma gives the universal lower bound \(|\operatorname{supp}(f)|\ge |S|=n\). The real issue is the equality case. The key idea is that if equality holds, then the lonely points already account for the entire support, so every other point created by overlapping translates must cancel exactly. That converts the problem from a raw counting problem into a rigidity problem about how a convex polygon can intersect its own translates.

The right geometric invariant is the self-overlap set \(S\cap(S+v)\). For a convex polygon vertex set, any nonzero translate can hit it in at most two vertices, and a two-point overlap is already the footprint of a parallelogram. From there, one splits according to the geometry of the net translate vectors: if they are collinear, a telescoping argument along the line forces a large overlap \(S\cap(S+v)\); if their convex hull is two-dimensional, the boundary of \(\operatorname{conv}(S)+\operatorname{conv}(U)\) forces alternating signs on adjacent extreme translates, and for \(n\ge 5\) this creates an unavoidable same-sign overlap that cannot cancel. One important caveat: as written, the conjecture has a 2-point counterexample (\(S=\{a,b\}\), \(T=\{0,+1;\,b-a,-1\}\)), so the decomposition below targets the corrected full-dimensional case where \(\dim \operatorname{conv}(S)=2\), i.e. \(S\) is a convex \(n\)-gon with \(n\ge 3\).

## Subproblem Decomposition

### Subproblem 1: Lower bound and the extremal consequence of equality

**Statement**: Let \(S\subset \mathbb R^2\) be the vertex set of a convex \(n\)-gon, let \(c(u)=\sum_{t\in T:\,t=u}\sigma(t)\), let \(U=\{u\in\mathbb R^2:c(u)\neq 0\}\), and define
\[
f(p)=\sum_{u\in U} c(u)\,\mathbf 1_{\{p-u\in S\}}.
\]
Then \(|\operatorname{supp}(f)|\ge n\); moreover, if \(|\operatorname{supp}(f)|=n\), then \(\operatorname{supp}(f)=\{\ell_s:s\in S\}\) for \(n\) distinct points \(\ell_s=s+u_s\) that each have a unique representation \(\ell_s=s+u_s\) with \(s\in S\) and \(u_s\in U\).

**Role**: This re-establishes the known lower bound and, more importantly, turns the equality case into a “perfect cancellation off the lonely points” statement.

**Approach**: Apply the Lonely Points Lemma to \(S\) and \(U\); if the support has exactly \(n\) points, the \(n\) lonely points already exhaust it.

**Difficulty**: easy

### Subproblem 2: Rigidity of overlaps of a convex polygon with a translate

**Statement**: Let \(S\subset \mathbb R^2\) be the vertex set of a convex \(n\)-gon and let \(v\in\mathbb R^2\setminus\{0\}\). Then
\[
|S\cap(S+v)|\le 2.
\]
If equality holds, say \(S\cap(S+v)=\{x,y\}\), then \(x-v,y-v,x,y\in S\) are four distinct vertices satisfying \(x+(y-v)=y+(x-v)\), so these four points form a parallelogram.

**Role**: This is the basic geometric cap on how much cancellation any single translation difference can produce, and it is the main rigidity input used in every later case split.

**Approach**: Compare the cyclic order of vertices on \(\operatorname{conv}(S)\) and on its translate \(\operatorname{conv}(S)+v\), or equivalently analyze boundary intersections of two translated convex polygons.

**Difficulty**: medium

### Subproblem 3: The collinear translate-hull case

**Statement**: Let \(S\subset\mathbb R^2\) be the vertex set of a convex \(n\)-gon, let \(c(u)=\sum_{t\in T:\,t=u}\sigma(t)\), let \(U=\{u:c(u)\neq 0\}\), and assume \(U\) is contained in an affine line \(L\). If the signed sum
\[
f(p)=\sum_{u\in U} c(u)\,\mathbf 1_{\{p-u\in S\}}
\]
satisfies \(|\operatorname{supp}(f)|=n\), then there exists a nonzero vector \(v\) parallel to \(L\) such that
\[
|S\cap(S+v)|\ge \frac n2.
\]

**Role**: This completely handles the one-dimensional geometry of the translate vectors and, together with Subproblem 2, yields \(n\le 4\) in the collinear case.

**Approach**: Order the translate vectors along \(L\), rewrite the signed family by summation-by-parts / telescoping into consecutive differences of two translates, and show that equality forces one such difference to produce at least \(n/2\) cancellations.

**Difficulty**: medium

### Subproblem 4: Adjacent extreme translates must have opposite signs in the two-dimensional case

**Statement**: Let \(S\subset\mathbb R^2\) be the vertex set of a convex \(n\)-gon, let \(c(u)=\sum_{t\in T:\,t=u}\sigma(t)\), let \(U=\{u:c(u)\neq 0\}\), let
\[
f(p)=\sum_{u\in U} c(u)\,\mathbf 1_{\{p-u\in S\}},
\qquad
Q=\operatorname{conv}(U),
\]
and assume \(\dim Q=2\) and \(|\operatorname{supp}(f)|=n\). If \(u_i,u_{i+1}\) are consecutive vertices of \(Q\) in cyclic order, then there exists a point
\[
p_i\in (S+u_i)\cap(S+u_{i+1})
\]
that has no third representation \(p_i=s+u\) with \(s\in S\) and \(u\in U\); consequently \(c(u_i)c(u_{i+1})<0\).

**Role**: This forces an alternating sign pattern on the extreme translate vectors, which is the first major rigidity statement in the genuinely two-dimensional case.

**Approach**: Study the boundary-block decomposition of \(\operatorname{conv}(S)+Q\); the transition point between two adjacent exposed blocks is a two-preimage point that must cancel.

**Difficulty**: hard

### Subproblem 5: Alternating extreme signs are impossible when \(n\ge 5\)

**Statement**: In the setup of Subproblem 4, assume additionally that \(n\ge 5\). Then there exist two nonadjacent vertices \(u_i,u_j\in \operatorname{vert}(Q)\) with \(c(u_i)c(u_j)>0\) and a point \(p\in\mathbb R^2\) having exactly the two representations
\[
p=s_a+u_i=s_b+u_j
\]
with \(s_a,s_b\in S\); therefore \(f(p)\neq 0\), contradicting \(|\operatorname{supp}(f)|=n\).

**Role**: This rules out every two-dimensional translate-hull equality case once \(n\ge 5\), so combined with Subproblem 3 it yields the global bound \(n\le 4\) for the corrected theorem.

**Approach**: After Subproblem 4, the signs on \(\operatorname{vert}(Q)\) alternate; choose a shortest same-sign diagonal of \(Q\) (or equivalently the shortest skipped boundary arc) and use convexity to show that the corresponding overlap point is exclusive to those two same-sign translates.

**Difficulty**: hard

### Subproblem 6: Finish the full-dimensional classification at \(n\le 4\)

**Statement**: Let \(S\subset\mathbb R^2\) be the vertex set of a convex \(n\)-gon with \(\dim\operatorname{conv}(S)=2\), and let \(T\) contain both signs. If \(|\operatorname{supp}(\sigma)|=n\) and \(n\le 4\), then \(n=4\), and after cyclic labeling \(S=\{s_1,s_2,s_3,s_4\}\) one has
\[
s_1+s_3=s_2+s_4,
\]
equivalently \(S\) is the vertex set of a parallelogram. Conversely, if
\[
S=\{x,\ x+a,\ x+b,\ x+a+b\},
\]
then choosing \(T=\{0,a,b,a+b\}\) with signs \(+,-,-,+\) gives \(|\operatorname{supp}(\sigma)|=4\).

**Role**: This excludes the triangle and identifies the unique full-dimensional extremal configuration, while also showing sharpness.

**Approach**: Use Subproblems 3–5 to rule out \(n=3\); then obtain a nonzero \(v\) with \(|S\cap(S+v)|=2\) and invoke Subproblem 2 to force a parallelogram; finish with the explicit signed \(4\)-translate construction.

**Difficulty**: medium

## Integration Sketch

After correcting the statement to the full-dimensional case \(\dim\operatorname{conv}(S)=2\), Subproblem 1 gives the lower bound and shows that equality means only lonely points survive, so every other point in \(S+U\) cancels exactly. Subproblem 2 supplies the universal overlap rigidity \(|S\cap(S+v)|\le 2\), with equality characterizing a parallelogram pattern. Now split by the convex hull \(Q=\operatorname{conv}(U)\) of the net translate vectors: if \(Q\) is collinear, Subproblem 3 telescopes the signed family along that line and produces a vector \(v\) with \(|S\cap(S+v)|\ge n/2\), hence \(n\le 4\) by Subproblem 2; if \(\dim Q=2\), Subproblem 4 forces alternating signs on adjacent extreme translates, and Subproblem 5 shows that for \(n\ge 5\) this alternating pattern creates an exclusive same-sign overlap, contradicting equality, so again \(n\le 4\). Finally, Subproblem 6 rules out the triangle in the full-dimensional setting, deduces \(n=4\), and then converts the resulting two-point self-overlap into the diagonal identity \(s_1+s_3=s_2+s_4\), proving that \(S\) is a parallelogram; the explicit \(+,-,-,+\) construction shows that this bound is sharp.