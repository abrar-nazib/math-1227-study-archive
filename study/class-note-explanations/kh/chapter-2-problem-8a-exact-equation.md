# KH Chapter 2, Problem 8(a): systematic exact-equation method

The question on PDF page 7 asks us to find the constant \(A\) that makes

\[
(Ax^2y+2y^2)\,dx+(x^3+4xy)\,dy=0
\]

exact, then solve the resulting equation. We will construct the potential function directly, as in [Problem 6](chapter-2-problem-6-exact-equation.md), without using grouping.

## The route

Write the equation as \(M\,dx+N\,dy=0\). First use \(M_y=N_x\) to determine \(A\). Then find a function \(F\) satisfying \(F_x=M\) and \(F_y=N\). Along a solution curve \(dF=0\), so \(F=C\).

Try it yourself: identify \(M,N\); calculate their relevant partial derivatives; solve for \(A\); integrate the new \(M\) with respect to \(x\); then match its \(y\)-derivative to \(N\).

## 1. Find the constant A

The coefficients of \(dx\) and \(dy\) are

\[
M(x,y)=Ax^2y+2y^2,\qquad N(x,y)=x^3+4xy.
\]

For this polynomial equation on the whole plane, exactness is equivalent to

\[
\frac{\partial M}{\partial y}=\frac{\partial N}{\partial x}.
\]

Differentiate \(M\) with respect to \(y\), treating \(x\) and \(A\) as constants. [Rules: \(\partial y/\partial y=1\), \(\partial(y^2)/\partial y=2y\), and \(\partial(c f)/\partial y=c\,\partial f/\partial y\) when \(c\) is fixed.]

\[
\begin{aligned}
\frac{\partial M}{\partial y}
&=\frac{\partial}{\partial y}(Ax^2y+2y^2)\\
&=Ax^2(1)+2(2y)\\
&=Ax^2+4y.
\end{aligned}
\]

Differentiate \(N\) with respect to \(x\), holding \(y\) constant. [Rules: \(\partial(x^3)/\partial x=3x^2\) and \(\partial(x)/\partial x=1\).]

\[
\begin{aligned}
\frac{\partial N}{\partial x}
&=\frac{\partial}{\partial x}(x^3+4xy)\\
&=3x^2+4y(1)\\
&=3x^2+4y.
\end{aligned}
\]

Set the two expressions equal:

\[
\begin{aligned}
Ax^2+4y&=3x^2+4y,\\
Ax^2&=3x^2,\\
(A-3)x^2&=0.
\end{aligned}
\]

Exactness requires this equality throughout the domain, not just at a single point such as \(x=0\). For example, at \(x=1\), it gives \(A-3=0\). Therefore

\[
\boxed{A=3.}
\]

## 2. Construct the potential F

Substituting \(A=3\), the equation becomes

\[
(3x^2y+2y^2)\,dx+(x^3+4xy)\,dy=0.
\]

We seek \(F(x,y)\) for which

\[
F_x=3x^2y+2y^2,\qquad F_y=x^3+4xy.
\]

Integrate the first equation with respect to \(x\), holding \(y\) constant. [Rules: \(\int x^n\,dx=x^{n+1}/(n+1)+C\) for \(n\ne-1\); \(\int c\,dx=cx+C\) when \(c\) is fixed with respect to \(x\).]

\[
\begin{aligned}
F(x,y)
&=\int(3x^2y+2y^2)\,dx\\
&=3y\int x^2\,dx+2y^2\int1\,dx\\
&=3y\left(\frac{x^3}{3}\right)+2y^2x+g(y)\\
&=x^3y+2xy^2+g(y).
\end{aligned}
\]

The unknown \(g(y)\) accounts for anything depending only on \(y\), since its partial derivative with respect to \(x\) is zero. We must still check the second partial derivative to determine it.

Differentiate with respect to \(y\), holding \(x\) constant. [Rules: \(\partial y/\partial y=1\), \(\partial(y^2)/\partial y=2y\), and \(d[g(y)]/dy=g'(y)\).]

\[
\begin{aligned}
F_y
&=\frac{\partial}{\partial y}\left(x^3y+2xy^2+g(y)\right)\\
&=x^3(1)+2x(2y)+g'(y)\\
&=x^3+4xy+g'(y).
\end{aligned}
\]

Match this with the required \(N\):

\[
\begin{aligned}
x^3+4xy+g'(y)&=x^3+4xy,\\
g'(y)&=0,\\
g(y)&=C_0,
\end{aligned}
\]

using \(\int0\,dy=C_0\). Thus \(F=x^3y+2xy^2+C_0\). The equation \(F=C_1\) absorbs \(C_0\) into a single arbitrary constant \(C=C_1-C_0\):

\[
\boxed{x^3y+2xy^2=C.}
\]

## 3. Check

For \(F=x^3y+2xy^2\), treating the other variable as constant in each derivative [power rule: \(d(u^n)/du=nu^{n-1}\)],

\[
\begin{aligned}
F_x&=3x^2y+2y^2=M,\\
F_y&=x^3+4xy=N.
\end{aligned}
\]

Both coefficients match the equation after \(A=3\). Hence the answer is the implicit family above, with \(A=3\).
