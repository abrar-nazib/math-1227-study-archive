# Vector-valued curves, unit tangents, and curvature

This note is for 2023 Q1(b)–(c). The curve is described by a moving point, not by one ordinary graph.

## 1. A curve as a moving point

A vector-valued curve is written

\[
\vec r(t)=\langle x(t),y(t),z(t)\rangle.
\]

At each value of the parameter \(t\), it gives one point in space. Imagine a tiny aircraft: \(t\) is the clock reading, and \(\vec r(t)\) is its location.

The derivative tells how the location changes:

> [!IMPORTANT]
> **Exam formula — velocity / tangent vector**
>
> \[
> \vec r\,'(t)=\left\langle\frac{dx}{dt},\frac{dy}{dt},\frac{dz}{dt}\right\rangle.
> \]

This is a tangent vector because, for a tiny time change \(dt\), the displacement is approximately \(\vec r\,'(t)dt\), which points along the curve. It does not usually have length \(1\).

## 2. Unit tangent vector

The **unit tangent vector** has the same direction as \(\vec r\,'(t)\), but length exactly \(1\). Divide the tangent vector by its magnitude.

> [!IMPORTANT]
> **Exam formula — unit tangent**
>
> \[
> \vec T(t)=\frac{\vec r\,'(t)}{|\vec r\,'(t)|},\qquad \vec r\,'(t)\ne\vec0.
> \]

For \(\vec v=\langle a,b,c\rangle\), its magnitude is

\[
|\vec v|=\sqrt{a^2+b^2+c^2}.
\]

### Tiny example

If \(\vec r\,'(t_0)=\langle3,4,0\rangle\), then

\[
|\vec r\,'(t_0)|=\sqrt{3^2+4^2+0^2}=5.
\]

So

\[
\vec T(t_0)=\frac{\langle3,4,0\rangle}{5}=\left\langle\frac35,\frac45,0\right\rangle.
\]

Its direction is unchanged, and its length is \(\sqrt{(3/5)^2+(4/5)^2}=1\).

## 3. Curvature: how sharply the path turns

Speed asks “how quickly are we moving?” Curvature asks “how quickly is the direction of motion turning?” A straight path has curvature \(0\); a tight bend has larger curvature. A car steering gently around a wide bend has lower curvature than one taking a tight roundabout.

For a regular space curve, calculate curvature directly from the first two derivatives:

> [!IMPORTANT]
> **Exam formula — curvature of a space curve**
>
> \[
> \kappa(t)=\frac{|\vec r\,'(t)\times\vec r\,''(t)|}{|\vec r\,'(t)|^3},
> \qquad \vec r\,'(t)\ne\vec0.
> \]

Here \(\vec r\,''(t)\) is the second derivative. The cross product measures the part of acceleration that bends the path rather than only speeding up or slowing down along it.

For \(\vec a=\langle a_1,a_2,a_3\rangle\) and \(\vec b=\langle b_1,b_2,b_3\rangle\),

\[
\vec a\times\vec b
=\left\langle
a_2b_3-a_3b_2,\ 
a_3b_1-a_1b_3,\ 
a_1b_2-a_2b_1
\right\rangle.
\]

### Reliable curvature workflow

1. Write \(\vec r(t)\) as one vector.
2. Differentiate once to obtain \(\vec r\,'(t)\), then again to obtain \(\vec r\,''(t)\).
3. Calculate the cross product in all three components.
4. Find its magnitude and the magnitude of \(\vec r\,'(t)\).
5. Substitute into the curvature formula; simplify only after both magnitudes are correct.
