## Overall Insight

This is a discrete convex-geometry / additive-combinatorics problem about a signed union of translates of a convex vertex set. The prior subproblems have already reduced the extremal case to a very rigid boundary description: the distinguished translates $t_1,\dots,t_n$ sit on a second polygonal cycle $Q$, and each boundary segment of $Q$ is completely filled by an arithmetic progression
$$F_i=\{t_i,t_i+a_i,\dots,t_i+m_i a_i\}$$
in the corresponding edge direction $a_i=s_{i+1}-s_i$, with alternating signs. So the problem is no longer “count all cancellations in $\sigma$”; it is “understand what boundary-sign data on $Q$ can possibly telescope down to only $n$ surviving points.”

The key idea is that the telescoping mechanism is compatible with a two-direction boundary cycle (the parallelogram case), but it breaks as soon as the boundary turns through a third direction. Globally, following signs around $Q$ gives a parity constraint $\sum_i m_i\equiv 0\pmod 2$. Locally, if three consecutive edge-direction classes are distinct, the middle chain cannot be canceled consistently from both ends: either two boundary chains overlap in an impermissible way, or an extra point of nonzero total weight survives outside the $n$ already-accounted-for exposed points. This bypasses any brute-force analysis of all equalities $s+t=s'+t'$.

## Subproblem Decomposition

### Subproblem 1: Closed translate polygon and parity

**Statement**: Assume $S=\{s_1,\dots,s_n\}\subset\mathbb R^2$ are the vertices of a convex $n$-gon $P$ in cyclic order, define $a_i=s_{i+1}-s_i$ (indices modulo $n$), let $T\subset\mathbb R^2$ be finite with sign map $\sigma:T\to\{\pm1\}$, set $\sigma(p)=\sum_{t\in T,\ p-t\in S}\sigma(t)$, assume $|\{p:\sigma(p)\neq0\}|=n$, and suppose that for each $i$ one has
$$F_i=T\cap[t_i,t_{i+1}]=\{t_i,t_i+a_i,\dots,t_i+m_i a_i\}$$
with alternating signs and $t_{i+1}=t_i+m_i a_i$; prove that
$$\sum_{i=1}^n m_i a_i=0,$$
and, writing $\varepsilon_i=\sigma(t_i)$, that
$$\varepsilon_{i+1}=(-1)^{m_i}\varepsilon_i\quad\text{for all }i,\qquad (-1)^{m_1+\cdots+m_n}=1,$$
equivalently $\sum_{i=1}^n m_i$ is even.

**Role**: This packages the extremal configuration into a closed polygonal cycle $Q$ with edge vectors $m_i a_i$ and records the global sign-consistency condition needed later.

**Approach**: Sum the displacement relations $t_{i+1}-t_i=m_i a_i$ around the full boundary, and separately propagate the alternating sign pattern from one endpoint of each chain to the next.

**Difficulty**: easy

### Subproblem 2: A third direction appears in a consecutive triple

**Statement**: Let $c_i=[a_i]$ be the cyclic sequence of edge-direction classes of the edges of a convex polygon $P$, in the sense of the problem statement. If the set $\{c_1,\dots,c_n\}$ has at least three elements, then there exists an index $i$ such that $c_i,c_{i+1},c_{i+2}$ are pairwise distinct.

**Role**: This reduces the global hypothesis “at least three edge-direction classes” to a local three-edge configuration, which is the minimal place where the obstruction must be proved.

**Approach**: Prove the contrapositive: if no three consecutive classes are pairwise distinct, then every class equals the class two steps later, so the whole cyclic sequence alternates between only two classes.

**Difficulty**: easy

### Subproblem 3: Local obstruction at a three-direction turn

**Statement**: Assume the setup of Subproblem 1, define $q_r=s_r+t_r$ for $1\le r\le n$, and suppose that for some index $i$ (modulo $n$) the three consecutive direction classes $[a_i],[a_{i+1}],[a_{i+2}]$ are pairwise distinct; then at least one of the following holds:
$$\big(F_i\cap F_{i+1}\big)\setminus\{t_{i+1}\}\neq\varnothing,\qquad \big(F_{i+1}\cap F_{i+2}\big)\setminus\{t_{i+2}\}\neq\varnothing,$$
$$F_i\cap F_{i+2}\neq\varnothing,\qquad \text{or}\qquad \exists\,p\in\mathbb R^2\setminus\{q_1,\dots,q_n\}\text{ with }\sigma(p)\neq0.$$

**Role**: This is the core obstruction lemma: once the boundary turns through three distinct directions, the alternating-chain cancellation cannot remain perfectly telescopic.

**Approach**: Focus on the middle chain $F_{i+1}$ and propagate the endpoint signs from both sides using Subproblem 1. Because the adjacent chains run in directions different from $a_{i+1}$, the two cancellation matchings cannot traverse the whole middle chain and meet cleanly; the first failure produces either a nontrivial boundary-chain overlap or an extra surviving point.

**Difficulty**: hard

### Subproblem 4: Main contradiction from three edge-direction classes

**Statement**: Assume the setup of Subproblem 1 and that the set of edge-direction classes $\{[a_1],\dots,[a_n]\}$ has at least three elements; then the equality
$$|\{p\in\mathbb R^2:\sigma(p)\neq0\}|=n$$
cannot hold.

**Role**: This turns the local obstruction into the full theorem under the stated geometric hypothesis on $P$.

**Approach**: Use Subproblem 2 to find three consecutive distinct direction classes, apply Subproblem 3 to that triple, and note that every outcome contradicts the extremal setup: nontrivial chain overlap violates the boundary geometry, while an extra point with $\sigma(p)\neq0$ violates support size $n$.

**Difficulty**: easy

### Subproblem 5: Classify the surviving polygon type

**Statement**: Prove that every triangle has at least three edge-direction classes, every convex $n$-gon with $n\ge5$ has at least three edge-direction classes, and every convex quadrilateral that is not a parallelogram has at least three edge-direction classes; conclude from Subproblem 4 that the only case not excluded is $n=4$ with exactly two edge-direction classes, i.e. $P$ is a parallelogram.

**Role**: This converts the abstract obstruction into the concrete case split stated at the end of the problem.

**Approach**: Use elementary convex-polygon geometry: a convex polygon with only two direction classes must alternate between those two classes around the boundary, which forces the parallelogram situation; all other listed polygon types necessarily introduce a third class.

**Difficulty**: easy

## Integration Sketch

First encode the exposed translates as a closed polygonal cycle $Q$ whose $i$th edge is the vector $m_i a_i$, and record the global parity/sign constraint obtained by traversing the alternating chains around the full boundary (Subproblem 1). Next, if $P$ has at least three direction classes, extract a local block of three consecutive edges with pairwise distinct classes (Subproblem 2). The central geometric step is then Subproblem 3: such a three-direction turn makes the middle arithmetic progression impossible to cancel perfectly from both ends, so one gets either an impermissible overlap of boundary chains or an additional point outside $\{s_1+t_1,\dots,s_n+t_n\}$ with nonzero total weight. Either alternative contradicts the extremal equality, yielding the main impossibility theorem (Subproblem 4). Finally, the elementary classification of convex polygons by number of edge-direction classes gives the advertised consequences: triangles, all $n\ge5$ polygons, and non-parallelogram quadrilaterals are ruled out, leaving only the $n=4$ parallelogram case (Subproblem 5).