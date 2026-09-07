# Polar coordinates for circular regions

Use this note whenever a surface projects onto a disk, a circle, or an annulus in the \(xy\)-plane. It is the missing link for 2023 Q3(b).

## 1. Why replace \(x,y\) with \(r,\theta\)?

Cartesian coordinates describe a point by horizontal and vertical movement. A disk has a curved boundary in those coordinates, so its limits are awkward. Polar coordinates instead describe a point by its distance from the origin and its turning angle:

> [!IMPORTANT]
> **Exam conversion — polar coordinates**
>
> \[
> x=r\cos\theta,\qquad y=r\sin\theta,\qquad x^2+y^2=r^2.
> \]

Imagine standing at the centre of a circular field. Choose a direction \(\theta\), then walk outward distance \(r\). That reaches one point. To visit every point in a disk of radius \(a\), turn all the way around and walk from the centre to the edge:

> [!IMPORTANT]
> **Exam bounds — full disk of radius \(a\)**
>
> \[
> 0\le\theta\le2\pi,\qquad0\le r\le a.
> \]

## 2. The small-area factor \(r\)

In polar coordinates, one tiny patch is not a rectangle of area \(dr\,d\theta\). At distance \(r\), a tiny angle \(d\theta\) sweeps an arc of length \(r\,d\theta\). The tiny patch has radial width \(dr\), so its area is

> [!IMPORTANT]
> **Exam formula — polar area element**
>
> \[
> dA=r\,dr\,d\theta.
> \]

Forgetting this extra \(r\) is the most common polar-coordinate error.

### Tiny check: area of a radius-2 disk

\[
\iint_D1\,dA
=\int_0^{2\pi}\int_0^2r\,dr\,d\theta.
\]

\[
=\int_0^{2\pi}\left[\frac{r^2}{2}\right]_0^2d\theta
=\int_0^{2\pi}2\,d\theta
=4\pi.
\]

That is the familiar area \(\pi(2)^2=4\pi\), confirming the bounds and area element.

## 3. Orientation of a circular boundary

The usual parameterization \(x=a\cos\theta,\ y=a\sin\theta\), with \(\theta\) increasing from 0 to \(2\pi\), traces the circle counter-clockwise when viewed from positive \(z\). For a clockwise route viewed from positive \(z\), use

\[
x=a\cos\theta,\qquad y=-a\sin\theta,\qquad0\le\theta\le2\pi.
\]

By the right-hand rule, clockwise viewed from above is compatible with a downward normal, \(-\hat k\). This matters in Stokes’ theorem.
