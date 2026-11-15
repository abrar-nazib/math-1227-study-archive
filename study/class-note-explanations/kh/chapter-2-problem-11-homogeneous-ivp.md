# KH Chapter 2, Problem 11: homogeneous equation and a square-root integral

The integral in your question occurs in **Problem 11**, immediately after Problem 10, on PDF pages 8–9. It asks us to solve

\[
\left(y+\sqrt{x^2+y^2}\right)dx-x\,dy=0,
\qquad y(1)=0.
\]

We use the same substitution as in [Problem 10](chapter-2-problem-10-homogeneous-ode.md), then spend extra time on the new integral. The initial condition means the solution passes through \((1,0)\). Because that point has \(x>0\), we work on an interval containing \(1\) where \(x>0\).

## 1. Separate the equation

Treat \(y\) as a function of \(x\). Divide by \(dx\), move terms, and divide by \(x\), which is nonzero on our chosen interval:

\[
\begin{aligned}
y+\sqrt{x^2+y^2}-x\frac{dy}{dx}&=0,\\
x\frac{dy}{dx}&=y+\sqrt{x^2+y^2},\\
\frac{dy}{dx}&=\frac{y+\sqrt{x^2+y^2}}{x}.
\end{aligned}
\]

Set \(v=y/x\), so \(y=vx\). Here \(v\) can vary with \(x\). [Product rule: \(d(uv)/dx=u'v+uv'\), with \(d(x)/dx=1\).] Therefore

\[
\frac{dy}{dx}=v+x\frac{dv}{dx}.
\]

Substitute \(y=vx\) into the square root:

\[
\begin{aligned}
\sqrt{x^2+y^2}
&=\sqrt{x^2+(vx)^2}\\
&=\sqrt{x^2(1+v^2)}\\
&=\lvert x\rvert\sqrt{1+v^2}\\
&=x\sqrt{1+v^2}\quad\text{because }x>0.
\end{aligned}
\]

The absolute value is important: \(\sqrt{x^2}=|x|\), not always \(x\). We may replace it by \(x\) here because our interval contains \(1\) and stays positive.

Put the substitutions into the derivative equation:

\[
\begin{aligned}
v+x\frac{dv}{dx}
&=\frac{vx+x\sqrt{1+v^2}}{x}\\
&=v+\sqrt{1+v^2},\\
x\frac{dv}{dx}&=\sqrt{1+v^2},\\
\frac{1}{\sqrt{1+v^2}}\frac{dv}{dx}&=\frac1x,\\
\frac{dv}{\sqrt{1+v^2}}&=\frac{dx}{x}.
\end{aligned}
\]

We may divide by \(\sqrt{1+v^2}\) because it is strictly positive for every real \(v\).

## 2. How do we integrate the left side?

We want

\[
I=\int\frac{dv}{\sqrt{1+v^2}}.
\]

The notes quote the logarithm answer without showing why. We can **derive** it with a substitution. Let

\[
u=v+\sqrt{1+v^2}.
\]

This might look like a guess; the useful observation is that its derivative contains the same square root as the original denominator. We will calculate that derivative and see the cancellation.

[Chain and power rules: \(d[f(g(v))]/dv=f'(g(v))g'(v)\), \(d(\sqrt{w})/dw=1/(2\sqrt w)\), and \(d(v^2)/dv=2v\).]

\[
\begin{aligned}
\frac{du}{dv}
&=\frac{d}{dv}\left(v+\sqrt{1+v^2}\right)\\
&=1+\frac1{2\sqrt{1+v^2}}\frac{d}{dv}(1+v^2)\\
&=1+\frac{2v}{2\sqrt{1+v^2}}\\
&=1+\frac{v}{\sqrt{1+v^2}}\\
&=\frac{\sqrt{1+v^2}+v}{\sqrt{1+v^2}}\\
&=\frac{u}{\sqrt{1+v^2}}.
\end{aligned}
\]

Multiplying by \(dv\), then dividing by \(u\), gives

\[
\begin{aligned}
du&=\frac{u}{\sqrt{1+v^2}}\,dv,\\
\frac{du}{u}&=\frac{dv}{\sqrt{1+v^2}}.
\end{aligned}
\]

The expression on the right is exactly our integrand. Also, \(u>0\) for every real \(v\), because \(\sqrt{1+v^2}>|v|\), so adding \(v\) stays positive. [Logarithm rule: \(\int du/u=\ln|u|+C\).] Thus

\[
\begin{aligned}
I&=\int\frac{du}{u}\\
&=\ln|u|+C\\
&=\ln\left(v+\sqrt{1+v^2}\right)+C.
\end{aligned}
\]

The absolute value is unnecessary in the last line because this particular \(u\) is always positive. Another name for the same antiderivative is \(\operatorname{arsinh}v+C\), but you do not need that name to use the logarithm form.

## 3. Integrate and apply the initial condition

On the right, [logarithm rule: \(\int dx/x=\ln|x|+C\)]. Since \(x>0\), \(\ln|x|=\ln x\). Integrating the separated equation and combining the two constants gives

\[
\ln\left(v+\sqrt{1+v^2}\right)=\ln x+K.
\]

Exponentiate both sides. [Rules: \(e^{a+b}=e^ae^b\), and \(e^{\ln z}=z\) for \(z>0\).]

\[
\begin{aligned}
v+\sqrt{1+v^2}&=xe^K,\\
v+\sqrt{1+v^2}&=Cx,
\end{aligned}
\]

where \(C=e^K>0\). Substitute \(v=y/x\) and use \(x>0\):

\[
\begin{aligned}
\frac yx+\sqrt{1+\frac{y^2}{x^2}}&=Cx,\\
\frac yx+\frac{\sqrt{x^2+y^2}}{x}&=Cx,\\
\frac{y+\sqrt{x^2+y^2}}{x}&=Cx,\\
y+\sqrt{x^2+y^2}&=Cx^2.
\end{aligned}
\]

The condition \(y(1)=0\) means insert \(x=1\), \(y=0\):

\[
\begin{aligned}
0+\sqrt{1^2+0^2}&=C(1^2),\\
1&=C.
\end{aligned}
\]

Therefore the implicit answer in the notes is

\[
\boxed{y+\sqrt{x^2+y^2}=x^2,\qquad x>0.}
\]

## 4. Make the answer explicit and check it

The implicit equation can also be solved for \(y\). First isolate the square root, then square both sides:

\[
\begin{aligned}
\sqrt{x^2+y^2}&=x^2-y,\\
x^2+y^2&=(x^2-y)^2,\\
x^2+y^2&=x^4-2x^2y+y^2,\\
x^2&=x^4-2x^2y,\\
1&=x^2-2y\quad(x>0),\\
\boxed{y&=\frac{x^2-1}{2}.}
\end{aligned}
\]

Squaring can introduce unwanted solutions, so check the result in the unsquared equation. For \(x>0\),

\[
\begin{aligned}
x^2+y^2
&=x^2+\left(\frac{x^2-1}{2}\right)^2\\
&=\frac{4x^2+(x^2-1)^2}{4}\\
&=\frac{x^4+2x^2+1}{4}\\
&=\frac{(x^2+1)^2}{4},\\
\sqrt{x^2+y^2}&=\frac{x^2+1}{2},\\
y+\sqrt{x^2+y^2}
&=\frac{x^2-1}{2}+\frac{x^2+1}{2}\\
&=x^2.
\end{aligned}
\]

Finally, [power rule: \(d(x^2)/dx=2x\), \(d(\text{constant})/dx=0\)] gives \(y'=x\). In the original equation written as \(y+\sqrt{x^2+y^2}-xy'=0\), substitution gives \(x^2-x(x)=0\). Also \(y(1)=(1-1)/2=0\). Both the equation and initial condition check out.
