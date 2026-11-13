# MAH notes, page 7: dependence and collinear endpoints

Page 7 asks us to show that three vectors are dependent, find their relation, and then show that their terminal points lie on a straight line. These are connected, but the last step needs extra reasoning: **dependent vectors do not automatically have collinear endpoints**.

For the meanings of components, terminal points, and linear dependence, first revisit [vectors and planes](vectors-and-planes.md#6-linear-independence-of-vectors). For the determinant expansion used below, see [the first-row expansion](eigenvalues-eigenvectors-and-linear-systems.md#expanding-a-3times3-determinant-along-the-first-row).

## What the question gives

Reading page 7 of `Math MAH Notes.pdf`, the vectors are

\[
\vec A=2\hat i+\hat j-3\hat k,\qquad
\vec B=\hat i-4\hat k,\qquad
\vec C=4\hat i+3\hat j-\hat k.
\]

Imagine each arrow starting at the same origin. Its terminal point is its arrowhead. The question asks about the three arrowheads, not whether the three arrows all point in the same direction.

Our route is: test dependence using a determinant; find a nonzero set of coefficients by solving equations; then compare the displacements between the arrowheads.

## 1. The determinant test

Put the three vectors' components in rows. In \(\vec B\), the missing \(\hat j\) term has coefficient zero:

\[
\Delta=\begin{vmatrix}2&1&-3\\1&0&-4\\4&3&-1\end{vmatrix}.
\]

Expand along the first row, using signs \(+,-,+\), and calculate each small determinant by \(ad-bc\):

\[
\begin{aligned}
\Delta
&=2\begin{vmatrix}0&-4\\3&-1\end{vmatrix}
-1\begin{vmatrix}1&-4\\4&-1\end{vmatrix}
+(-3)\begin{vmatrix}1&0\\4&3\end{vmatrix}\\
&=2\bigl(0(-1)-(-4)(3)\bigr)
-\bigl(1(-1)-(-4)(4)\bigr)
-3\bigl(1(3)-0(4)\bigr)\\
&=2(0+12)-(-1+16)-3(3-0)\\
&=24-15-9\\
&=0.
\end{aligned}
\]

The determinant is zero, so the vectors are dependent. This tells us a nontrivial relation exists, but does not yet tell us its coefficients.

## 2. Find the relation, one step at a time

We seek scalars \(\alpha,\beta,\gamma\), not all zero, such that

\[
\alpha\vec A+\beta\vec B+\gamma\vec C=\vec0.
\]

Substitute the vectors and group matching components:

\[
\begin{aligned}
&\alpha(2\hat i+\hat j-3\hat k)
+\beta(\hat i-4\hat k)
+\gamma(4\hat i+3\hat j-\hat k)=\vec0,\\
&(2\alpha+\beta+4\gamma)\hat i
+(\alpha+3\gamma)\hat j
+(-3\alpha-4\beta-\gamma)\hat k=\vec0.
\end{aligned}
\]

Each component must be zero, giving

\[
\begin{aligned}
2\alpha+\beta+4\gamma&=0, &(1)\\
\alpha+3\gamma&=0, &(2)\\
-3\alpha-4\beta-\gamma&=0. &(3)
\end{aligned}
\]

Start with the shorter second equation:

\[
\alpha=-3\gamma.
\]

Put that into equation (1):

\[
\begin{aligned}
2(-3\gamma)+\beta+4\gamma&=0,\\
-6\gamma+\beta+4\gamma&=0,\\
\beta-2\gamma&=0,\\
\beta&=2\gamma.
\end{aligned}
\]

Check these expressions in equation (3):

\[
\begin{aligned}
-3(-3\gamma)-4(2\gamma)-\gamma&=0,\\
9\gamma-8\gamma-\gamma&=0,\\
0&=0.
\end{aligned}
\]

The third equation adds no new restriction. We can choose any value for \(\gamma\); to get a nonzero relation with small integers, choose \(\gamma=-1\). Then

\[
\begin{aligned}
\alpha&=-3(-1)=3,\\
\beta&=2(-1)=-2,\\
\gamma&=-1.
\end{aligned}
\]

Therefore

\[
\boxed{3\vec A-2\vec B-\vec C=\vec0.}
\]

The coefficients are not all zero, so this relation proves dependence directly too. Multiplying all three coefficients by the same nonzero number gives another valid relation.

**A sign to watch in the handwritten page:** because the \(\hat k\) component of \(\vec B\) is \(-4\), its contribution is \(-4\beta\). A working line near the bottom appears to use \(+4\beta\) and obtain a contradictory zero-only result. The correct check is the one above; the boxed vector relation on the page is correct.

## 3. Why are the terminal points on one line?

Call the endpoints \(P,Q,R\), respectively, and place the arrows' tails at the origin. Their coordinates are the components of the vectors:

\[
P=(2,1,-3),\qquad Q=(1,0,-4),\qquad R=(4,3,-1).
\]

Picture walking from \(Q\) to \(P\), and then from \(Q\) to \(R\). If the second displacement is a scalar multiple of the first, both walks follow the same straight line. Subtract starting coordinates from ending coordinates:

\[
\begin{aligned}
\overrightarrow{QP}
&=P-Q\\
&=(2-1,\ 1-0,\ -3-(-4))\\
&=(1,1,1),
\end{aligned}
\]

\[
\begin{aligned}
\overrightarrow{QR}
&=R-Q\\
&=(4-1,\ 3-0,\ -1-(-4))\\
&=(3,3,3)\\
&=3(1,1,1)\\
&=3\overrightarrow{QP}.
\end{aligned}
\]

So the path from \(Q\) to \(R\) is three times the path from \(Q\) to \(P\): the points are collinear. In fact \(P\) lies between \(Q\) and \(R\), one third of the way along.

### How does this connect to the relation?

Rearrange the relation to make the displacement connection visible:

\[
\begin{aligned}
3\vec A-2\vec B-\vec C&=\vec0,\\
\vec C&=3\vec A-2\vec B,\\
\vec C-\vec B&=3\vec A-3\vec B,\\
\vec C-\vec B&=3(\vec A-\vec B).
\end{aligned}
\]

Since the position vectors begin at the origin, \(\vec A-\vec B\) is the displacement from \(Q\) to \(P\), and \(\vec C-\vec B\) is the displacement from \(Q\) to \(R\). This is exactly the same straight-line test.

The notes also observe that the three coefficients in this particular relation add to zero: \(3-2-1=0\). That is why its terms can be rearranged into differences of position vectors, as above. Merely finding *some* dependence relation is not enough to conclude the endpoints are collinear: the additional zero-sum condition matters. For example, the horizontal and vertical unit arrows and their sum are dependent, but their three endpoints form a triangle.
