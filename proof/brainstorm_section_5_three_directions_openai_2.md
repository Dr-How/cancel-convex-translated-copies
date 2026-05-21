## Overall Insight

This is a discrete convex-geometry / additive-cancellation problem. The earlier subproblems have already done the hard local structural work: along each edge direction \(a_i=s_{i+1}-s_i\), the translate set \(T\) does not behave arbitrarily, but as a one-dimensional arithmetic progression
\[
F_i=\{t_i,t_i+a_i,\dots,t_i+m_i a_i\}
\]
with alternating signs. So the extremal condition \(|\{p:\sigma(p)\neq 0\}|=n\) should be attacked by treating the whole configuration as a collection of alternating boundary chains and asking whether those chains can be made globally compatible.

The key idea is to separate **local cancellation** from **global compatibility**. Locally, each chain \(F_i\) cancels all interior points on its associated edge-segment of \(S+T\). Thus the only way to avoid creating extra nonzero points is for different chains to pair up perfectly across parallel edge directions. Global sign transport around the boundary gives a parity constraint, and once there are three distinct unoriented edge directions, those pairings cannot all be realized simultaneously: some chains must overlap in \(T\), or some additional point of \(S+T\) survives. This bypasses brute-force analysis of all sums \(s+t\) and reduces the problem to boundary geometry plus parity.

## Subproblem Decomposition

### Subproblem 1: Closed translate walk and parity

**Statement**: Assume \(S=\{s_1,\dots,s_n\}\subset \mathbb{R}^2\) are the vertices of a convex \(n\)-gon \(P\) in cyclic order, \(a_i=s_{i+1}-s_i\) (indices mod \(n\)), \(T\subset\mathbb{R}^2\) is finite with signs \(\sigma(t)\in\{\pm1\}\), \(\sigma(p):=\sum_{t\in T,\;p-t\in S}\sigma(t)\), \(|\{p:\sigma(p)\neq0\}|=n\), and for each \(i\) one has \(F_i=T\cap[t_i,t_{i+1}]=\{t_i+r a_i:0\le r\le m_i\}\) with alternating signs; prove that the polygonal chain through \(t_1,\dots,t_n\) closes, so
\[
\sum_{i=1}^n m_i a_i=0,
\]
and that sign consistency around one full traversal forces
\[
\sum_{i=1}^n m_i\equiv 0 \pmod 2.
\]

**Role**: This extracts the two global bookkeeping constraints that every later contradiction uses: vector closure of the translate walk and even total parity of the boundary-step count.

**Approach**: Sum the relations \(t_{i+1}-t_i=m_i a_i\) around the cycle, and separately transport the sign from \(t_1\) back to itself using \(\sigma(t_{i+1})=(-1)^{m_i}\sigma(t_i)\).

**Difficulty**: easy

### Subproblem 2: Local cancellation on one edge-chain

**Statement**: Under the hypotheses of Subproblem 1, fix \(i\) and define
\[
p_{i,r}:=s_i+t_i+r a_i=s_{i+1}+t_i+(r-1)a_i \qquad (1\le r\le m_i);
\]
prove that the two contributions to \(\sigma(p_{i,r})\) coming from the consecutive translates \(t_i+(r-1)a_i\) and \(t_i+r a_i\) cancel because their signs are opposite, so the chain \(F_i\) contributes zero to every interior point of the segment \([\,s_i+t_i,\;s_{i+1}+t_{i+1}\,]\).

**Role**: This isolates the purely one-dimensional cancellation already built into a single boundary chain, showing that any obstruction must come from how different chains interact rather than from the interior of one chain.

**Approach**: Write the same point \(p_{i,r}\) in the two obvious ways using the adjacent vertices \(s_i,s_{i+1}\), and then use the alternating-sign rule on \(F_i\).

**Difficulty**: medium

### Subproblem 3: Compatibility required for one direction class

**Statement**: Under the hypotheses of Subproblem 1, fix an unoriented line-direction class \(\ell\) of edges of \(P\) (i.e. edges parallel as segments); prove that if the edges of \(P\) parallel to \(\ell\) do not form exactly one opposite pair whose chains can be parametrized as
\[
F=\{x+r u:0\le r\le m\},\qquad F'=\{y+r u:0\le r\le m\}
\]
for the same nonzero step vector \(u\in\ell\), with opposite signs on corresponding terms, then the extremal equality \(|\{p:\sigma(p)\neq0\}|=n\) fails because either two distinct translates coincide in \(T\) or some point \(p\in S+T\setminus\{s_r+t_r:1\le r\le n\}\) has \(\sigma(p)\neq0\).

**Role**: This converts “no extra nonzero points” into a precise per-direction compatibility condition: each surviving direction must behave like one matched opposite strip.

**Approach**: Use Subproblem 2 to see that uncanceled mass can only be repaired by another chain in the same line direction; then compare the two parallel arithmetic progressions term-by-term. Any missing partner, unequal step size, unequal length, or wrong sign pattern leaves an unmatched point or forces overlap.

**Difficulty**: medium

### Subproblem 4: Three direction classes are globally incompatible

**Statement**: Assume the hypotheses of Subproblem 1 and that every unoriented edge-direction class satisfies the compatible opposite-pair condition from Subproblem 3; prove that \(P\) still cannot have three distinct unoriented edge-direction classes, because if three classes occur then tracing the closed walk
\[
t_{i+1}=t_i+m_i a_i
\]
and the three matched opposite pairs around the boundary forces either (i) two different chains \(F_i,F_j\) to overlap in a translate of \(T\), or (ii) an additional point
\[
p\in S+T\setminus\{s_r+t_r:1\le r\le n\}
\]
with \(\sigma(p)\neq0\).

**Role**: This is the decisive obstruction: even after imposing the necessary local pairings from Subproblem 3, a third edge direction makes the global geometry impossible.

**Approach**: Work with the closed translate polygon determined by the vertices \(t_i\). Pick three direction classes in cyclic order, compare the three paired strips, and use the closure equation plus the even-parity condition from Subproblem 1 to show that the middle pair cannot be placed compatibly with both neighbors without overlap or leftover support.

**Difficulty**: hard

### Subproblem 5: Polygon-level consequences

**Statement**: Using Subproblem 4 and the elementary fact that a convex polygon has exactly two unoriented edge directions if and only if it is a parallelogram, deduce that no triangle, no non-parallelogram convex quadrilateral, and no convex \(n\)-gon with \(n\ge5\) can satisfy \(|\{p:\sigma(p)\neq0\}|=n\); hence the only surviving extremal case is \(n=4\) with exactly two edge-direction classes.

**Role**: This translates the abstract obstruction into the concrete classification stated in the problem.

**Approach**: Check the direction-count for each polygon type: triangles have \(3\), non-parallelogram quadrilaterals have \(3\) or \(4\), and every convex \(n\)-gon with \(n\ge5\) has at least \(3\) unoriented edge directions.

**Difficulty**: easy

## Integration Sketch

Subproblem 1 gives the global closure and parity constraints for the translate walk \(t_1\to\cdots\to t_n\). Subproblem 2 shows that each single chain already cancels its own interior edge-points, so any obstruction must come from interactions between different chains. Subproblem 3 then upgrades this to a rigid compatibility rule for each edge-direction class: under extremality, every direction must appear as one matched opposite pair of equal arithmetic progressions with opposite signs. Subproblem 4 proves that such compatible pairs cannot coexist for three distinct directions, because the boundary geometry and parity force overlap or an extra surviving point. Finally, Subproblem 5 converts “at most two edge directions” into the polygon classification, leaving only the \(n=4\) parallelogram case.