## Overall Insight

After Subproblem 4 gives n≤4, we need to exclude n=3. The key fact is that a nonzero translation cannot send two vertices of a triangle to two other vertices of the same triangle.

### Subproblem 5: Triangles cannot attain equality

**Statement**: Let S={A,B,C}⊂ℝ² be the vertices of a non-degenerate triangle (three non-collinear points), and let v∈ℝ², v≠0. Prove: |S∩(S+v)|≤1. Conclude that for F(p)=𝟏_S(p)-𝟏_{S+v}(p) one has |{p:F(p)≠0}|=2·3-2|S∩(S+v)|≥4>3, so equality |{p:F(p)≠0}|=3=|S| is impossible.

**Approach**: Suppose for contradiction that |S∩(S+v)|≥2, say p₁,p₂∈S∩(S+v) with p₁≠p₂. Then both p₁,p₂∈S={A,B,C} and both p₁-v,p₂-v∈S={A,B,C}. So the four points p₁,p₂,p₁-v,p₂-v all lie in {A,B,C}. Since |{A,B,C}|=3, at least two of these four points coincide. Case analysis: the only possibilities are p₁-v=p₂ or p₁=p₂-v (or trivially p₁-v=p₂-v which would give p₁=p₂, contradiction).

If p₁-v=p₂: then v=p₁-p₂, and p₂-v=p₁, so {p₁,p₂,p₁-v,p₂-v}={p₁,p₂,p₂,p₁}={p₁,p₂}. That means {p₁,p₂}⊆S and {p₁-v,p₂-v}={p₂,p₁}⊆S, which is fine, but then S∩(S+v)⊇{p₁,p₂} still. However, we also need the third element: S={A,B,C} has 3 elements, so w.l.o.g. {A,B,C}={p₁,p₂,X} for some X. Then p₁-v=p₂, p₂-v=p₁: so the three points A,B,C satisfy A-v=B (say), hence A,B,C form an arithmetic progression along the line through A and B, meaning C lies on this line too... but A,B,C are non-collinear. Contradiction.

**Difficulty**: easy

## Integration Sketch

Subproblem 5 excludes n=3 (the triangle case) after Subproblem 4 gives n≤4. Together with Subproblem 4 they force n=4. Subproblem 6 then classifies the quadrilateral.
