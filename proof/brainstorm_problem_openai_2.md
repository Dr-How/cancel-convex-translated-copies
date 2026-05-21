## Overall Insight

This is a discrete convex-geometry problem with an additive-combinatorial flavor. The natural first step is to compress the signed multiset \(T\) into net integer coefficients on distinct translation vectors: if
\[
c(u)=\sum_{t\in T:\,t=u}\sigma(t),
\]
then the pointwise function is
\[
\sigma(p)=\sum_{u} c(u)\,\mathbf 1_{S+u}(p),
\]
so repeated copies of the same translation can be merged without changing the support. In the nontrivial reduced case, the Lonely Points Lemma gives the lower bound \(|\operatorname{supp}(\sigma)|\ge n\), and equality is extremely rigid: the \(n\) lonely points already account for the whole support, so every surviving point must have a unique preimage.

The key idea is then to switch from raw cancellation bookkeeping to convex-hull geometry. Let \(P=\operatorname{conv}(S)\) and \(Q=\operatorname{conv}(U)\), where \(U=\{u:c(u)\neq 0\}\). Every vertex of the Minkowski sum \(P+Q\) is a lonely support point, so equality forces \(P+Q\) to have only \(n\) vertices. Standard rigidity of Minkowski sums then implies that \(Q\) must be a line segment: all effective translations are collinear. Once that happens, the problem decomposes into independent one-dimensional signed-translate problems on lines parallel to that segment. Equality on every slice is so restrictive that each slice must contain exactly two vertices of \(S\), with the same separation vector on every slice. A final edge-orientation argument shows that a strictly convex polygon cannot consist of two translated chains of length greater than \(2\), so only a parallelogram remains.

## Subproblem Decomposition

### Subproblem 1: Normalize the translations and exhaust the support by lonely points

**Statement**: Let \(S\subset\mathbb R^2\) be the vertex set of a convex \(n\)-gon, let \(T\) be a finite multiset of translation vectors with signs in \(\{\pm1\}\), define
\[
c(u)=\sum_{t\in T:\,t=u}\sigma(t),\qquad U=\{u\in\mathbb R^2:c(u)\neq 0\},
\]
and
\[
\sigma(p)=\sum_{\substack{u\in U\\ p-u\in S}} c(u),\qquad \operatorname{supp}(\sigma)=\{p\in\mathbb R^2:\sigma(p)\neq 0\}.
\]
Then \(|\operatorname{supp}(\sigma)|\ge n\); moreover, if \(|\operatorname{supp}(\sigma)|=n\), then every point \(p\in \operatorname{supp}(\sigma)\) has a unique representation \(p=s+u\) with \(s\in S\) and \(u\in U\).

**Role**: This is the lower bound and the main rigidity upgrade in the equality case: once equality holds, all surviving points are lonely, so no support point can come from overlapping translates.

**Approach**: First merge equal translation vectors into net coefficients \(c(u)\). Then apply the Lonely Points Lemma to the reduced family \(\{S+u:u\in U\}\): each vertex \(s\in S\) yields a distinct lonely point. If the support has exactly \(n\) points, those lonely points must already be the entire support.

**Difficulty**: easy

### Subproblem 2: Equality forces a single translation direction

**Statement**: In the notation of Subproblem 1, assume \(|U|\ge 2\), the coefficients \(c(u)\) take both positive and negative values, and \(|\operatorname{supp}(\sigma)|=n\). Let \(P=\operatorname{conv}(S)\) and \(Q=\operatorname{conv}(U)\). Then \(Q\) is a nondegenerate line segment, and this segment is parallel to a pair of opposite edges of the convex polygon \(P\).

**Role**: This collapses the genuinely two-dimensional cancellation problem to a one-directional one: all effective translates lie on one line.

**Approach**: Show that every vertex of \(P+Q\) is a lonely point and therefore lies in \(\operatorname{supp}(\sigma)\). Since \(|\operatorname{supp}(\sigma)|=n\), the polygon \(P+Q\) has at most \(n\) vertices. Use the standard edge-direction description of Minkowski sums of convex polygons: adding a 2-dimensional \(Q\) would increase the number of vertices, and a segment preserves the count only when it is parallel to opposite edges of \(P\).

**Difficulty**: medium

### Subproblem 3: Slice rigidity along the common direction

**Statement**: In the notation of Subproblems 1–2, fix a nonzero direction vector \(v\) for the segment \(Q\), write each \(u\in U\) uniquely as \(u=\lambda_u v\), and let \(c(\lambda_u)=c(u)\). For each line \(L\) parallel to \(v\), set \(A_L=S\cap L\). If \(|\operatorname{supp}(\sigma)|=n\), then every line \(L\) with \(A_L\neq\varnothing\) satisfies \(|A_L|=2\), and there exists a single nonzero vector \(w\parallel v\) such that for every such \(L\), if \(A_L=\{a_L,b_L\}\), then \(b_L-a_L=w\).

**Role**: This identifies the exact vertex structure forced by equality: the vertices of \(S\) occur in parallel pairs, and every pair has the same displacement vector.

**Approach**: Because all translations are parallel to \(v\), different lines \(L\parallel v\) do not interact, so the support splits as a sum of independent 1-dimensional problems. A line containing one vertex contributes exactly \(|U|\) support points, so equality forbids singleton lines. On a line containing two vertices at gap \(d\), the induced 1-dimensional signed sum is \(c+\tau_d c\); the condition that its support has size \(2\) forces the reduced coefficient sequence to be a contiguous arithmetic progression with alternating signs and common step \(d\). The same sequence cannot satisfy that extremal condition for two different gaps, so all lines must have the same gap.

**Difficulty**: hard

### Subproblem 4: Two translated chains force a parallelogram

**Statement**: Let \(S\) be the vertex set of a convex \(n\)-gon. Suppose there exist pairwise distinct lines \(L_1,\dots,L_m\), all parallel to a nonzero vector \(v\), and a nonzero vector \(w\parallel v\) such that
\[
S\cap L_i=\{a_i,b_i\}\quad\text{and}\quad b_i-a_i=w\qquad (1\le i\le m),
\]
and the cyclic order of the vertices of \(S\) is
\[
a_1,\ b_1,\ b_2,\ \dots,\ b_m,\ a_m,\ a_{m-1},\ \dots,\ a_2.
\]
Then \(m=2\); hence \(n=2m=4\), and \(S=\{a_1,a_2,a_1+w,a_2+w\}\) is the vertex set of a parallelogram.

**Role**: This is the final convexity step: it converts the common-pairing structure from Subproblem 3 into the precise classification \(n=4\) and parallelogram.

**Approach**: Write the polygon edge sequence as
\[
w,\ e_1,\ e_2,\ \dots,\ e_{m-1},\ -w,\ -e_{m-1},\ \dots,\ -e_1,
\quad\text{where } e_i=a_{i+1}-a_i.
\]
Strict convexity requires all consecutive oriented cross products to have the same nonzero sign. But if \(m\ge 3\), the pairs \((e_i,e_{i+1})\) and later \((-e_{i+1},-e_i)\) occur, and their cross products are opposite. That contradiction forces \(m=2\), and the \(4\)-vertex case is exactly a parallelogram.

**Difficulty**: medium

## Integration Sketch

First compress the multiset \(T\) to net coefficients \(c(u)\) on distinct translation vectors \(U\). Subproblem 1 gives the lower bound \(|\operatorname{supp}(\sigma)|\ge n\), and in the extremal case \(|\operatorname{supp}(\sigma)|=n\) it upgrades to the crucial fact that every support point is lonely. Subproblem 2 then uses exposed-point/Minkowski-sum geometry to show that the reduced translation set \(U\) must be collinear, so all effective cancellations happen along one direction. Subproblem 3 slices the configuration by lines parallel to that direction and proves that equality can hold only if every such slice contains exactly two vertices of \(S\), always separated by the same vector \(w\). Finally, Subproblem 4 shows that a strictly convex polygon with that “two translated chains” structure must have only two slices, so \(n=4\); the common displacement \(w\) then makes the four vertices a parallelogram.