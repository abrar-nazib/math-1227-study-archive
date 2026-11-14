# MAH page 16: constant-length vectors and the Frenet frame

Page 16 has two connected ideas: first, how a vector can change while its length stays fixed; second, how three unit arrows turn as we travel along a curve. The second part uses the first result. For the earlier background, see [vector-valued curves, tangents, and curvature](../../concepts/vector-valued-curves-tangent-and-curvature.md) and [vectors and planes](../../concepts/vectors-and-planes.md).

## 1. How can a constant-length vector change?

Imagine the hand of a clock. Its length stays the same, but it turns, so the arrow itself changes. At any instant its tip is moving along a circle, sideways relative to the hand. A change pointing directly outward or inward would instead increase or decrease its length at that instant.

Let \(\vec A(t)\) be a differentiable vector depending on time \(t\). Its derivative \(d\vec A/dt\) describes how that vector changes. The question says its magnitude is constant and asks us to prove that the vector and its derivative are perpendicular, assuming the derivative is nonzero. That assumption also guarantees \(\vec A\ne\vec0\): a vector whose constant magnitude is zero is always zero and has zero derivative.

### Why start with a dot product?

For any vector, its dot product with itself is its squared length:

\[
\vec A\cdot\vec A=|\vec A|^2.
\]

Since its length is constant, its squared length is also constant. Differentiate both sides with respect to \(t\). The rule being used is the **dot-product product rule**:

\[
\frac{d}{dt}(\vec u\cdot\vec v)
=\frac{d\vec u}{dt}\cdot\vec v+\vec u\cdot\frac{d\vec v}{dt},
\qquad \frac{d}{dt}(\text{constant})=0.
\]

There are two terms because *both* occurrences of \(\vec A\) change with time:

\[
\begin{aligned}
\frac{d}{dt}(\vec A\cdot\vec A)&=\frac{d}{dt}(|\vec A|^2),\\
\frac{d\vec A}{dt}\cdot\vec A+\vec A\cdot\frac{d\vec A}{dt}&=0,\\
\vec A\cdot\frac{d\vec A}{dt}+\vec A\cdot\frac{d\vec A}{dt}&=0,\\
2\vec A\cdot\frac{d\vec A}{dt}&=0,\\
\vec A\cdot\frac{d\vec A}{dt}&=0.
\end{aligned}
\]

In the third line we used commutativity of the dot product: \(\vec u\cdot\vec v=\vec v\cdot\vec u\). Since both vectors are nonzero, a zero dot product means their angle is 90°. This proves the statement.

### Check it with a rotating arrow

Take \(\vec A(t)=(\cos t,\sin t,0)\). Its length is always one because \(\cos^2t+\sin^2t=1\). Differentiate each component, using \(d(\cos t)/dt=-\sin t\) and \(d(\sin t)/dt=\cos t\):

\[
\frac{d\vec A}{dt}=(-\sin t,\cos t,0).
\]

Now calculate the dot product explicitly:

\[
\begin{aligned}
\vec A\cdot\frac{d\vec A}{dt}
&=(\cos t)(-\sin t)+(\sin t)(\cos t)+(0)(0)\\
&=-\cos t\sin t+\sin t\cos t\\
&=0.
\end{aligned}
\]

At \(t=0\), the arrow points right while its instantaneous change points up. The arrow rotates without growing.

## 2. The three moving arrows on a curve

Imagine travelling along a smooth winding road, carrying a tiny three-arrow coordinate frame that moves and turns with you:

- \(\vec T\), the **unit tangent**, points in your instantaneous forward direction.
- \(\vec N\), the **principal unit normal**, points toward the direction in which \(\vec T\) is turning. It is perpendicular to \(\vec T\).
- \(\vec B\), the **unit binormal**, is \(\vec T\times\vec N\). It is perpendicular to both of the other arrows.

These arrows have length one, and the three directions are mutually perpendicular. They change *direction* as you move, but never change length. The symbols here are a moving frame, not fixed coordinate axes.

The variable \(s\) is **arc length**: the distance travelled along the curve, measured from a chosen starting point. For a small movement, \(\Delta s\) is the short length along the road. Thus \(d\vec T/ds\) describes the change in forward direction **per unit distance**, not per unit time. If \(t\) is time and the speed is nonzero, the chain rule gives \(d\vec T/ds=(d\vec T/dt)/(ds/dt)\).

We assume a sufficiently smooth regular curve, and positive curvature on the portion considered. A regular curve has nonzero velocity; positive curvature ensures that the principal normal and hence this Frenet frame are defined. A straight line has zero curvature, and the principal normal is not uniquely determined there.

## 3. Why does the first Frenet–Serret formula work?

Since \(\vec T\) is a unit vector,

\[
\vec T\cdot\vec T=|\vec T|^2=1.
\]

Differentiate with respect to \(s\), applying the same dot-product rule above, with \(s\) in place of \(t\), and \(d(1)/ds=0\):

\[
\begin{aligned}
\frac{d}{ds}(\vec T\cdot\vec T)&=\frac{d}{ds}(1),\\
\frac{d\vec T}{ds}\cdot\vec T+\vec T\cdot\frac{d\vec T}{ds}&=0,\\
2\vec T\cdot\frac{d\vec T}{ds}&=0,\\
\vec T\cdot\frac{d\vec T}{ds}&=0.
\end{aligned}
\]

Thus the change in the tangent points sideways relative to the tangent. But a direction perpendicular to \(\vec T\) could point anywhere in the plane perpendicular to it; why specifically \(\vec N\)? **Because we define** the principal normal to point in the direction of this change:

\[
\kappa=\left|\frac{d\vec T}{ds}\right|,\qquad
\vec N=\frac{d\vec T/ds}{|d\vec T/ds|}\quad(\kappa>0).
\]

Here \(\kappa\), called **curvature**, is how fast the forward direction changes per unit distance. Multiply the definition of \(\vec N\) by \(\kappa\):

\[
\boxed{\frac{d\vec T}{ds}=\kappa\vec N.}
\]

This is the first formula on page 16. A large curvature means a sharper turn. The radius of curvature is \(\rho=1/\kappa\) when \(\kappa>0\): a tight circle has a small radius and high curvature.

### Example: a circle

For a circle of radius \(R>0\), let \(\theta=s/R\), and write

\[
\vec T=(-\sin\theta,\cos\theta,0),\qquad
\vec N=(-\cos\theta,-\sin\theta,0).
\]

The normal points toward the circle's centre. Use the chain rule \(d[f(\theta)]/ds=f'(\theta)\,d\theta/ds\), together with \(d\theta/ds=1/R\), \(d(\sin\theta)/d\theta=\cos\theta\), and \(d(\cos\theta)/d\theta=-\sin\theta\):

\[
\begin{aligned}
\frac{d\vec T}{ds}
&=\left(-\cos\theta\frac1R,-\sin\theta\frac1R,0\right)\\
&=\frac1R(-\cos\theta,-\sin\theta,0)\\
&=\frac1R\vec N.
\end{aligned}
\]

So \(\kappa=1/R\): a smaller circle requires a sharper turn per metre travelled.

## 4. What do the other two formulas say?

With the standard choice \(\vec B=\vec T\times\vec N\), the three Frenet–Serret formulas are

\[
\boxed{\frac{d\vec T}{ds}=\kappa\vec N,\qquad
\frac{d\vec B}{ds}=-\tau\vec N,\qquad
\frac{d\vec N}{ds}=-\kappa\vec T+\tau\vec B.}
\]

The letter \(\tau\) (tau) is **torsion**, a signed measure of how the curve's bending plane twists as you travel. The second formula says the binormal turns in the normal direction, with sign controlled by torsion. The third says the normal can turn toward the tangent and binormal, with the displayed coefficients. These formulas use the stated cross-product order and torsion convention; reversing the definition of the binormal changes the corresponding signs.

For a circle in a fixed flat plane, \(\vec B\) is a fixed arrow perpendicular to that plane. Therefore \(d\vec B/ds=\vec0\) and \(\tau=0\): the bending plane does not twist. For a helix, like a spring, the bending plane changes as you travel, so torsion need not be zero. Curvature describes turning; torsion describes twisting out of the local bending plane.

Page 16 proves only the first of the three formulas. The next pages develop the remaining formulas; the boxed list on page 16 states them in advance.
