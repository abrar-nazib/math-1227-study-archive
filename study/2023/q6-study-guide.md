# Math 1227 — 2023 Q6 study guide

Read [Differential equations: the ground floor](../concepts/differential-equations-foundations.md) and [First-order ODEs](../concepts/first-order-odes-exact-integrating-factors-and-substitutions.md) first.

## Q6(a) Exact differential equation

> Define exact differential equation. Test whether \((x+y)^2dx-(y^2-2xy-x^2)dy=0\) is exact and hence solve it.

### Underlying-concept map

1. Write the equation as \(Mdx+Ndy=0\).
2. The class-note test is \(M_y=N_x\).
3. If exact, find one potential function \(\Phi\) with \(\Phi_x=M,\ \Phi_y=N\).

### Detailed answer

Following the class notes, an equation

\[
M(x,y)dx+N(x,y)dy=0
\]

is **exact** when there exists a function \(\Phi(x,y)\) such that

\[
d\Phi=Mdx+Ndy.
\]

Thus \(M=\Phi_x,\ N=\Phi_y\). The class-note test is

\[
\frac{\partial M}{\partial y}=\frac{\partial N}{\partial x}.
\]

Here

\[
M=(x+y)^2,
\]

\[
N=-(y^2-2xy-x^2)=x^2+2xy-y^2.
\]

\[
M=x^2+2xy+y^2.
\]

Holding \(x\) constant,

\[
M_y=\frac{\partial}{\partial y}(x^2+2xy+y^2)=0+2x+2y=2x+2y.
\]

Holding \(y\) constant,

\[
N_x=\frac{\partial}{\partial x}(x^2+2xy-y^2)=2x+2y+0=2x+2y.
\]

Therefore \(M_y=N_x\), so the equation is exact.

Find \(\Phi\) from \(\Phi_x=M\):

\[
\Phi=\int(x^2+2xy+y^2)\,dx+g(y).
\]

[Power rule: \(\int x^n\,dx=x^{n+1}/(n+1)+C\), for \(n\ne-1\). Here \(y\) is constant during integration with respect to \(x\).]

\[
\Phi=\frac{x^3}{3}+x^2y+xy^2+g(y).
\]

Differentiate this with respect to \(y\):

\[
\Phi_y=0+x^2+2xy+g'(y).
\]

Match it to \(N=x^2+2xy-y^2\):

\[
x^2+2xy+g'(y)=x^2+2xy-y^2.
\]

\[
g'(y)=-y^2.
\]

\[
g(y)=-\frac{y^3}{3}.
\]

Thus

\[
\boxed{\frac{x^3}{3}+x^2y+xy^2-\frac{y^3}{3}=C.}
\]

## Q6(b) Form a differential equation

> Form a differential equation of \(y=a\ln x+b\).

### Underlying-concept map

The two arbitrary constants \(a,b\) require two differentiations to eliminate them. The logarithm requires \(x>0\).

### Detailed answer

\[
y=a\ln x+b,\qquad x>0.
\]

Differentiate once. [Derivative rule: \(d(\ln x)/dx=1/x\); constants differentiate to zero.]

\[
\frac{dy}{dx}=\frac{a}{x}.
\]

Multiply by \(x\):

\[
a=x\frac{dy}{dx}.
\]

Differentiate \(y'=a/x\) again. [Power rule: \(d(x^{-1})/dx=-x^{-2}\).]

\[
\frac{d^2y}{dx^2}=-\frac{a}{x^2}.
\]

Multiply by \(x^2\):

\[
x^2\frac{d^2y}{dx^2}=-a.
\]

Substitute \(a=x\,dy/dx\):

\[
x^2\frac{d^2y}{dx^2}=-x\frac{dy}{dx}.
\]

\[
\boxed{x^2\frac{d^2y}{dx^2}+x\frac{dy}{dx}=0,\qquad x>0.}
\]

## Q6(c) Homogeneous first-order equation

> Solve \(\frac{dy}{dx}=\frac{xy-2y^2}{x^2-3xy}\).

### Underlying-concept map

Both numerator and denominator have total degree \(2\), so the right side depends only on \(y/x\). Use \(y=vx\), then separate variables.

> [!IMPORTANT]
> **Exam recognition and substitution**
>
> \[
> y=vx,\qquad \frac{dy}{dx}=v+x\frac{dv}{dx}.
> \]

### Detailed answer

Set

\[
y=vx.
\]

[Product rule: \(d(vx)/dx=v+x\,dv/dx\).]

\[
\frac{dy}{dx}=v+x\frac{dv}{dx}.
\]

Substitute \(y=vx\):

\[
\frac{xy-2y^2}{x^2-3xy}
=\frac{x(vx)-2(vx)^2}{x^2-3x(vx)}.
\]

\[
=\frac{vx^2-2v^2x^2}{x^2-3vx^2}.
\]

\[
=\frac{x^2(v-2v^2)}{x^2(1-3v)}
=\frac{v-2v^2}{1-3v}.
\]

Therefore

\[
v+x\frac{dv}{dx}=\frac{v-2v^2}{1-3v}.
\]

\[
x\frac{dv}{dx}
=\frac{v-2v^2}{1-3v}-v.
\]

\[
=\frac{v-2v^2-v(1-3v)}{1-3v}.
\]

\[
=\frac{v-2v^2-v+3v^2}{1-3v}.
\]

\[
=\frac{v^2}{1-3v}.
\]

Separate variables:

> [!IMPORTANT]
> **Exam separated equation**
>
> \[
> \frac{1-3v}{v^2}\,dv=\frac{dx}{x}.
> \]

\[
\frac{1-3v}{v^2}\,dv=\frac{dx}{x}.
\]

\[
\left(v^{-2}-3v^{-1}\right)dv=\frac{dx}{x}.
\]

[Integration rules: \(\int v^{-2}dv=-v^{-1}+C\), and \(\int v^{-1}dv=\ln|v|+C\).]

\[
-\frac1v-3\ln|v|=\ln|x|+C.
\]

Substitute \(v=y/x\):

> [!IMPORTANT]
> **Exam substitution back**
>
> \[
> v=\frac yx,\qquad \frac1v=\frac xy.
> \]

\[
-\frac{x}{y}-3\ln\left|\frac{y}{x}\right|=\ln|x|+C.
\]

\[
-\frac{x}{y}-3\ln|y|+3\ln|x|=\ln|x|+C.
\]

\[
\boxed{\frac{x}{y}+3\ln|y|-2\ln|x|=C.}
\]

This family assumes \(y\ne0\), because we divided by \(v^2\). The lost solution is

\[
\boxed{y=0.}
\]

The original equation also requires \(x\ne0\) and \(x-3y\ne0\).
