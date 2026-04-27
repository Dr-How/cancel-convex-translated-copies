## Overall Insight

Once the general configuration is reduced to exactly two translates (one positive, one negative), the support size has an explicit formula. Combined with the overlap bound, this gives a sharp upper bound on n.

### Subproblem 4: Count the support in the two-translate case

**Statement**: Let S⊂ℝ² be a finite set of n≥3 points in convex position, let v∈ℝ²\{0}, and define F(p)=𝟏_S(p)-𝟏_{S+v}(p). Then {p∈ℝ²:F(p)≠0}=S△(S+v) and |{p:F(p)≠0}|=2n-2|S∩(S+v)|≥2n-4. In particular, if |{p:F(p)≠0}|=n, then n≤4.

**Approach**: Normalize by translating so the two vectors are 0 and v; points in S∩(S+v) cancel and all others survive. The formula follows from inclusion-exclusion: |S∪(S+v)|-|S∩(S+v)|=2n-2|S∩(S+v)|. Then use |S∩(S+v)|≤2 (Overlap Bound, proved separately) to get ≥2n-4. Setting this equal to n gives n≤4.

**Difficulty**: easy

## Integration Sketch

Subproblem 4 turns the structural reduction of Subproblem 3 into the numerical bound n≤4. Combined with Subproblem 5 (triangles can't attain equality), we get n=4. Subproblem 6 then shows the quadrilateral must be a parallelogram.
