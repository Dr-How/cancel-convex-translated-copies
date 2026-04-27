## Overall Insight

This is a problem in discrete convex geometry with an additive-combinatorial flavor: one studies a signed superposition of translated copies of a finite vertex set \(S\) of a convex polygon. The natural starting point is the **Lonely Points Lemma**. Because every \(s\in S\) is an exposed vertex, one can choose a linear functional that uniquely maximizes at \(s\), and this produces a point \(s+t_s\in S+T\) with a unique preimage. Hence there are always at least \(n=|S|\) nonzero points in the signed sum.

The key insight for the equality case is **rigidity**. If \(|\{p:\sigma(p)\neq 0\}|=n\), then the \(n\) lonely points already account for every nonzero point, so every other incidence must cancel perfectly. That converts the problem from “count all cancellations” into “bound how much cancellation is even possible.” The crucial geometric bound is that two distinct translates of a set in convex position can share at most two points. This sharply limits opposite-sign cancellation and is what collapses the general configuration to a two-translate situation. Once reduced to \(S\) versus \(S+v\), the support size is just \(2n-2|S\cap(S+v)|\), and the rest becomes a small-\(n\) classification: triangles cannot have two overlaps, while a convex quadrilateral with two overlaps must be a parallelogram.

## Subproblem Decomposition

### Subproblem 1: Lonely-points lower bound

**Statement**: Let \(S\subset\mathbb{R}^2\) be a finite set of \(n\) points in convex position, let \(T\subset\mathbb{R}^2\) be finite, let \(\varepsilon:T\to\{+1,-1\}\), and define \(F(p)=\sum_{t\in T,\;p\in S+t}\varepsilon(t)\). Then for every \(s\in S\) there exists a point \(\ell_s\in S+T\) with a unique representation \(\ell_s=s+t_s\) for some \(t_s\in T\); the points \(\ell_s\) are distinct and satisfy \(F(\ell_s)=\varepsilon(t_s)\neq 0\), hence \(|\{p\in\mathbb{R}^2:F(p)\neq 0\}|\ge n\).

**Role**: This re-establishes the known lower bound and, in the extremal case \(|\{p:F(p)\neq 0\}|=n\), forces all nonzero points to be exactly these lonely points.

**Approach**: Apply the Lonely Points Lemma: for each \(s\in S\), choose a linear functional uniquely maximized at \(s\), then maximize it over \(s+T\) to obtain a point that cannot come from any other \(s'\in S\).

**Difficulty**: easy

### Subproblem 2: Two distinct translates meet in at most two points

**Statement**: Let \(S\subset\mathbb{R}^2\) be finite in convex position and let \(v\in\mathbb{R}^2\setminus\{0\}\). Then \(|S\cap(S+v)|\le 2\); equivalently, for any distinct \(t,t'\in\mathbb{R}^2\), \(|(S+t)\cap(S+t')|\le 2\). If \(|S\cap(S+v)|=2\), then the two coincidence pairs determine four distinct points of \(S\) that form a parallelogram.

**Role**: This is the basic geometric cap on cancellation: any fixed opposite-sign pair of translates can cancel at only two points.

**Approach**: Order the points of \(S\) cyclically along the boundary of its convex hull and study equal directed chords. Show that a convex polygon cannot contain three distinct vertex-pairs with the same translation vector; if two such pairs exist, they are the opposite sides of a parallelogram.

**Difficulty**: medium

### Subproblem 3: Extremal equality forces exactly one positive and one negative translate

**Statement**: Let \(S\subset\mathbb{R}^2\) be a finite set of \(n\ge 3\) points in convex position, let \(T\subset\mathbb{R}^2\) be finite, let \(\varepsilon:T\to\{+1,-1\}\) attain both signs, and define \(F(p)=\sum_{t\in T,\;p\in S+t}\varepsilon(t)\). If \(|\{p\in\mathbb{R}^2:F(p)\neq 0\}|=n\), then \(|\{t\in T:\varepsilon(t)=+1\}|=|\{t\in T:\varepsilon(t)=-1\}|=1\).

**Role**: This is the main rigidity reduction: it collapses the general signed family to the two-translate model needed for the final count.

**Approach**: Use Subproblem 1 to note that in the equality case every nonzero point is lonely, so every other incidence must be canceled exactly at a point shared with an opposite-sign translate. Then double-count translate-point incidences and use Subproblem 2 to show that any third translate would leave uncanceled points, forcing more than \(n\) nonzero points.

**Difficulty**: hard

### Subproblem 4: Count the support in the two-translate case

**Statement**: Let \(S\subset\mathbb{R}^2\) be a finite set of \(n\) points in convex position, let \(v\in\mathbb{R}^2\setminus\{0\}\), and define \(F(p)=\mathbf{1}_S(p)-\mathbf{1}_{S+v}(p)\). Then \(\{p\in\mathbb{R}^2:F(p)\neq 0\}=S\triangle(S+v)\) and
\[
|\{p\in\mathbb{R}^2:F(p)\neq 0\}|=2n-2|S\cap(S+v)|\ge 2n-4.
\]
In particular, if \(|\{p:F(p)\neq 0\}|=n\), then \(n\le 4\).

**Role**: This turns the structural reduction of Subproblem 3 into the numerical bound \(n\le 4\).

**Approach**: Normalize by translating so the two vectors are \(0\) and \(v\); points in \(S\cap(S+v)\) cancel and all others survive. Then insert the bound from Subproblem 2.

**Difficulty**: easy

### Subproblem 5: Triangles cannot attain equality

**Statement**: Let \(S\subset\mathbb{R}^2\) be the vertex set of a triangle and let \(v\in\mathbb{R}^2\setminus\{0\}\). Then \(|S\cap(S+v)|\le 1\), so for \(F(p)=\mathbf{1}_S(p)-\mathbf{1}_{S+v}(p)\) one has
\[
|\{p\in\mathbb{R}^2:F(p)\neq 0\}|=6-2|S\cap(S+v)|\ge 4.
\]
Hence the equality \(|\{p:F(p)\neq 0\}|=3\) is impossible.

**Role**: After Subproblem 4 gives \(n\le 4\), this removes the only remaining case with \(n<4\).

**Approach**: Show a nonzero translation cannot send two vertices of a triangle to two vertices of the same triangle; then substitute the resulting overlap bound into the formula from Subproblem 4.

**Difficulty**: easy

### Subproblem 6: A quadrilateral with two overlaps is a parallelogram

**Statement**: Let \(S=\{a,b,c,d\}\subset\mathbb{R}^2\) be the vertices of a convex quadrilateral in cyclic order. If there exists \(v\in\mathbb{R}^2\setminus\{0\}\) such that \(|S\cap(S+v)|=2\), then after cyclic relabeling one has \(b-a=v=c-d\), equivalently \(a+c=b+d\), so \(S\) is the vertex set of a parallelogram.

**Role**: This classifies the unique possible extremal quadrilateral once Subproblem 4 forces \(n=4\).

**Approach**: Use the two coincidence pairs to show they must come from the two opposite sides of the quadrilateral; equal and parallel opposite sides imply the diagonals bisect each other, hence the quadrilateral is a parallelogram.

**Difficulty**: medium

## Integration Sketch

Subproblem 1 gives the universal lower bound \(|\{p:\sigma(p)\neq 0\}|\ge n\). If equality holds, those \(n\) lonely points exhaust the entire support, so every other point must cancel completely. Subproblem 2 supplies the key geometric restriction: any two distinct translates can coincide at at most two points. Subproblem 3 uses that restriction together with the extremal equality to show that there can be only one positive translate and one negative translate. After translating, the problem is reduced to \(F=\mathbf{1}_S-\mathbf{1}_{S+v}\), and Subproblem 4 gives \(|\{p:F(p)\neq 0\}|=2n-2|S\cap(S+v)|\ge 2n-4\), forcing \(n\le 4\). Subproblem 5 excludes \(n=3\), so \(n=4\). Finally, in the quadrilateral case equality implies \(|S\cap(S+v)|=2\), and Subproblem 6 shows that this can happen only when the quadrilateral is a parallelogram. Thus equality with both signs occurs exactly in the parallelogram case, and necessarily \(n=4\).