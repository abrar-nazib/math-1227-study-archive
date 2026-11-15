# KH Chapter 2, Problem 10: homogeneous substitution step by step

The problem on PDF page 8 asks us to solve

\[
(x^2-3y^2)\,dx+2xy\,dy=0.
\]

For the general distinction between first-order homogeneous equations and homogeneous linear equations, see [the ODE foundations](../../concepts/differential-equations-foundations.md#6-two-different-meanings-of-homogeneous). Here we use the **first-order ratio** meaning: the right side can be expressed using \(y/x\) alone.

## The idea before calculating

Think of \(v=y/x\) as tracking the ratio between the two coordinates as we move along a solution curve. It need not be constant: as \(x\) changes, \(y\) and their ratio \(v\) can change too. If the differential equation depends on that ratio, replacing it by one symbol often leaves an equation we can separate.

The route is: write the equation in derivative form; recognize the ratio; use \(y=vx\); separate and integrate; then return to \(x,y\). We will also check what happens to expressions we divide by.

## 1. Write the derivative form

Treat \(y\) as a differentiable function of \(x\). From the differential equation,

\[
\begin{aligned}
(x^2-3y^2)\,dx+2xy\,dy&=0,\\
(x^2-3y^2)+2xy\frac{dy}{dx}&=0,\\
2xy\frac{dy}{dx}&=-(x^2-3y^2),\\
\frac{dy}{dx}&=-\frac{x^2-3y^2}{2xy}.
\end{aligned}
\]

The last line divides by \(2xy\), so use it only where \(x\ne0\) and \(y\ne0\). Later, check the original equation rather than silently assuming those restrictions cover every possible point.

## 2. Why is it homogeneous?

For \(x\ne0\), divide the numerator and denominator by \(x^2\):

\[
\begin{aligned}
-\frac{x^2-3y^2}{2xy}
&=-\frac{(x^2-3y^2)/x^2}{(2xy)/x^2}\\
&=-\frac{1-3(y/x)^2}{2(y/x)}.
\end{aligned}
\]

The remaining expression uses \(x\) and \(y\) only through the ratio \(y/x\). That is the cue for the homogeneous substitution.

## 3. Substitute the ratio

Let \(v=v(x)=y/x\), or equivalently \(y=vx\). Because \(v\) can vary with \(x\), we must differentiate a product. [Product rule: \(d(uv)/dx=u'v+uv'\); also \(d(x)/dx=1\).]

\[
\begin{aligned}
\frac{dy}{dx}
&=\frac{d}{dx}(vx)\\
&=\frac{dv}{dx}x+v\frac{d}{dx}(x)\\
&=x\frac{dv}{dx}+v.
\end{aligned}
\]

It would be incorrect to write just \(dy/dx=v\) unless \(v\) happened to be constant.

Substitute \(y=vx\) and the derivative into the equation:

\[
\begin{aligned}
v+x\frac{dv}{dx}
&=-\frac{x^2-3(vx)^2}{2x(vx)}\\
&=-\frac{x^2-3v^2x^2}{2vx^2}\\
&=-\frac{x^2(1-3v^2)}{2vx^2}\\
&=-\frac{1-3v^2}{2v}.
\end{aligned}
\]

In the last line we cancelled \(x^2\), using \(x\ne0\). The denominator also requires \(v\ne0\), corresponding to \(y\ne0\).

## 4. Isolate and separate the variables

Subtract \(v\) from both sides, then use a common denominator:

\[
\begin{aligned}
x\frac{dv}{dx}
&=-\frac{1-3v^2}{2v}-v\\
&=\frac{-1+3v^2}{2v}-\frac{2v^2}{2v}\\
&=\frac{-1+3v^2-2v^2}{2v}\\
&=\frac{v^2-1}{2v}.
\end{aligned}
\]

On a segment where \(v^2-1\ne0\), multiply by \(2v/(v^2-1)\), divide by \(x\), and write the differential form:

\[
\begin{aligned}
\frac{2v}{v^2-1}\frac{dv}{dx}&=\frac1x,\\
\frac{2v}{v^2-1}\,dv&=\frac{dx}{x}.
\end{aligned}
\]

We have also divided by \(v^2-1\), so we must return to \(v=1\) and \(v=-1\) after integrating.

## 5. Integrate, including absolute values

Use the logarithm rule

\[
\int\frac{u'}{u}\,dx=\ln\lvert u\rvert+C,
\qquad
\int\frac{dx}{x}=\ln\lvert x\rvert+C.
\]

On the left set \(u=v^2-1\). [Power rule: \(d(v^2-1)/dv=2v\), so \(du=2v\,dv\).] Hence

\[
\begin{aligned}
\int\frac{2v}{v^2-1}\,dv&=\int\frac{dx}{x},\\
\int\frac{du}{u}&=\int\frac{dx}{x},\\
\ln\lvert u\rvert&=\ln\lvert x\rvert+K,\\
\ln\lvert v^2-1\rvert&=\ln\lvert x\rvert+K.
\end{aligned}
\]

The absolute values matter: the expressions inside the logarithms can be negative. This integration is valid on an interval where \(x\ne0\) and \(v^2-1\ne0\).

Exponentiate, using \(e^{\ln z}=z\) for \(z>0\) and \(e^{a+b}=e^ae^b\):

\[
\begin{aligned}
e^{\ln\lvert v^2-1\rvert}
&=e^{\ln\lvert x\rvert+K},\\
\lvert v^2-1\rvert&=e^K\lvert x\rvert.
\end{aligned}
\]

On each connected interval, the signs of \(x\) and \(v^2-1\) are fixed. Absorb their sign and the positive factor \(e^K\) into a real nonzero constant \(C\):

\[
v^2-1=Cx.
\]

The PDF writes logarithms without absolute values; the above version covers both signs correctly.

## 6. Return to x and y

Substitute \(v=y/x\), then multiply both sides by \(x^2\):

\[
\begin{aligned}
\left(\frac yx\right)^2-1&=Cx,\\
\frac{y^2}{x^2}-1&=Cx,\\
\frac{y^2-x^2}{x^2}&=Cx,\\
y^2-x^2&=Cx^3.
\end{aligned}
\]

Thus the implicit family is

\[
\boxed{y^2-x^2=Cx^3.}
\]

## 7. Check the divided-out cases

The separation step divided by \(v^2-1\). If \(v=1\), then \(y=x\); if \(v=-1\), then \(y=-x\). Both satisfy the original differential equation: for either straight line \(y=\pm x\), [rule: \(d(\pm x)/dx=\pm1\)] substitute into its derivative form *before* division by \(2xy\):

\[
\begin{aligned}
x^2-3x^2+2x(x)(1)&=0\quad(y=x),\\
x^2-3x^2+2x(-x)(-1)&=0\quad(y=-x).
\end{aligned}
\]

They are already included by allowing \(C=0\) in the final implicit family. They were not produced by the logarithm step, so they need this separate check.

The earlier derivative form also excluded \(y=0\). The whole line \(y=0\) is not a solution on an interval: [rule: \(d(0)/dx=0\)] substitution in \(x^2-3y^2+2xyy'=0\) would require \(x^2=0\) throughout that interval. A differentiable graph satisfying the original equation can meet \(y=0\) only at \(x=0\); the origin is a singular point, so the divided equation alone cannot decide how curves behave there.

## 8. Check the final family

Differentiate \(y^2-x^2=Cx^3\) along a differentiable solution, treating \(C\) as constant. [Power and chain rules: \(d(y^2)/dx=2y\,dy/dx\), \(d(x^2)/dx=2x\), and \(d(x^3)/dx=3x^2\).]

\[
2y\frac{dy}{dx}-2x=3Cx^2.
\]

On an interval where \(x\ne0\), use the family to substitute \(C=(y^2-x^2)/x^3\):

\[
\begin{aligned}
2y\frac{dy}{dx}-2x
&=3x^2\left(\frac{y^2-x^2}{x^3}\right)\\
&=\frac{3(y^2-x^2)}{x},\\
2xy\frac{dy}{dx}-2x^2&=3y^2-3x^2,\\
2xy\frac{dy}{dx}+x^2-3y^2&=0.
\end{aligned}
\]

This is the original equation in derivative form. The implicit relation may contain branches or points that cannot be represented as a differentiable \(y(x)\); use an appropriate differentiable branch when interpreting a solution.
