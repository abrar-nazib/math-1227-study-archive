# Math 1227 — 2023 Q1 study guide

Read [Vectors and planes](../concepts/vectors-and-planes.md), especially linear independence, then [Vector-valued curves, unit tangents, and curvature](../concepts/vector-valued-curves-tangent-and-curvature.md). The differentiation rules used below are in the [quick reference](../concepts/differentiation-and-integration-reference.md).

## Q1(a) Linear independence

> Are the vectors \(\vec A=2\hat i-\hat k\), \(\vec B=3\hat i-2\hat j+\hat k\), and \(\vec C=3\hat i+2\hat j-\hat k\) linearly independent? If not, find a dependent relation between them.

### Underlying-concept map

1. Write each vector as a column of components.
2. Form the matrix with those columns.
3. Its determinant is nonzero exactly when these three vectors give three independent directions.
4. Since the question says “if not,” give a relation only if the determinant is zero.

### Solve it yourself

1. Convert \(\hat i,\hat j,\hat k\) notation into component columns.
2. Expand the determinant along the first row, keeping the signs \(+,-,+\).
3. State clearly what a nonzero determinant means.

### Detailed answer

Write the vectors in component form:

\[
\vec A=\langle2,0,-1\rangle,
\qquad
\vec B=\langle3,-2,1\rangle,
\qquad
\vec C=\langle3,2,-1\rangle.
\]

Put them as columns in a matrix:

\[
M=[\vec A\ \vec B\ \vec C]
=\begin{pmatrix}
2&3&3\\
0&-2&2\\
-1&1&-1
\end{pmatrix}.
\]

Calculate its determinant by first-row expansion:

\[
\det M
=2\begin{vmatrix}-2&2\\1&-1\end{vmatrix}
-3\begin{vmatrix}0&2\\-1&-1\end{vmatrix}
+3\begin{vmatrix}0&-2\\-1&1\end{vmatrix}.
\]

Evaluate each \(2\times2\) determinant:

\[
\det M
=2\bigl((-2)(-1)-2(1)\bigr)
-3\bigl(0(-1)-2(-1)\bigr)
+3\bigl(0(1)-(-2)(-1)\bigr).
\]

\[
=2(2-2)-3(0+2)+3(0-2).
\]

\[
=2(0)-3(2)+3(-2).
\]

\[
=0-6-6=-12.
\]

Because \(\det M=-12\ne0\), the only solution of

\[
a\vec A+b\vec B+c\vec C=\vec0
\]

is \(a=b=c=0\). Therefore

\[
\boxed{\vec A,\ \vec B,\ \vec C\text{ are linearly independent.}}
\]

No dependent relation exists, so the “if not” instruction does not apply.

## Q1(b) Unit tangent vector

> Find the unit tangent vector at the point where \(t=2\) on the curve \(x=t^2+1,\ y=4t-3,\ z=2t^2-6t\).

### Underlying-concept map

1. Combine the three coordinate rules into \(\vec r(t)\).
2. Differentiate each coordinate to get the tangent direction \(\vec r\,'(t)\).
3. Substitute \(t=2\) **after** differentiating.
4. Divide by the vector's magnitude to make its length \(1\).

### Solve it yourself

1. Write \(\vec r(t)\), then differentiate it component by component.
2. Evaluate the derivative at \(t=2\).
3. Calculate its length with the square-root formula.
4. Divide every component by that length, then check the resulting vector has magnitude \(1\).

### Detailed answer

The curve is

\[
\vec r(t)=\langle t^2+1,\ 4t-3,\ 2t^2-6t\rangle.
\]

Differentiate each component. [Power rule: \(d(t^n)/dt=nt^{n-1}\); derivative of a constant is \(0\).]

\[
\vec r\,'(t)
=\left\langle\frac{d}{dt}(t^2+1),\ \frac{d}{dt}(4t-3),\ \frac{d}{dt}(2t^2-6t)\right\rangle.
\]

\[
\vec r\,'(t)=\langle2t,\ 4,\ 4t-6\rangle.
\]

At \(t=2\),

\[
\vec r\,'(2)=\langle2(2),\ 4,\ 4(2)-6\rangle.
\]

\[
\vec r\,'(2)=\langle4,4,2\rangle.
\]

Find its magnitude:

\[
|\vec r\,'(2)|=\sqrt{4^2+4^2+2^2}.
\]

\[
=\sqrt{16+16+4}=\sqrt{36}=6.
\]

The unit tangent vector is

\[
\vec T(2)=\frac{\vec r\,'(2)}{|\vec r\,'(2)|}
=\frac{\langle4,4,2\rangle}{6}.
\]

\[
\boxed{\vec T(2)=\left\langle\frac23,\frac23,\frac13\right\rangle.}
\]

Check its length:

\[
|\vec T(2)|
=\sqrt{\left(\frac23\right)^2+\left(\frac23\right)^2+\left(\frac13\right)^2}
=\sqrt{\frac49+\frac49+\frac19}
=\sqrt1=1.
\]

## Q1(c) Curvature

> Find the curvature \(k\) for the curve \(x=t,\ y=t^2,\ z=\frac{2t^3}{3}\).

### Underlying-concept map

1. Curvature measures turning, not speed.
2. Use \(\kappa=|\vec r\,'\times\vec r\,''|/|\vec r\,'|^3\).
3. The cross product must be calculated before taking its magnitude.
4. Notice that \(2t^2+1>0\), which lets a square root simplify safely.

### Solve it yourself

1. Find the first and second derivative vectors.
2. Expand the cross product component by component.
3. Square each component to find the cross-product magnitude.
4. Find \(|\vec r\,'|^3\), then divide and simplify.

### Detailed answer

Write the curve as

\[
\vec r(t)=\left\langle t,\ t^2,\ \frac{2t^3}{3}\right\rangle.
\]

Differentiate once. [Power rule: \(d(t^n)/dt=nt^{n-1}\).]

\[
\vec r\,'(t)
=\left\langle1,\ 2t,\ \frac23(3t^2)\right\rangle
=\langle1,2t,2t^2\rangle.
\]

Differentiate again:

\[
\vec r\,''(t)=\langle0,2,4t\rangle.
\]

Calculate the cross product:

\[
\vec r\,'(t)\times\vec r\,''(t)
=\begin{vmatrix}
\hat i&\hat j&\hat k\\
1&2t&2t^2\\
0&2&4t
\end{vmatrix}.
\]

\[
=\hat i\bigl((2t)(4t)-(2t^2)(2)\bigr)
-\hat j\bigl((1)(4t)-(2t^2)(0)\bigr)
+\hat k\bigl((1)(2)-(2t)(0)\bigr).
\]

\[
=\hat i(8t^2-4t^2)-\hat j(4t-0)+\hat k(2-0).
\]

\[
=\langle4t^2,-4t,2\rangle.
\]

Its magnitude is

\[
|\vec r\,'\times\vec r\,''|
=\sqrt{(4t^2)^2+(-4t)^2+2^2}.
\]

\[
=\sqrt{16t^4+16t^2+4}.
\]

\[
=\sqrt{4(4t^4+4t^2+1)}
=2\sqrt{(2t^2+1)^2}.
\]

Since \(2t^2+1>0\),

\[
|\vec r\,'\times\vec r\,''|=2(2t^2+1).
\]

Now calculate the speed:

\[
|\vec r\,'|
=\sqrt{1^2+(2t)^2+(2t^2)^2}.
\]

\[
=\sqrt{1+4t^2+4t^4}
=\sqrt{(2t^2+1)^2}
=2t^2+1.
\]

Therefore

\[
\kappa(t)=\frac{|\vec r\,'\times\vec r\,''|}{|\vec r\,'|^3}
=\frac{2(2t^2+1)}{(2t^2+1)^3}.
\]

Cancel one nonzero factor \(2t^2+1\):

\[
\boxed{\kappa(t)=\frac{2}{(2t^2+1)^2}.}
\]
