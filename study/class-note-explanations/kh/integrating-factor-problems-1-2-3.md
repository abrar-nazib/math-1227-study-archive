# KH integrating-factor exercises 1–3

These are the three exercises at the top of PDF page 10 of the KH first-order ODE notes. The goal is to find an integrating factor, multiply **both** coefficients by it, and then use the systematic potential-function method—not grouping.

For the idea of exactness and how to construct a potential, see [the exact-equation and integrating-factor note](../../concepts/first-order-odes-exact-integrating-factors-and-substitutions.md) and [Problem 6](chapter-2-problem-6-exact-equation.md).

## How we choose a factor

Write \(M(x,y)dx+N(x,y)dy=0\). If \(M_y\ne N_x\), the equation is not exact as written. The subscripts mean partial derivatives: \(M_y\) holds \(x\) fixed; \(N_x\) holds \(y\) fixed.

Two useful tests from the preceding PDF page are:

\[
\frac{M_y-N_x}{N}=f(x)
\quad\Rightarrow\quad
\mu(x)=e^{\int f(x)\,dx},
\]

\[
\frac{N_x-M_y}{M}=g(y)
\quad\Rightarrow\quad
\mu(y)=e^{\int g(y)\,dy}.
\]

Use each test only on a region where its denominator is nonzero and the displayed ratio really depends on only the indicated variable. The signs are opposite: for an \(x\)-factor start with \(M_y-N_x\); for a \(y\)-factor start with \(N_x-M_y\). Multiplying a factor by a nonzero constant does not change its usefulness.

After finding \(\mu\), set \(\widetilde M=\mu M\), \(\widetilde N=\mu N\), check \(\widetilde M_y=\widetilde N_x\), and solve using \(F_x=\widetilde M\), \(F_y=\widetilde N\).

## Problem 1

\[
(x^2+y^2+x)dx+xy\,dy=0.
\]

### Find the integrating factor

Let

\[
M=x^2+y^2+x,\qquad N=xy.
\]

Hold \(x\) fixed for \(M_y\) and \(y\) fixed for \(N_x\). [Partial-derivative rules: \(\partial(y^2)/\partial y=2y\), \(\partial x/\partial y=0\), \(\partial x/\partial x=1\), \(\partial y/\partial x=0\).]

\[
\begin{aligned}
M_y&=0+2y+0=2y,\\
N_x&=y(1)=y.
\end{aligned}
\]

They are not equal as functions, so try the \(x\)-factor ratio. On a region where \(xy\ne0\),

\[
\begin{aligned}
\frac{M_y-N_x}{N}
&=\frac{2y-y}{xy}\\
&=\frac{y}{xy}\\
&=\frac1x.
\end{aligned}
\]

Only \(x\) remains. [Logarithm rule: \(\int dx/x=\ln|x|+C\).] A nonzero factor on either interval \(x>0\) or \(x<0\) is

\[
\begin{aligned}
\mu(x)&=e^{\int (1/x)dx}\\
&=e^{\ln|x|}\\
&=|x|.
\end{aligned}
\]

On either interval, \(x\) differs from \(|x|\) only by a nonzero constant sign, so we may choose the simpler \(\boxed{\mu=x}\). The ratio was calculated where \(y\ne0\); the resulting factor and exactness check below remain valid at \(y=0\) as long as \(x\ne0\).

### Multiply and construct F

\[
\begin{aligned}
\widetilde M&=x(x^2+y^2+x)=x^3+xy^2+x^2,\\
\widetilde N&=x(xy)=x^2y.
\end{aligned}
\]

Check exactness. [Power and constant-multiple rules: \(\partial(y^2)/\partial y=2y\), \(\partial(x^2)/\partial x=2x\).]

\[
\widetilde M_y=2xy,\qquad \widetilde N_x=2xy.
\]

Integrate \(F_x=\widetilde M\) with respect to \(x\), holding \(y\) constant. [Power rule: \(\int x^n dx=x^{n+1}/(n+1)+C\), \(n\ne-1\).]

\[
\begin{aligned}
F&=\int(x^3+xy^2+x^2)dx\\
&=\frac{x^4}{4}+y^2\frac{x^2}{2}+\frac{x^3}{3}+g(y)\\
&=\frac{x^4}{4}+\frac{x^2y^2}{2}+\frac{x^3}{3}+g(y).
\end{aligned}
\]

Differentiate with respect to \(y\), holding \(x\) fixed. [Rules: \(\partial(y^2)/\partial y=2y\), \(d[g(y)]/dy=g'(y)\).]

\[
\begin{aligned}
F_y&=0+\frac{x^2}{2}(2y)+0+g'(y)\\
&=x^2y+g'(y).
\end{aligned}
\]

Match with \(\widetilde N=x^2y\):

\[
\begin{aligned}
x^2y+g'(y)&=x^2y,\\
g'(y)&=0,\\
g(y)&=\text{constant}.
\end{aligned}
\]

The constant can be absorbed into the right-hand side, so

\[
\boxed{\frac{x^4}{4}+\frac{x^2y^2}{2}+\frac{x^3}{3}=C,\qquad x\ne0.}
\]

Multiplying the whole equation by 12 and renaming the constant yields \(3x^4+6x^2y^2+4x^3=C\), the answer printed in the notes. Since \(x\) is zero on the excluded line, multiplication by this factor is not reversible there; the original form also admits the vertical curve \(x=0\) if solution curves are considered parametrically, though it is not a graph \(y(x)\) on an interval.

## Problem 2

\[
(3x^2y^4+2xy)dx+(2x^3y^3-x^2)dy=0.
\]

This is also 2020 Q6(c) in the question archive.

### Find the integrating factor

\[
M=3x^2y^4+2xy,\qquad N=2x^3y^3-x^2.
\]

Hold \(x\) constant for \(M_y\), \(y\) constant for \(N_x\). [Power rule: \(\partial(u^n)/\partial u=nu^{n-1}\); the other variable is constant.]

\[
\begin{aligned}
M_y&=3x^2(4y^3)+2x=12x^2y^3+2x,\\
N_x&=2(3x^2)y^3-2x=6x^2y^3-2x.
\end{aligned}
\]

Try the \(y\)-factor ratio, carefully keeping the order \(N_x-M_y\):

\[
\begin{aligned}
\frac{N_x-M_y}{M}
&=\frac{(6x^2y^3-2x)-(12x^2y^3+2x)}{3x^2y^4+2xy}\\
&=\frac{-6x^2y^3-4x}{3x^2y^4+2xy}\\
&=\frac{-2x(3xy^3+2)}{xy(3xy^3+2)}\\
&=-\frac2y.
\end{aligned}
\]

The cancellation was performed where \(M\ne0\), in particular \(x\ne0\), \(y\ne0\), and \(3xy^3+2\ne0\). The simplified expression depends only on \(y\). [Logarithm rule: \(\int dy/y=\ln|y|+C\).]

\[
\begin{aligned}
\mu(y)&=e^{\int(-2/y)dy}\\
&=e^{-2\ln|y|}\\
&=|y|^{-2}\\
&=\boxed{\frac1{y^2}}\qquad(y\ne0).
\end{aligned}
\]

### Multiply, then find F

\[
\begin{aligned}
\widetilde M
&=\frac{3x^2y^4+2xy}{y^2}\\
&=3x^2y^2+\frac{2x}{y},\\
\widetilde N
&=\frac{2x^3y^3-x^2}{y^2}\\
&=2x^3y-\frac{x^2}{y^2}.
\end{aligned}
\]

Check the transformed coefficients directly, holding the other variable fixed. [Power rule: \(d(y^n)/dy=ny^{n-1}\), including \(d(y^{-1})/dy=-y^{-2}\); \(d(x^n)/dx=nx^{n-1}\).]

\[
\begin{aligned}
\widetilde M_y&=3x^2(2y)+2x(-y^{-2})
=6x^2y-\frac{2x}{y^2},\\
\widetilde N_x&=2(3x^2)y-\frac{2x}{y^2}
=6x^2y-\frac{2x}{y^2}.
\end{aligned}
\]

They agree for \(y\ne0\), even at points excluded temporarily when calculating the ratio, provided the factor itself is defined. Now integrate \(F_x=\widetilde M\) with respect to \(x\), holding \(y\) fixed. [Power rule: \(\int x^n dx=x^{n+1}/(n+1)+C\).]

\[
\begin{aligned}
F&=\int\left(3x^2y^2+\frac{2x}{y}\right)dx\\
&=3y^2\left(\frac{x^3}{3}\right)+\frac2y\left(\frac{x^2}{2}\right)+g(y)\\
&=x^3y^2+\frac{x^2}{y}+g(y).
\end{aligned}
\]

Differentiate with respect to \(y\), holding \(x\) fixed. [Rules: \(d(y^2)/dy=2y\), \(d(y^{-1})/dy=-y^{-2}\), and \(d[g(y)]/dy=g'(y)\).]

\[
\begin{aligned}
F_y&=2x^3y-\frac{x^2}{y^2}+g'(y),\\
2x^3y-\frac{x^2}{y^2}+g'(y)
&=2x^3y-\frac{x^2}{y^2},\\
g'(y)&=0.
\end{aligned}
\]

Thus, after absorbing the constant \(g\),

\[
\boxed{x^3y^2+\frac{x^2}{y}=C,\qquad y\ne0.}
\]

The factor is undefined at \(y=0\), so check that case in the original equation. [Derivative of a constant: \(d(0)/dx=0\).] For \(y(x)=0\), both \(M(x,0)=0\) and \(dy/dx=0\), so \(M+Ny'=0\). Therefore **\(y=0\) is an additional solution**, not contained in the displayed family.

## Problem 3

\[
(x^4+y^4)dx-xy^3\,dy=0.
\]

### Find the integrating factor

\[
M=x^4+y^4,\qquad N=-xy^3.
\]

Hold \(x\) constant for \(M_y\), \(y\) constant for \(N_x\). [Rules: \(\partial(y^4)/\partial y=4y^3\), \(\partial x/\partial x=1\), and the other variable is fixed.]

\[
\begin{aligned}
M_y&=0+4y^3=4y^3,\\
N_x&=-y^3.
\end{aligned}
\]

Try the \(x\)-factor ratio, initially where \(xy\ne0\):

\[
\begin{aligned}
\frac{M_y-N_x}{N}
&=\frac{4y^3-(-y^3)}{-xy^3}\\
&=\frac{5y^3}{-xy^3}\\
&=-\frac5x.
\end{aligned}
\]

[Logarithm rule: \(\int dx/x=\ln|x|+C\).] On either interval \(x>0\) or \(x<0\),

\[
\begin{aligned}
\mu(x)&=e^{\int(-5/x)dx}\\
&=e^{-5\ln|x|}\\
&=|x|^{-5}.
\end{aligned}
\]

Since \(x^{-5}\) differs from \(|x|^{-5}\) by a nonzero constant sign on each interval, choose

\[
\boxed{\mu=x^{-5}=\frac1{x^5}},\qquad x\ne0.
\]

### Multiply, then find F

\[
\begin{aligned}
\widetilde M&=\frac{x^4+y^4}{x^5}
=\frac1x+\frac{y^4}{x^5},\\
\widetilde N&=\frac{-xy^3}{x^5}
=-\frac{y^3}{x^4}.
\end{aligned}
\]

Check exactness, holding the other variable fixed. [Power rules: \(d(y^4)/dy=4y^3\), \(d(x^{-4})/dx=-4x^{-5}\).]

\[
\begin{aligned}
\widetilde M_y&=\frac{4y^3}{x^5},\\
\widetilde N_x&=-y^3(-4x^{-5})=\frac{4y^3}{x^5}.
\end{aligned}
\]

The transformed equation is exact. Integrate \(F_x=\widetilde M\) with respect to \(x\), holding \(y\) fixed. [Rules: \(\int dx/x=\ln|x|+C\) and \(\int x^n dx=x^{n+1}/(n+1)+C\), \(n\ne-1\).]

\[
\begin{aligned}
F&=\int\left(\frac1x+y^4x^{-5}\right)dx\\
&=\ln|x|+y^4\left(\frac{x^{-4}}{-4}\right)+g(y)\\
&=\ln|x|-\frac{y^4}{4x^4}+g(y).
\end{aligned}
\]

Differentiate with respect to \(y\), holding \(x\) fixed. [Rule: \(d(y^4)/dy=4y^3\).]

\[
\begin{aligned}
F_y&=-\frac{4y^3}{4x^4}+g'(y)\\
&=-\frac{y^3}{x^4}+g'(y).
\end{aligned}
\]

Match \(F_y\) to \(\widetilde N\):

\[
\begin{aligned}
-\frac{y^3}{x^4}+g'(y)&=-\frac{y^3}{x^4},\\
g'(y)&=0.
\end{aligned}
\]

Thus

\[
\boxed{\ln|x|-\frac{y^4}{4x^4}=C,\qquad x\ne0.}
\]

**Correction to the printed answer:** the PDF shows a plus sign before the fraction. The minus sign above is required: differentiating the minus term with respect to \(y\) gives the negative \(dy\) coefficient in the transformed equation. A plus sign would give the opposite sign. The factor is undefined at \(x=0\); the original differential form degenerates on the vertical line \(x=0\), which is not a graph \(y(x)\) over an interval.

## How to verify any of these

For each displayed potential \(F\), the working checked that \(F_x=\mu M\) and \(F_y=\mu N\). Therefore \(dF=\mu(Mdx+Ndy)\). On a region where \(\mu\ne0\), \(dF=0\) and the original differential equation have the same solution curves. Always inspect where the factor is zero or undefined separately, as we did for Problem 2.
