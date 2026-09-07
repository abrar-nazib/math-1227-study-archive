# Math 1227 — 2023 Q2 study guide

Read [Scalar fields, gradients, and potential functions](../concepts/scalar-fields-gradient-and-potential.md), especially “Geometrical interpretation,” for Q2(a). For Q2(b), read [Line integrals of vector fields](../concepts/line-integrals.md) and then the already-complete [2024 Q1(c) walkthrough](../2024/q1-study-guide.md#q1c-line-integral-on-a-quarter-circle).

## Q2(a) Geometrical interpretation of \(\nabla\phi\)

> Write down the geometrical interpretation of \(\nabla\phi\).

### Underlying-concept map

1. \(\phi\) is a scalar field: it assigns one number to each location.
2. \(\phi=c\) describes a level surface, where the number stays unchanged.
3. The gradient is the normal direction to that surface and points toward the fastest increase.

### Answer

At a point where \(\nabla\phi\ne\vec0\), the gradient \(\nabla\phi\):

1. points in the direction in which the scalar field \(\phi\) increases most rapidly;
2. has magnitude \(|\nabla\phi|\), equal to that maximum rate of increase per unit distance; and
3. is perpendicular (normal) to the level surface \(\phi(x,y,z)=c\) passing through that point.

Imagine walking on a hill described by height \(\phi\). Walking along a contour keeps your height unchanged. The gradient points straight uphill, across the contours rather than along them; its length tells how steep the uphill direction is.

## Q2(b) Line integral along the unit circle

> Evaluate \(\int_C\vec A\cdot d\vec r\) along the curve \(x^2+y^2=1,\ z=1\), in the positive direction from \((0,1,1)\) to \((1,0,1)\), if \(\vec A=(yz+zx)\hat i+xz\hat j+(xy+2z)\hat k\).

### Underlying-concept map

This is exactly the same field, circle, starting point, finishing point, and orientation as 2024 Q1(c). Repeating the calculation here would create a duplicate study note, so use the linked walkthrough. Its key decisions are:

1. parameterize the circle by \(x=\cos\theta\), \(y=\sin\theta\), \(z=1\);
2. encode the given journey using \(\theta:\pi/2\to0\);
3. substitute into both the field and the displacement vector; and
4. take the dot product before integrating.

### Answer

Follow the complete calculation in [2024 Q1(c)](../2024/q1-study-guide.md#q1c-line-integral-on-a-quarter-circle). It gives

\[
\boxed{\int_C\vec A\cdot d\vec r=\frac12.}
\]

As a direction check, reversing the path would reverse the answer to \(-\frac12\).
