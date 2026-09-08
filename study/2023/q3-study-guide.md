# Math 1227 — 2023 Q3 study guide

Read [Curl, surface integrals, and volume integrals](../concepts/curl-surface-and-volume-integrals.md), [Divergence Theorem and Stokes’ Theorem](../concepts/divergence-and-integral-theorems.md), and [Polar coordinates for circular regions](../concepts/polar-coordinates-for-circular-regions.md) before this guide.

## Q3(a) Scalar-weighted oriented surface integral

> Evaluate \(\iint_S\phi\hat n\,dS\) where \(\phi=4x+3y-2z\) and \(S\) is the surface of \(2x+y+2z=6\) bounded by \(x=0,x=1,y=0,y=2\).

### Underlying-concept map

1. The given plane is an infinite sheet; the four \(x,y\) bounds select one rectangular patch.
2. Solve the plane equation for \(z\), using \(x,y\) as the surface parameters.
3. \(\vec r_x\times\vec r_y\) is the upward oriented area vector. It includes both \(\hat n\) and \(dS\).
4. Since \(\phi\) is a scalar, multiply that number by the oriented area vector before integrating.

### Solve it yourself

1. Rewrite the plane as \(z=f(x,y)\), with \(0\le x\le1\), \(0\le y\le2\).
2. Find \(\vec r_x\), \(\vec r_y\), and their cross product.
3. Substitute the plane's value of \(z\) into \(\phi\).
4. Integrate each vector component over the same rectangle.

### Detailed answer

The orientation is not specified. We choose the standard **upward** orientation; reversing the normal would reverse the final vector.

Solve the plane equation for \(z\):

\[
2x+y+2z=6,
\]

\[
2z=6-2x-y,
\]

\[
z=3-x-\frac y2.
\]

The boundaries already give a rectangle in the \(xy\)-plane:

\[
0\le x\le1,\qquad0\le y\le2.
\]

Parameterize the patch:

\[
\vec r(x,y)=\left\langle x,y,3-x-\frac y2\right\rangle.
\]

Differentiate with respect to each parameter:

\[
\vec r_x=\left\langle1,0,-1\right\rangle,
\qquad
\vec r_y=\left\langle0,1,-\frac12\right\rangle.
\]

Their cross product is

\[
\vec r_x\times\vec r_y
=\begin{vmatrix}
\hat i&\hat j&\hat k\\
1&0&-1\\
0&1&-\frac12
\end{vmatrix}.
\]

\[
=\left[0\left(-\frac12\right)-(-1)(1)\right]\hat i
-\left[1\left(-\frac12\right)-(-1)(0)\right]\hat j
+\left[1(1)-0(0)\right]\hat k.
\]

\[
=\left\langle1,\frac12,1\right\rangle.
\]

Its positive \(z\)-component confirms that it is upward. Now substitute the surface height into \(\phi\):

\[
\phi=4x+3y-2z.
\]

\[
\phi\bigl(\vec r(x,y)\bigr)=4x+3y-2\left(3-x-\frac y2\right).
\]

\[
=4x+3y-6+2x+y.
\]

\[
=6x+4y-6.
\]

The surface integral is

\[
\iint_S\phi\hat n\,dS
=\int_0^1\int_0^2(6x+4y-6)\left\langle1,\frac12,1\right\rangle dy\,dx.
\]

The vector factor is constant, so first calculate its scalar multiplier:

\[
I=\int_0^1\int_0^2(6x+4y-6)\,dy\,dx.
\]

For the inner integral, \(x\) is constant. [Power rule for integration: \(\int y^n\,dy=y^{n+1}/(n+1)+C\), for \(n\ne-1\).]

\[
I=\int_0^1\left[6xy+2y^2-6y\right]_{y=0}^{y=2}dx.
\]

\[
=\int_0^1\left[(12x+8-12)-0\right]dx.
\]

\[
=\int_0^1(12x-4)dx.
\]

\[
=\left[6x^2-4x\right]_{x=0}^{x=1}.
\]

\[
=(6-4)-0=2.
\]

Therefore

\[
\iint_S\phi\hat n\,dS
=2\left\langle1,\frac12,1\right\rangle
=\boxed{\left\langle2,1,2\right\rangle}.
\]

With downward orientation, the answer is \(\langle-2,-1,-2\rangle\).

## Q3(b) Verify Stokes’ theorem on a paraboloid

> Verify Stokes theorem for \(\vec A=3y\hat i-xz\hat j+yz^2\hat k\), where \(s\) is the surface of the paraboloid \(2z=x^2+y^2\) bounded by \(z=2\) and \(c\) is its boundary traversed in the clockwise direction.

### Underlying-concept map

1. Stokes’ theorem compares a line integral around the rim with curl flux through any spanning surface.
2. Setting \(z=2\) in the paraboloid gives the circular rim \(x^2+y^2=4\).
3. “Clockwise viewed from above” is compatible with a downward normal. Keep that choice on both sides.
4. Use a clockwise circle parameterization for the line side and polar coordinates for the curved surface side.

### How the clockwise direction determines the downward normal

The rim lies in the horizontal plane \(z=2\). The word “clockwise” needs a viewing side; for this horizontal circle, use the standard convention that it is viewed from the positive-\(z\) side, looking down toward the \(xy\)-plane. In that view, the ordinary circle parameterization

\[
\vec r_{\mathrm{ordinary}}(\theta)
=\langle2\cos\theta,2\sin\theta,2\rangle,
\qquad0\le\theta\le2\pi,
\]

starts at the rightmost point when \(\theta=0\):

\[
\vec r_{\mathrm{ordinary}}(0)=\langle2,0,2\rangle.
\]

At the next familiar angle, \(\theta=\pi/2\), it is at the top of the circle:

\[
\vec r_{\mathrm{ordinary}}\left(\frac{\pi}{2}\right)
=\langle0,2,2\rangle.
\]

So it travels **right \(\to\) top**, which is counter-clockwise when viewed from above. The question instead says clockwise. Reverse the vertical coordinate:

\[
\vec r_{\mathrm{clockwise}}(\theta)
=\langle2\cos\theta,-2\sin\theta,2\rangle.
\]

It still begins at the rightmost point:

\[
\vec r_{\mathrm{clockwise}}(0)
=\langle2,0,2\rangle,
\]

but now, at \(\theta=\pi/2\), it reaches the bottom:

\[
\vec r_{\mathrm{clockwise}}\left(\frac{\pi}{2}\right)
=\langle0,-2,2\rangle.
\]

So it travels **right \(\to\) bottom**, which is clockwise.

Stokes’ theorem requires the boundary direction and surface normal to be a matching pair. Apply the right-hand rule: curl the fingers of your right hand in the direction of travel. With clockwise travel as you look from above, your thumb points downward. Thus the compatible normal points toward negative \(z\):

\[
\hat n\text{ has a negative }z\text{-component}.
\]

For this question, we do **not** calculate that the route is clockwise; the paper gives it. We choose a parameterization that follows the given route, then choose the normal that matches it. A counter-clockwise route viewed from above would instead require an upward normal.

### Solve it yourself

1. Calculate \(\nabla\times\vec A\).
2. Parameterize the boundary circle clockwise and evaluate \(\oint_C\vec A\cdot d\vec r\).
3. Parameterize the paraboloid with polar variables \((r,\theta)\), choosing the downward area vector.
4. Evaluate the curl flux and compare it with the line integral.

### Detailed answer

Stokes’ theorem says

\[
\oint_C\vec A\cdot d\vec r
=\iint_S(\nabla\times\vec A)\cdot\hat n\,dS.
\]

Write

\[
P=3y,\qquad Q=-xz,\qquad R=yz^2.
\]

Calculate curl component by component:

\[
\nabla\times\vec A
=\left(\frac{\partial R}{\partial y}-\frac{\partial Q}{\partial z}\right)\hat i
+\left(\frac{\partial P}{\partial z}-\frac{\partial R}{\partial x}\right)\hat j
+\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)\hat k.
\]

For these partial derivatives, hold the other independent variables fixed. In particular, \(\partial(cy)/\partial y=c\), \(\partial(cz^2)/\partial z=2cz\), and \(\partial x/\partial z=0\) when \(x\) and \(z\) are independent.

\[
\frac{\partial R}{\partial y}-\frac{\partial Q}{\partial z}
=z^2-(-x)=x+z^2.
\]

\[
\frac{\partial P}{\partial z}-\frac{\partial R}{\partial x}=0-0=0.
\]

\[
\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}=-z-3.
\]

Thus

\[
\nabla\times\vec A=(x+z^2)\hat i+0\hat j-(z+3)\hat k.
\]

### Line-integral side

At the rim, \(z=2\), so

\[
x^2+y^2=2z=4.
\]

The boundary is a radius-2 circle in the horizontal plane \(z=2\). For clockwise travel viewed from positive \(z\), use

\[
\vec r(\theta)=\langle2\cos\theta,-2\sin\theta,2\rangle,
\qquad0\le\theta\le2\pi.
\]

Differentiate:

\[
d\vec r=\langle-2\sin\theta,-2\cos\theta,0\rangle d\theta.
\]

On the boundary,

\[
x=2\cos\theta,\qquad y=-2\sin\theta,\qquad z=2.
\]

Substitute into \(\vec A\):

\[
\vec A=\langle3y,-xz,yz^2\rangle.
\]

\[
\vec A\bigl(\vec r(\theta)\bigr)
=\langle3(-2\sin\theta),-(2\cos\theta)(2),(-2\sin\theta)(2^2)\rangle.
\]

\[
=\langle-6\sin\theta,-4\cos\theta,-8\sin\theta\rangle.
\]

Take the dot product:

\[
\vec A\cdot d\vec r
=\langle-6\sin\theta,-4\cos\theta,-8\sin\theta\rangle
\cdot\langle-2\sin\theta,-2\cos\theta,0\rangle d\theta.
\]

\[
=\left[12\sin^2\theta+8\cos^2\theta+0\right]d\theta.
\]

\[
\oint_C\vec A\cdot d\vec r
=\int_0^{2\pi}\left(12\sin^2\theta+8\cos^2\theta\right)d\theta.
\]

The square identities give the two required integrals:

\[
\sin^2\theta=\frac{1-\cos(2\theta)}2,
\qquad
\cos^2\theta=\frac{1+\cos(2\theta)}2.
\]

\[
\int_0^{2\pi}\sin^2\theta\,d\theta
=\int_0^{2\pi}\frac{1-\cos(2\theta)}2\,d\theta.
\]

\[
=\left[\frac\theta2-\frac{\sin(2\theta)}4\right]_0^{2\pi}
=\pi-0=\pi.
\]

\[
\int_0^{2\pi}\cos^2\theta\,d\theta
=\int_0^{2\pi}\frac{1+\cos(2\theta)}2\,d\theta.
\]

\[
=\left[\frac\theta2+\frac{\sin(2\theta)}4\right]_0^{2\pi}
=\pi+0=\pi.
\]

[Integration rules: \(\int1\,d\theta=\theta+C\), and \(\int\cos(2\theta)\,d\theta=\sin(2\theta)/2+C\), by the reverse chain rule.]

\[
\oint_C\vec A\cdot d\vec r=12\pi+8\pi=20\pi.
\]

### Surface-flux side

Use polar parameters on the paraboloid:

\[
\vec r(r,\theta)=\left\langle r\cos\theta,r\sin\theta,\frac{r^2}{2}\right\rangle,
\qquad0\le r\le2,\quad0\le\theta\le2\pi.
\]

The bound \(r\le2\) comes from the rim \(x^2+y^2=4\). The natural cross product is upward, so reverse it for the clockwise boundary:

\[
\vec r_r=\langle\cos\theta,\sin\theta,r\rangle,
\]

\[
\vec r_\theta=\langle-r\sin\theta,r\cos\theta,0\rangle.
\]

\[
\vec r_r\times\vec r_\theta
=\langle-r^2\cos\theta,-r^2\sin\theta,r\rangle.
\]

Its third component is \(r\), and \(0\le r\le2\), so this cross product has a non-negative \(z\)-component: it is the **upward** area vector. But the already-given clockwise boundary requires downward orientation. Therefore reverse the vector; equivalently, use \(\vec r_\theta\times\vec r_r\) instead. Thus the downward oriented area vector is

\[
d\vec S=\langle r^2\cos\theta,r^2\sin\theta,-r\rangle dr\,d\theta.
\]

On the surface,

\[
x=r\cos\theta,\qquad z=\frac{r^2}{2},\qquad z^2=\frac{r^4}{4}.
\]

Hence

\[
(\nabla\times\vec A)\cdot d\vec S
=\left\langle r\cos\theta+\frac{r^4}{4},0,-\frac{r^2}{2}-3\right\rangle
\cdot\langle r^2\cos\theta,r^2\sin\theta,-r\rangle dr\,d\theta.
\]

\[
=\left[r^3\cos^2\theta+\frac{r^6}{4}\cos\theta+\frac{r^3}{2}+3r\right]dr\,d\theta.
\]

Therefore

\[
\iint_S(\nabla\times\vec A)\cdot d\vec S
=\int_0^2\int_0^{2\pi}
\left[r^3\cos^2\theta+\frac{r^6}{4}\cos\theta+\frac{r^3}{2}+3r\right]d\theta\,dr.
\]

The inner limits say to integrate in \(\theta\) first:

\[
\int_0^{2\pi}
\left[r^3\cos^2\theta+\frac{r^6}{4}\cos\theta+\frac{r^3}{2}+3r\right]d\theta
\]

Here \(\int_0^{2\pi}\cos\theta\,d\theta=[\sin\theta]_0^{2\pi}=0\), and the earlier calculation gives \(\int_0^{2\pi}\cos^2\theta\,d\theta=\pi\). Thus

\[
=\pi r^3+0+\frac{r^3}{2}(2\pi)+3r(2\pi).
\]

\[
=\pi r^3+0+\pi r^3+6\pi r.
\]

\[
\iint_S(\nabla\times\vec A)\cdot d\vec S
=\int_0^2\left[\pi r^3+0+\pi r^3+6\pi r\right]dr.
\]

\[
=\int_0^2(2\pi r^3+6\pi r)dr.
\]

[Power rule for integration: \(\int r^n\,dr=r^{n+1}/(n+1)+C\), for \(n\ne-1\).]

\[
=\left[\frac{2\pi r^4}{4}+\frac{6\pi r^2}{2}\right]_{r=0}^{r=2}.
\]

\[
=\left[\frac{\pi r^4}{2}+3\pi r^2\right]_0^2.
\]

\[
=\left(\frac{\pi(2)^4}{2}+3\pi(2)^2\right)-0.
\]

\[
=8\pi+12\pi=20\pi.
\]

Both sides are equal:

\[
\boxed{\oint_C\vec A\cdot d\vec r=20\pi=\iint_S(\nabla\times\vec A)\cdot\hat n\,dS.}
\]

Therefore Stokes’ theorem is verified for the stated clockwise orientation.
