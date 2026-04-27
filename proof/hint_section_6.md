## Overall Insight

Once n=4 is established, equality |{p:F(p)≠0}|=4 forces |S∩(S+v)|=2. The task is to show that a convex quadrilateral with two such overlap points must be a parallelogram.

### Subproblem 6: A convex quadrilateral with a two-point overlap is a parallelogram

**Statement**: Let S={A,B,C,D}⊂ℝ² be four points in convex position (vertices of a convex quadrilateral) in cyclic order. Let v∈ℝ²\{0}. Suppose |S∩(S+v)|=2. Prove S is a parallelogram (i.e., A+C=B+D, equivalently the diagonals bisect each other).

**Approach**:
- S∩(S+v)={P,Q} with P≠Q.
- P∈S and P-v∈S; Q∈S and Q-v∈S.
- The four points P,Q,P-v,Q-v are all in S={A,B,C,D}, hence (since v≠0, so P≠P-v and Q≠Q-v) they are four distinct elements.
- So {P,Q,P-v,Q-v}={A,B,C,D}.
- We have two "chords" in S: the chord P→(P-v) and the chord Q→(Q-v), both with the same vector v. So v = P-(P-v) = Q-(Q-v).
- In a convex quadrilateral ABCD (cyclic order), two parallel chords of equal length must connect opposite vertices. Specifically: the two chords must be AB and DC (or AD and BC), i.e., they are opposite sides.
- If the two chords are AB and CD with AB∥CD and |AB|=|CD| and pointing in the same direction, then ABDC or ABCD... check that this gives a parallelogram.

Key claim: in a convex quadrilateral with vertices in cyclic order A,B,C,D, if there is a vector v with v=B-A=C-D (i.e., A+C=B+D... wait, that's not right). Let me redo: v=P-(P-v). If P=B and P-v=A, then v=B-A. If Q=C and Q-v=D, then v=C-D. So B-A=C-D, giving AB∥DC and |AB|=|DC|: this is exactly the condition for a parallelogram (one pair of opposite sides equal and parallel).

Check the other possible assignments (P=B, P-v=C, etc.) and show they either also give a parallelogram or contradict the convex cyclic ordering.

**Difficulty**: medium

## Integration Sketch

Subproblem 6 completes the proof: after Subproblems 3-5 establish n=4 and reduce to T={t⁺,t⁻} with |S∩(S+v)|=2 (where v=t⁺-t⁻), this subproblem shows S must be a parallelogram. The full proof: SP1→lower bound; SP2→overlap≤2; SP3→exactly 2 translates; SP4→n≤4; SP5→n≠3; SP6→parallelogram.
