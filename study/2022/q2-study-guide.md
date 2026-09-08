# Math 1227 — 2022 Q2 study guide

Read [Line integrals](../concepts/line-integrals.md) for part (a), and [Curl, surface integrals, and volume integrals](../concepts/curl-surface-and-volume-integrals.md#A-scalar-field-times-a-surface-normal) for part (b).

## Q2(a) Line integral along two straight pieces

> If \(\vec F=(2x+y)\hat i+(3y-x)\hat j\), then evaluate \(\int_C\vec F\cdot d\vec r\) where \(C\) is the curve in the \(xy\) plane consisting of the straight lines from \((0,0)\) to \((2,0)\) and then to \((3,2)\).

The path has two pieces, so add two line integrals.

For \(C_1:(0,0)\to(2,0)\), use

\[
\vec r_1(t)=\langle t,0\rangle,\qquad0\le t\le2.
\]

\[
d\vec r_1=\langle1,0\rangle dt.
\]

\(\vec F\) is a rule that expects a point \((x,y)\) and returns a vector:

\[
\vec F(x,y)=\langle2x+y,\ 3y-x\rangle.
\]

The path \(\vec r_1(t)=\langle t,0\rangle\) tells us that, at time \(t\),

\[
x=t,
\]

\[
y=0.
\]

The notation \(\vec F(\vec r_1(t))\) means: put these path coordinates into the two slots of \(\vec F(x,y)\). Do this component by component:

\[
\vec F(\vec r_1(t))
=\langle2x+y,\ 3y-x\rangle.
\]

\[
=\langle2(t)+0,\ 3(0)-t\rangle.
\]

\[
=\langle2t+0,\ 0-t\rangle.
\]

\[
=\langle2t,-t\rangle.
\]

\[
\vec F(\vec r_1(t))=\langle2t,-t\rangle.
\]

\(d\vec r_1=\langle1,0\rangle dt\) says that this first piece moves only horizontally: its \(x\)-change is \(dt\), and its \(y\)-change is \(0\). Now take the dot product one component at a time:

\[
\vec F\cdot d\vec r_1
=\left[(2t)(1)+(-t)(0)\right]dt.
\]

\[
=\left[2t+0\right]dt.
\]

\[
=2t\,dt.
\]

[Power rule: \(\int t^n\,dt=t^{n+1}/(n+1)+C\).]

\[
\int_{C_1}\vec F\cdot d\vec r=\int_0^2 2t\,dt=[t^2]_0^2=4.
\]

For \(C_2:(2,0)\to(3,2)\), use

\[
\vec r_2(t)=\langle2+t,2t\rangle,\qquad0\le t\le1.
\]

This is not a formula to memorize blindly. Start at

\[
\langle2,0\rangle.
\]

To reach \(\langle3,2\rangle\), the required change is

\[
\langle3,2\rangle-\langle2,0\rangle
=\langle3-2,2-0\rangle
=\langle1,2\rangle.
\]

Multiply that whole movement by \(t\), then add it to the start:

\[
\vec r_2(t)=\langle2,0\rangle+t\langle1,2\rangle.
\]

\[
=\langle2,0\rangle+\langle t,2t\rangle.
\]

\[
=\langle2+t,2t\rangle.
\]

At \(t=0\), it gives the starting point:

\[
\vec r_2(0)=\langle2+0,2(0)\rangle=\langle2,0\rangle.
\]

At \(t=1\), it gives the ending point:

\[
\vec r_2(1)=\langle2+1,2(1)\rangle=\langle3,2\rangle.
\]

Every value between \(0\) and \(1\) gives a point between them, so this traces exactly the required straight piece.

\[
d\vec r_2=\langle1,2\rangle dt.
\]

\[
\vec F(\vec r_2(t))
=\langle2(2+t)+2t,\ 3(2t)-(2+t)\rangle
=\langle4+4t,5t-2\rangle.
\]

\[
\vec F\cdot d\vec r_2
=(4+4t)(1)+(5t-2)(2).
\]

\[
=4+4t+10t-4=14t.
\]

\[
\int_{C_2}\vec F\cdot d\vec r=\int_0^1 14t\,dt=[7t^2]_0^1=7.
\]

\[
\boxed{\int_C\vec F\cdot d\vec r=4+7=11.}
\]

## Q2(b) Scalar-weighted oriented integral on a cylinder

> Evaluate \(\iint_S\phi\hat n\,dS\) where \(\phi=\frac{3}{8}xyz\) and \(S\) is the surface of the cylinder \(x^2+y^2=16\) included in the first octant between \(z=0\) and \(z=5\).

The first-octant cylindrical patch has \(0\le\theta\le\pi/2\), \(0\le z\le5\). Use the outward parameterization

\[
\vec r(\theta,z)=\langle4\cos\theta,4\sin\theta,z\rangle.
\]

\[
\vec r_\theta=\langle-4\sin\theta,4\cos\theta,0\rangle,
\qquad
\vec r_z=\langle0,0,1\rangle.
\]

\[
\vec r_\theta\times\vec r_z=\langle4\cos\theta,4\sin\theta,0\rangle.
\]

Its horizontal components point away from the \(z\)-axis, so it is outward.

\[
\phi(\vec r)=\frac38(4\cos\theta)(4\sin\theta)z=6z\cos\theta\sin\theta.
\]

\[
\phi(\vec r)(\vec r_\theta\times\vec r_z)
=\langle24z\cos^2\theta\sin\theta,\ 24z\cos\theta\sin^2\theta,\ 0\rangle.
\]

\[
\iint_S\phi\hat n\,dS
=\int_0^5\int_0^{\pi/2}
\langle24z\cos^2\theta\sin\theta,\ 24z\cos\theta\sin^2\theta,\ 0\rangle d\theta\,dz.
\]

[Substitution: with \(u=\cos\theta\), \(du=-\sin\theta\,d\theta\); similarly use \(u=\sin\theta\) for the second component.]

\[
\int_0^{\pi/2}\cos^2\theta\sin\theta\,d\theta
=\int_1^0-u^2\,du
=\left[-\frac{u^3}{3}\right]_1^0=\frac13.
\]

\[
\int_0^{\pi/2}\cos\theta\sin^2\theta\,d\theta
=\int_0^1u^2\,du
=\left[\frac{u^3}{3}\right]_0^1=\frac13.
\]

\[
\int_0^5 24z\left(\frac13\right)dz
=8\int_0^5z\,dz
=8\left[\frac{z^2}{2}\right]_0^5=100.
\]

\[
\boxed{\iint_S\phi\hat n\,dS=\langle100,100,0\rangle.}
\]
