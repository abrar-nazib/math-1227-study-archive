# 2024 Q2 Study Guide

This guide teaches curl, flux through a plane, and a triple integral of a vector field. Before attempting it, read:

- [Curl, surface integrals, and volume integrals](../concepts/curl-surface-and-volume-integrals.md)
- [Vectors and planes](../concepts/vectors-and-planes.md) for dot products, normals, and cross products
- [Differentiation and integration quick reference](../concepts/differentiation-and-integration-reference.md)

---

## Q2(a): Curl flux through a bounded plane

**Question.** Evaluate \(\iint_S(\nabla\times\vec F)\cdot\hat n\,ds\) where \(\vec F=(x+2y)\hat i-3z\hat j+x\hat k\) and \(S\) is the surface of \(2x+y+2z=6\) bounded by \(x=0,x=1,y=0,y=2\).

### Underlying-concept map

1. **Curl:** first convert the given vector field into \(\nabla\times\vec F\).
2. **Bounded plane:** the four bounds on \(x\) and \(y\) make the plane into a finite rectangular patch, not an infinite plane.
3. **Surface parameterization:** solve the plane equation for \(z\), then use \(x\) and \(y\) as parameters.
4. **Oriented area:** use a cross product of the two tangent vectors. Its order chooses the normal direction.
5. **Flux integral:** take one dot product and integrate it over the stated rectangle.

### Solve it yourself

1. Identify \(P=x+2y\), \(Q=-3z\), and \(R=x\), then calculate all three components of curl.
2. Rewrite the plane as \(z\) in terms of \(x\) and \(y\).
3. Form \(\vec r(x,y)\), then calculate \(\vec r_x\), \(\vec r_y\), and \(\vec r_x\times\vec r_y\).
4. Check whether that cross product points upward or downward.
5. Dot the curl with the oriented area vector and integrate for \(0\le x\le1\), \(0\le y\le2\).

### Detailed solution

Write the field in component form:

\[
\vec F=P\hat i+Q\hat j+R\hat k,
\qquad
P=x+2y,\quad Q=-3z,\quad R=x.
\]

Use the curl formula

\[
\nabla\times\vec F=
\left(\frac{\partial R}{\partial y}-\frac{\partial Q}{\partial z}\right)\hat i
+\left(\frac{\partial P}{\partial z}-\frac{\partial R}{\partial x}\right)\hat j
+\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)\hat k.
\]

For the partial derivatives below, hold the other variables constant. In particular, \(\partial x/\partial y=0\), \(\partial x/\partial x=1\), and \(\partial(cu)/\partial u=c\) for a constant \(c\). These rules are collected in the linked concept note.

The three components are calculated separately:

\[
\begin{aligned}
\frac{\partial R}{\partial y}-\frac{\partial Q}{\partial z}
&=\frac{\partial x}{\partial y}-\frac{\partial(-3z)}{\partial z}\\
&=0-(-3)\\
&=3,\\[4pt]
\frac{\partial P}{\partial z}-\frac{\partial R}{\partial x}
&=\frac{\partial(x+2y)}{\partial z}-\frac{\partial x}{\partial x}\\
&=0-1\\
&=-1,\\[4pt]
\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}
&=\frac{\partial(-3z)}{\partial x}-\frac{\partial(x+2y)}{\partial y}\\
&=0-2\\
&=-2.
\end{aligned}
\]

Therefore

\[
\nabla\times\vec F=3\hat i-\hat j-2\hat k.
\]

Now parameterize the plane. Start from its equation and solve for \(z\):

\[
\begin{aligned}
2x+y+2z&=6,\\
2z&=6-2x-y,\\
z&=\frac{6-2x-y}{2},\\
z&=3-x-\frac y2.
\end{aligned}
\]

Because the given bounds are already bounds on \(x\) and \(y\), use them as the parameters:

\[
\vec r(x,y)=\left\langle x,y,3-x-\frac y2\right\rangle,
\qquad 0\le x\le1,\quad0\le y\le2.
\]

Differentiate each coordinate to obtain the two tangent vectors:

\[
\text{[Partial-derivative rules: \(\partial u/\partial u=1\), \(\partial c/\partial u=0\), and every other independent variable is constant.]}
\]

\[
\begin{aligned}
\vec r_x
&=\left\langle\frac{\partial x}{\partial x},\frac{\partial y}{\partial x},\frac{\partial(3-x-y/2)}{\partial x}\right\rangle\\
&=\langle1,0,-1\rangle,\\[4pt]
\vec r_y
&=\left\langle\frac{\partial x}{\partial y},\frac{\partial y}{\partial y},\frac{\partial(3-x-y/2)}{\partial y}\right\rangle\\
&=\left\langle0,1,-\frac12\right\rangle.
\end{aligned}
\]

Take their cross product. This is the oriented area vector that replaces \(\hat n\,dS\):

\[
\begin{aligned}
\vec r_x\times\vec r_y
&=\begin{vmatrix}
\hat i&\hat j&\hat k\\
1&0&-1\\
0&1&-\frac12
\end{vmatrix}\\
&=\left[0\left(-\frac12\right)-(-1)(1)\right]\hat i
-\left[1\left(-\frac12\right)-(-1)(0)\right]\hat j
+\left[1(1)-0(0)\right]\hat k\\
&=\left[0+1\right]\hat i
-\left[-\frac12-0\right]\hat j
+\left[1-0\right]\hat k\\
&=\hat i+\frac12\hat j+\hat k.
\end{aligned}
\]

Its \(\hat k\)-component is positive, so this is the **upward** orientation. The question does not state an orientation. We use the standard upward choice; choosing the opposite normal changes only the sign of the final answer.

Use the parameterized-surface formula:

\[
\iint_S(\nabla\times\vec F)\cdot\hat n\,dS
=\int_0^1\int_0^2(\nabla\times\vec F)\cdot(\vec r_x\times\vec r_y)\,dy\,dx.
\]

Calculate the dot product one component at a time:

\[
\begin{aligned}
(\nabla\times\vec F)\cdot(\vec r_x\times\vec r_y)
&=\left\langle3,-1,-2\right\rangle\cdot\left\langle1,\frac12,1\right\rangle\\
&=3(1)+(-1)\left(\frac12\right)+(-2)(1)\\
&=3-\frac12-2\\
&=1-\frac12\\
&=\frac12.
\end{aligned}
\]

Substitute this constant integrand and evaluate both limits:

\[
\begin{aligned}
\iint_S(\nabla\times\vec F)\cdot\hat n\,dS
&=\int_0^1\int_0^2\frac12\,dy\,dx\\
&=\int_0^1\left[\frac12y\right]_{y=0}^{y=2}\,dx
&&\text{[Constant rule: \(\int c\,dy=cy+C\)]}\\
&=\int_0^1\left[\frac12(2)-\frac12(0)\right]dx\\
&=\int_0^1 1\,dx\\
&=\left[x\right]_{x=0}^{x=1}\\
&=1-0\\
&=1.
\end{aligned}
\]

\[
\boxed{\iint_S(\nabla\times\vec F)\cdot\hat n\,dS=1\quad\text{for the upward orientation}.}
\]

With the downward orientation, \(\vec r_y\times\vec r_x=-(\vec r_x\times\vec r_y)\), so the answer would be \(-1\).

---

## Q2(b): Triple integral of curl over a solid

**Question.** If \(\vec F=(2x^2-3z)\hat i-2xy\hat j-4x\hat k\), then evaluate \(\iiint_V(\nabla\times\vec F)dV\) where \(V\) is the closed region bounded by \(x=0,y=0,z=0,2x+2y+z=4\).

### Underlying-concept map

1. **Curl:** calculate a vector with three components.
2. **Closed region:** the three coordinate planes keep the solid in the first octant; the fourth plane is its sloping roof.
3. **Bounds:** solve the roof for \(z\), then project the solid onto the \(xy\)-plane to get the bounds for \(x\) and \(y\).
4. **Vector triple integral:** integrate each curl component over exactly the same solid, then combine the three results into one vector.

### Solve it yourself

1. Identify \(P=2x^2-3z\), \(Q=-2xy\), and \(R=-4x\), then find curl.
2. Write the roof as \(z=4-2x-2y\).
3. Require this upper bound to be non-negative. Derive the triangular condition on \(x\) and \(y\).
4. Use the order \(dz\,dy\,dx\).
5. Integrate the \(\hat i\)-, \(\hat j\)-, and \(\hat k\)-components separately. Do not turn a vector integral into one scalar integral.

### Detailed solution

Write the field as \(\vec F=P\hat i+Q\hat j+R\hat k\):

\[
P=2x^2-3z,\qquad Q=-2xy,\qquad R=-4x.
\]

Use the curl formula:

\[
\nabla\times\vec F=
\left(\frac{\partial R}{\partial y}-\frac{\partial Q}{\partial z}\right)\hat i
+\left(\frac{\partial P}{\partial z}-\frac{\partial R}{\partial x}\right)\hat j
+\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)\hat k.
\]

For the partial derivatives below, hold every variable other than the denominator variable constant. Thus, for example, \(\partial(-2xy)/\partial x=-2y\) because \(y\) is constant with respect to \(x\).

Calculate every component:

\[
\begin{aligned}
\frac{\partial R}{\partial y}-\frac{\partial Q}{\partial z}
&=\frac{\partial(-4x)}{\partial y}-\frac{\partial(-2xy)}{\partial z}\\
&=0-0\\
&=0,\\[4pt]
\frac{\partial P}{\partial z}-\frac{\partial R}{\partial x}
&=\frac{\partial(2x^2-3z)}{\partial z}-\frac{\partial(-4x)}{\partial x}\\
&=-3-(-4)\\
&=1,\\[4pt]
\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}
&=\frac{\partial(-2xy)}{\partial x}-\frac{\partial(2x^2-3z)}{\partial y}\\
&=-2y-0\\
&=-2y.
\end{aligned}
\]

Thus

\[
\nabla\times\vec F=0\hat i+\hat j-2y\hat k.
\]

Next, derive the limits of the solid. The sloping boundary is

\[
\begin{aligned}
2x+2y+z&=4,\\
z&=4-2x-2y.
\end{aligned}
\]

The bottom boundary is \(z=0\), so for each allowed \((x,y)\),

\[
0\le z\le4-2x-2y.
\]

For the upper limit to lie above the bottom limit,

\[
\begin{aligned}
4-2x-2y&\ge0,\\
4&\ge2x+2y,\\
2&\ge x+y,\\
y&\le2-x.
\end{aligned}
\]

The planes \(x=0\) and \(y=0\) give \(x\ge0\) and \(y\ge0\). The largest possible \(x\) occurs when \(y=0\) on \(x+y=2\), giving \(x=2\). Therefore the complete limits are

\[
0\le x\le2,\qquad 0\le y\le2-x,\qquad 0\le z\le4-2x-2y.
\]

Because the integrand is a vector, integrate its components separately:

\[
\iiint_V(\nabla\times\vec F)\,dV
=\left\langle I_x,I_y,I_z\right\rangle.
\]

The \(\hat i\)-component is

\[
\begin{aligned}
I_x
&=\int_0^2\int_0^{2-x}\int_0^{4-2x-2y}0\,dz\,dy\,dx\\
&=0.
\end{aligned}
\]

The \(\hat j\)-component is

\[
\begin{aligned}
I_y
&=\int_0^2\int_0^{2-x}\int_0^{4-2x-2y}1\,dz\,dy\,dx\\
&=\int_0^2\int_0^{2-x}\left[z\right]_{z=0}^{z=4-2x-2y}\,dy\,dx
&&\text{[Constant rule: \(\int1\,dz=z+C\)]}\\
&=\int_0^2\int_0^{2-x}\left[(4-2x-2y)-0\right]dy\,dx\\
&=\int_0^2\int_0^{2-x}(4-2x-2y)\,dy\,dx\\
&=\int_0^2\left[(4-2x)y-y^2\right]_{y=0}^{y=2-x}\,dx
&&\text{[Power rule: \(\int y^n\,dy=y^{n+1}/(n+1)+C\), \(n\ne-1\)]}\\
&=\int_0^2\left[(4-2x)(2-x)-(2-x)^2-0\right]dx\\
&=\int_0^2\left[2(2-x)(2-x)-(2-x)^2\right]dx\\
&=\int_0^2\left[2(2-x)^2-(2-x)^2\right]dx\\
&=\int_0^2(2-x)^2\,dx\\
&=\int_0^2(4-4x+x^2)\,dx\\
&=\left[4x-2x^2+\frac{x^3}{3}\right]_{x=0}^{x=2}
&&\text{[Power rule: \(\int x^n\,dx=x^{n+1}/(n+1)+C\), \(n\ne-1\)]}\\
&=\left[4(2)-2(2)^2+\frac{(2)^3}{3}\right]-\left[4(0)-2(0)^2+\frac{(0)^3}{3}\right]\\
&=\left[8-8+\frac83\right]-0\\
&=\frac83.
\end{aligned}
\]

The \(\hat k\)-component is

\[
\begin{aligned}
I_z
&=\int_0^2\int_0^{2-x}\int_0^{4-2x-2y}(-2y)\,dz\,dy\,dx\\
&=\int_0^2\int_0^{2-x}\left[-2yz\right]_{z=0}^{z=4-2x-2y}\,dy\,dx
&&\text{[Constant-multiple rule: \(\int c\,dz=cz+C\) when \(c\) is constant with respect to \(z\)]}\\
&=\int_0^2\int_0^{2-x}\left[-2y(4-2x-2y)-(-2y)(0)\right]dy\,dx\\
&=\int_0^2\int_0^{2-x}\left[-2y(4-2x-2y)\right]dy\,dx\\
&=\int_0^2\int_0^{2-x}\left[-8y+4xy+4y^2\right]dy\,dx\\
&=\int_0^2\left[-4y^2+2xy^2+\frac{4y^3}{3}\right]_{y=0}^{y=2-x}dx
&&\text{[Power rule: \(\int y^n\,dy=y^{n+1}/(n+1)+C\), \(n\ne-1\)]}\\
&=\int_0^2\left[-4(2-x)^2+2x(2-x)^2+\frac{4(2-x)^3}{3}\right]dx\\
&=\int_0^2\left[(-4+2x)(2-x)^2+\frac{4(2-x)^3}{3}\right]dx\\
&=\int_0^2\left[-2(2-x)(2-x)^2+\frac{4(2-x)^3}{3}\right]dx\\
&=\int_0^2\left[-2(2-x)^3+\frac{4(2-x)^3}{3}\right]dx\\
&=\int_0^2\left[-\frac{6(2-x)^3}{3}+\frac{4(2-x)^3}{3}\right]dx\\
&=\int_0^2\left[-\frac{2(2-x)^3}{3}\right]dx\\
&=-\frac23\int_0^2(2-x)^3\,dx\\
&=-\frac23\int_0^2(8-12x+6x^2-x^3)\,dx\\
&=-\frac23\left[8x-6x^2+2x^3-\frac{x^4}{4}\right]_{x=0}^{x=2}
&&\text{[Power rule: \(\int x^n\,dx=x^{n+1}/(n+1)+C\), \(n\ne-1\)]}\\
&=-\frac23\left(\left[8(2)-6(2)^2+2(2)^3-\frac{(2)^4}{4}\right]-0\right)\\
&=-\frac23\left(16-24+16-4\right)\\
&=-\frac23(4)\\
&=-\frac83.
\end{aligned}
\]

Assemble the three components:

\[
\boxed{\iiint_V(\nabla\times\vec F)\,dV
=\left\langle0,\frac83,-\frac83\right\rangle.}
\]

### Final checks

- The first component of curl is zero everywhere, so its integrated first component must be zero.
- The \(\hat j\)-integrand is positive one throughout the solid, so the second component must be positive.
- The \(\hat k\)-integrand is \(-2y\). Since \(y\ge0\) throughout the solid, the third component must be non-positive. The negative result has the correct sign.
