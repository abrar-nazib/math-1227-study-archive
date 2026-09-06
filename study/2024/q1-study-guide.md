# 2024 Q1 Study Guide

This guide teaches the three ideas tested in 2024 Q1: plane equations, conservative fields and potentials, and vector line integrals. Read the linked concept notes first if a term feels new:

- [Vectors and planes](../concepts/vectors-and-planes.md)
- [Scalar fields, gradients, and potentials](../concepts/scalar-fields-gradient-and-potential.md)
- [Line integrals](../concepts/line-integrals.md)
- [Trigonometric formulas quick reference](../concepts/trigonometric-formulas-reference.md) for Q1(c)

---

## Q1(a): Plane perpendicular to a vector

**Question.** Find an equation for the plane perpendicular to \(\vec A=2\hat i+3\hat j+6\hat k\) and passing through the terminal point of \(\vec B=\hat i+5\hat j+3\hat k\).

### Conceptual walkthrough

The wording gives the two ingredients of a plane immediately:

- “perpendicular to \(\vec A\)” gives the normal vector \(\vec n=\langle2,3,6\rangle\);
- “terminal point of \(\vec B\)” gives a point \(P_0=(1,5,3)\).

Use the point-normal equation \(\vec n\cdot(\vec r-\vec r_0)=0\). Do not try to construct two directions in the plane; they are unnecessary.

### Solve it yourself

1. Write \(2(x-1)+3(y-5)+6(z-3)=0\).
2. Expand carefully.
3. Substitute \((1,5,3)\) into your final equation to check it.

### Detailed solution

The terminal point of \(\vec B=\langle1,5,3\rangle\) is

\[
P_0=(1,5,3).
\]

Since the required plane is perpendicular to \(\vec A\), its normal is

\[
\vec n=\langle2,3,6\rangle.
\]

For a general point \(P(x,y,z)\) on the plane,

\[
\langle2,3,6\rangle\cdot\langle x-1,y-5,z-3\rangle=0.
\]

Thus

\[
2(x-1)+3(y-5)+6(z-3)=0,
\]

or, after expanding,

\[
\boxed{2x+3y+6z-35=0.}
\]

Check: at \((1,5,3)\), \(2+15+18-35=0\), so the plane contains the required point.

---

## Q1(b): Proving a radial field is conservative

**Question.** Show that \(\vec E=\vec r/r^2\) is conservative. Find \(\phi\) such that \(\vec E=-\nabla\phi\) and \(\phi(a)=0\), where \(a>0\).

### Conceptual walkthrough

Here \(r=\sqrt{x^2+y^2+z^2}\). The pattern \(\vec r/r^2\) should suggest \(\nabla(\ln r)\), because differentiating \(\ln r\) produces a factor \(1/r\), and \(\nabla r=\vec r/r\). The question uses the physics sign convention \(\vec E=-\nabla\phi\), so the potential will be negative \(\ln r\), plus a constant fixed by \(\phi(a)=0\).

### Solve it yourself

1. Verify \(\nabla(\ln r)=\vec r/r^2\).
2. From \(-\nabla\phi=\nabla(\ln r)\), write \(\phi=-\ln r+C\).
3. Set \(r=a\) and use \(\phi(a)=0\) to find \(C\).
4. State where the answer is valid.

### Detailed solution

Let

\[
r=\sqrt{x^2+y^2+z^2},\qquad \vec r=x\hat i+y\hat j+z\hat k.
\]

Using the chain rule,

\[
\nabla(\ln r)=\frac1r\nabla r
=\frac1r\left(\frac{x}{r}\hat i+\frac{y}{r}\hat j+\frac{z}{r}\hat k\right)
=\frac{x\hat i+y\hat j+z\hat k}{r^2}
=\frac{\vec r}{r^2}.
\]

Therefore

\[
\vec E=\nabla(\ln r),
\]

so \(\vec E\) is conservative for \(r>0\). We need \(\vec E=-\nabla\phi\), hence

\[
\phi=-\ln r+C.
\]

Apply \(\phi(a)=0\):

\[
0=-\ln a+C \quad\Rightarrow\quad C=\ln a.
\]

Thus

\[
\boxed{\phi=\ln\left(\frac{a}{r}\right)}
\qquad (r>0).
\]

Differentiating gives \(-\nabla\phi=\vec r/r^2=\vec E\), which checks the sign.

---

## Q1(c): Line integral on a quarter circle

**Question.** Evaluate \(\int_C\vec A\cdot d\vec r\) along \(x^2+y^2=1, z=1\), from \((0,1,1)\) to \((1,0,1)\), where \(\vec A=(yz+zx)\hat i+xz\hat j+(xy+2z)\hat k\).

### Conceptual walkthrough

The path is a unit circle at height \(z=1\). The endpoints determine the direction: use \(\theta=\pi/2\) at the start and \(\theta=0\) at the finish. This is clockwise when viewed from positive \(z\). Since \(z\) remains 1, \(dz=0\), so the \(\hat k\)-component of the field contributes nothing.

### Solve it yourself

1. Take \(x=\cos\theta, y=\sin\theta,z=1\), \(\pi/2\ge\theta\ge0\).
2. Write \(dx=-\sin\theta\,d\theta\), \(dy=\cos\theta\,d\theta\), \(dz=0\).
3. On the curve, simplify \(P=yz+zx\) and \(Q=xz\).
4. Integrate \(P\,dx+Q\,dy\) from \(\pi/2\) to 0.

### Detailed solution

Parameterize the path as

\[
\vec r(\theta)=\cos\theta\,\hat i+\sin\theta\,\hat j+\hat k,
\qquad \frac\pi2\ge\theta\ge0.
\]

Then

\[
d\vec r=(-\sin\theta\,\hat i+\cos\theta\,\hat j)\,d\theta.
\]

This comes from differentiating the three coordinates of the moving point. In particular, \(d(\cos\theta)/d\theta=-\sin\theta\), \(d(\sin\theta)/d\theta=\cos\theta\), and \(d(1)/d\theta=0\). The final zero means the particle never moves upward or downward.

Along the curve, \(x=\cos\theta\), \(y=\sin\theta\), and \(z=1\), so

\[
\vec A=(\sin\theta+\cos\theta)\hat i+\cos\theta\hat j+
(\sin\theta\cos\theta+2)\hat k.
\]

Here is exactly what happened. The original field is a rule that requires a location \((x,y,z)\). But our particle is no longer at one fixed location: at each value of \(\theta\), it is at \((\cos\theta,\sin\theta,1)\). So we replace every \(x,y,z\) in **each component** of the field:

\[
\begin{aligned}
yz+zx
&=(\sin\theta)(1)+(1)(\cos\theta)
=\sin\theta+\cos\theta,\\
xz&=(\cos\theta)(1)=\cos\theta,\\
xy+2z
&=(\cos\theta)(\sin\theta)+2(1)
=\sin\theta\cos\theta+2.
\end{aligned}
\]

After this substitution, \(\vec A\) is no longer written in terms of three changing coordinates. It is written in terms of the one parameter \(\theta\), just like the path. This is the key simplification: now the whole problem is an ordinary one-variable integral.

Now calculate the dot product one component at a time. The \(\hat k\) term disappears because the path has no vertical motion: its matching component in \(d\vec r\) is \(0\).

\[
\begin{aligned}
\vec A\cdot d\vec r
&=\Big[(\sin\theta+\cos\theta)\hat i+\cos\theta\hat j+(\sin\theta\cos\theta+2)\hat k\Big]\\
&\quad\cdot\Big[(-\sin\theta)\hat i+(\cos\theta)\hat j+0\hat k\Big]d\theta\\
&=(\sin\theta+\cos\theta)(-\sin\theta)d\theta+(\cos\theta)(\cos\theta)d\theta\\
&\quad+(\sin\theta\cos\theta+2)(0)d\theta\\
&=\Big[-\sin^2\theta-\sin\theta\cos\theta+\cos^2\theta+0\Big]d\theta\\
&=\Big[\cos^2\theta-\sin^2\theta-\sin\theta\cos\theta\Big]d\theta.
\end{aligned}
\]

Put this result into the line integral.

\[
\begin{aligned}
\int_C\vec A\cdot d\vec r
&=\int_{\pi/2}^{0}\left(\cos^2\theta-\sin^2\theta-\sin\theta\cos\theta\right)d\theta\\
&=\int_{\pi/2}^{0}\left(\cos2\theta-\frac12\sin2\theta\right)d\theta
&&\text{[Identities: \(\cos^2\theta-\sin^2\theta=\cos2\theta\), \(\sin\theta\cos\theta=\frac12\sin2\theta\)]}\\
&=\left[\frac12\sin2\theta+\frac14\cos2\theta\right]_{\pi/2}^{0}
&&\text{[Formulas: \(\int\cos2\theta\,d\theta=\frac12\sin2\theta\), \(\int\sin2\theta\,d\theta=-\frac12\cos2\theta\)]}\\
&=\left[\frac12\sin0+\frac14\cos0\right]-\left[\frac12\sin\pi+\frac14\cos\pi\right]\\
&=\left[\frac12(0)+\frac14(1)\right]-\left[\frac12(0)+\frac14(-1)\right]\\
&=\frac14-\left(-\frac14\right)\\
&=\frac12.
\end{aligned}
\]

Hence

\[
\boxed{\int_C\vec A\cdot d\vec r=\frac12.}
\]

If the path were traversed in the reverse direction, the answer would be \(-1/2\). That sign change is the most useful final check.
