# Math 1227 — 2022 Q3 study guide

## Q3(a) Divergence theorem

> State and prove divergence theorem.

Use [Divergence Theorem and Stokes’ Theorem](../concepts/divergence-and-integral-theorems.md#3-closed-surfaces-and-the-divergence-theorem). It contains the full theorem statement, hypotheses, rectangular-box proof, and the cancellation argument for a general solid. Follow its “2024 Q3 checklist”; the theorem and proof are the same in 2022 Q3(a).

## Q3(b) Verify Green’s theorem

> Verify Green’s theorem in the plane for \(\oint_C(3x^2-8y^2)dx+(4y-6xy)dy\), where \(C\) is the boundary of the region defined by \(y=\sqrt{x}\) and \(y=x^2\).

Write

\[
M=3x^2-8y^2,\qquad N=4y-6xy.
\]

Green’s theorem says

\[
\oint_C Mdx+Ndy=\iint_R(N_x-M_y)\,dA.
\]

The curves meet where \(\sqrt{x}=x^2\), so \(x=0,1\). For \(0\le x\le1\), \(x^2\) is lower and \(\sqrt{x}\) is upper.

\[
N_x=-6y,\qquad M_y=-16y.
\]

\[
N_x-M_y=-6y-(-16y)=10y.
\]

\[
\iint_R10y\,dA=\int_0^1\int_{x^2}^{\sqrt{x}}10y\,dy\,dx.
\]

[Power rule: \(\int y\,dy=y^2/2+C\).]

\[
=\int_0^1[5y^2]_{x^2}^{\sqrt{x}}dx
=\int_0^1(5x-5x^4)dx.
\]

\[
=\left[\frac{5x^2}{2}-x^5\right]_0^1
=\frac52-1=\frac32.
\]

Now calculate the boundary integral counter-clockwise. On the lower curve, go from \((0,0)\) to \((1,1)\):

\[
x=t,\quad y=t^2,\quad0\le t\le1,\quad dx=dt,\quad dy=2t\,dt.
\]

\[
M=3t^2-8t^4,\qquad N=4t^2-6t^3.
\]

\[
Mdx+Ndy=(3t^2-8t^4)dt+(4t^2-6t^3)(2t)dt.
\]

\[
=(3t^2+8t^3-20t^4)dt.
\]

\[
\int_{C_1}=\left[t^3+2t^4-4t^5\right]_0^1=-1.
\]

On the upper curve, travel back from \((1,1)\) to \((0,0)\):

\[
x=t^2,\quad y=t,\quad1\ge t\ge0,\quad dx=2t\,dt,\quad dy=dt.
\]

\[
M=3t^4-8t^2,\qquad N=4t-6t^3.
\]

\[
Mdx+Ndy=(3t^4-8t^2)(2t)dt+(4t-6t^3)dt.
\]

\[
=(6t^5-22t^3+4t)dt.
\]

\[
\int_{C_2}=\left[t^6-\frac{11}{2}t^4+2t^2\right]_1^0=\frac52.
\]

\[
\oint_C Mdx+Ndy=-1+\frac52=\frac32.
\]

\[
\boxed{\oint_C Mdx+Ndy=\frac32=\iint_R(N_x-M_y)dA.}
\]

Thus Green’s theorem is verified.
