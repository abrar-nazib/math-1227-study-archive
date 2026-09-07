# Math 1227 — 2024 Q6 study guide

Read [Matrix rank, echelon form, and normal form](../concepts/matrix-rank-echelon-form-and-normal-form.md) before part (a), then [Differential equations: the ground floor](../concepts/differential-equations-foundations.md) and [First-order ODEs](../concepts/first-order-odes-exact-integrating-factors-and-substitutions.md) before parts (b) and (c).

## Q6(a) Rank and normal form

> Define rank of a matrix. Reduce \(A=\begin{pmatrix}2&3&-1&-1\\1&-1&-2&-4\\3&1&3&-2\\6&3&0&-7\end{pmatrix}\) into normal form and hence find its rank.

### Concept map

The rank asks, “how many rows carry genuinely new information?” Elementary row operations expose that information as pivots without changing rank. Three pivots will appear. Row reduction alone reaches echelon form; the final column operation is needed because the paper specifically asks for normal form.

### Solve it yourself

1. Bring the row with first entry \(1\) to the top, then zero everything beneath it in column 1.
2. Use the second pivot to zero the remaining entries beneath column 2.
3. When a zero row appears, count the pivots: that already tells the rank.
4. Continue: make the pivots \(1\), clear above them, then clear the remaining fourth column by a column operation.

### Detailed answer

> [!IMPORTANT]
> **Exam definition — rank**
>
> The rank of a matrix is the order of the largest nonzero minor; equivalently, it is the number of nonzero rows in its row-echelon form, or the number of \(1\)s in its normal form.

Start by interchanging rows 1 and 2 so the first pivot is \(1\):

\[
\begin{pmatrix}2&3&-1&-1\\1&-1&-2&-4\\3&1&3&-2\\6&3&0&-7\end{pmatrix}
\xrightarrow{R_1\leftrightarrow R_2}
\begin{pmatrix}1&-1&-2&-4\\2&3&-1&-1\\3&1&3&-2\\6&3&0&-7\end{pmatrix}.
\]

Eliminate entries below the first pivot:

\[
R_2\to R_2-2R_1=(0,5,3,7),
\]

\[
R_3\to R_3-3R_1=(0,4,9,10),
\]

\[
R_4\to R_4-6R_1=(0,9,12,17).
\]

Thus

\[
\begin{pmatrix}1&-1&-2&-4\\0&5&3&7\\0&4&9&10\\0&9&12&17\end{pmatrix}.
\]

Remove the second-column entries without fractions:

\[
R_3\to5R_3-4R_2=(0,0,33,22),
\]

\[
R_4\to5R_4-9R_2=(0,0,33,22),
\]

\[
R_4\to R_4-R_3=(0,0,0,0).
\]

We have

\[
\begin{pmatrix}1&-1&-2&-4\\0&5&3&7\\0&0&33&22\\0&0&0&0\end{pmatrix}.
\]

Scale the two lower pivots:

\[
R_2\to\frac15R_2,\qquad R_3\to\frac1{33}R_3.
\]

The matrix becomes

\[
\begin{pmatrix}1&-1&-2&-4\\0&1&\frac35&\frac75\\0&0&1&\frac23\\0&0&0&0\end{pmatrix}.
\]

Clear the third entry in row 2:

\[
R_2\to R_2-\frac35R_3
\]

\[
(0,1,\tfrac35,\tfrac75)-\tfrac35(0,0,1,\tfrac23)
=(0,1,0,\tfrac75-\tfrac25)
=(0,1,0,1).
\]

Clear the second entry in row 1:

\[
R_1\to R_1+R_2
\]

\[
(1,-1,-2,-4)+(0,1,0,1)=(1,0,-2,-3).
\]

Clear the third entry in row 1:

\[
R_1\to R_1+2R_3
\]

\[
(1,0,-2,-3)+2(0,0,1,\tfrac23)
=(1,0,0,-3+\tfrac43)
=(1,0,0,-\tfrac53).
\]

We now have

\[
\begin{pmatrix}1&0&0&-\frac53\\0&1&0&1\\0&0&1&\frac23\\0&0&0&0\end{pmatrix}.
\]

Now use a column operation to clear column 4:

\[
C_4\to C_4+\frac53C_1-C_2-\frac23C_3.
\]

Therefore the normal form is

\[
\boxed{\begin{pmatrix}1&0&0&0\\0&1&0&0\\0&0&1&0\\0&0&0&0\end{pmatrix}}.
\]

It has three leading \(1\)s, so \(\boxed{\operatorname{rank}(A)=3}\).

## Q6(b) Definition and uses of a differential equation

> Define differential equation. Also mention the uses of differential equation.

### Detailed answer

A differential equation is an equation involving an unknown function and one or more of its derivatives. It describes a quantity through its rate(s) of change rather than directly giving the finished function.

Uses include modelling the motion of projectiles, rockets, and planets; current and charge in electrical circuits; heat conduction; vibration of strings and membranes; population growth and radioactive decay; chemical reactions; and curves with prescribed geometrical properties. See [the applications explanation](../concepts/differential-equations-foundations.md#7-why-des-matter) for the intuition behind this list.

## Q6(c) Exact differential equation

> Solve \((y^2e^{xy^2}+4x^3)dx+(2xye^{xy^2}-3y^2)dy=0\).

### Concept map and solve-it-yourself path

It is written as \(Mdx+Ndy=0\), so first test exactness. If exact, integrate \(M\) with respect to \(x\), add \(g(y)\), compare its \(y\)-derivative with \(N\), then set the potential equal to a constant.

### Detailed answer

Let

\[
M=y^2e^{xy^2}+4x^3,\qquad N=2xye^{xy^2}-3y^2.
\]

Differentiate \(M\) with respect to \(y\), holding \(x\) constant. [Product and chain rules: \(d(uv)/dy=u'v+uv'\), \(d(e^{u})/dy=e^u u'\).]

\[
M_y=2ye^{xy^2}+y^2e^{xy^2}(2xy).
\]

\[
M_y=2ye^{xy^2}+2xy^3e^{xy^2}.
\]

Differentiate \(N\) with respect to \(x\), holding \(y\) constant:

\[
N_x=2ye^{xy^2}+2xye^{xy^2}(y^2)-0.
\]

\[
N_x=2ye^{xy^2}+2xy^3e^{xy^2}=M_y.
\]

The equation is exact. Integrate \(M\) with respect to \(x\):

\[
\Phi=\int\bigl(y^2e^{xy^2}+4x^3\bigr)dx+g(y).
\]

For the first term, \(u=xy^2\), so \(du=y^2dx\):

\[
\int y^2e^{xy^2}dx=\int e^u du=e^u=e^{xy^2}.
\]

For the second term, [Power rule: \(\int x^n dx=x^{n+1}/(n+1)+C\)]:

\[
\int4x^3dx=x^4.
\]

Thus

\[
\Phi=e^{xy^2}+x^4+g(y).
\]

Differentiate with respect to \(y\):

\[
\Phi_y=2xye^{xy^2}+g'(y).
\]

Match it to \(N\):

\[
2xye^{xy^2}+g'(y)=2xye^{xy^2}-3y^2,
\]

\[
g'(y)=-3y^2,
\]

\[
g(y)=-y^3.
\]

Hence the general solution is

\[
\boxed{e^{xy^2}+x^4-y^3=C}.
\]
