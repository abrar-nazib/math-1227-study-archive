# KH Chapter 2, Problem 12: both homogeneous equations

These are the two exercises on PDF page 9. Both use \(v=y/x\), but the first contains a square root and the second needs partial fractions. For the basic substitution and why \(dy/dx=v+x\,dv/dx\), see [Problem 10](chapter-2-problem-10-homogeneous-ode.md). In each solution below, work on an interval where \(x\ne0\); it is either entirely positive or entirely negative.

## 12(i)

\[
\left(x^3+y^2\sqrt{x^2+y^2}\right)dx
-xy\sqrt{x^2+y^2}\,dy=0.
\]

### Plan

Put the equation in derivative form, use \(y=vx\), separate, and integrate. The important point is \(\sqrt{x^2}=|x|\), so we must account for the sign of \(x\).

### Step 1: substitute

Let \(r=\sqrt{x^2+y^2}\). On a segment with \(x\ne0\) and \(y\ne0\), \(r>0\), so dividing by \(xyr\) is allowed:

\[
\begin{aligned}
x^3+y^2r-xyr\frac{dy}{dx}&=0,\\
xyr\frac{dy}{dx}&=x^3+y^2r,\\
\frac{dy}{dx}&=\frac{x^3}{xyr}+\frac{y^2r}{xyr}\\
&=\frac{x^2}{yr}+\frac yx.
\end{aligned}
\]

Put \(v=y/x\), \(y=vx\). [Product rule: \(d(vx)/dx=v+x\,dv/dx\).] Define \(\varepsilon=\operatorname{sgn}(x)\), which is \(1\) for positive \(x\) and \(-1\) for negative \(x\); it is constant on the interval. Then

\[
\begin{aligned}
r&=\sqrt{x^2+v^2x^2}\\
&=|x|\sqrt{1+v^2}\\
&=\varepsilon x\sqrt{1+v^2}.
\end{aligned}
\]

Substitute all three expressions:

\[
\begin{aligned}
v+x\frac{dv}{dx}
&=\frac{x^2}{(vx)(\varepsilon x\sqrt{1+v^2})}+v\\
&=\frac{1}{\varepsilon v\sqrt{1+v^2}}+v\\
&=\frac{\varepsilon}{v\sqrt{1+v^2}}+v,\\
x\frac{dv}{dx}&=\frac{\varepsilon}{v\sqrt{1+v^2}}.
\end{aligned}
\]

Here \(1/\varepsilon=\varepsilon\) because \(\varepsilon=\pm1\). Multiply by \(v\sqrt{1+v^2}/x\):

\[
v\sqrt{1+v^2}\,dv=\varepsilon\frac{dx}{x}.
\]

### Step 2: integrate

For the left side set \(u=1+v^2\). [Power rule: \(du/dv=2v\), so \(v\,dv=du/2\); integration power rule: \(\int u^n du=u^{n+1}/(n+1)+C\), \(n\ne-1\).] On the right use \(\int dx/x=\ln|x|+C\):

\[
\begin{aligned}
\int v\sqrt{1+v^2}\,dv
&=\varepsilon\int\frac{dx}{x},\\
\frac12\int u^{1/2}\,du
&=\varepsilon\ln|x|+K,\\
\frac12\left(\frac{u^{3/2}}{3/2}\right)
&=\varepsilon\ln|x|+K,\\
\frac13(1+v^2)^{3/2}
&=\varepsilon\ln|x|+K.
\end{aligned}
\]

Multiply by \(\varepsilon\), and absorb \(\varepsilon K\) into a new constant \(C\). Because \(\varepsilon|x|^3=x^3\),

\[
\begin{aligned}
\frac{\varepsilon}{3}\left(1+\frac{y^2}{x^2}\right)^{3/2}
&=\ln|x|+C,\\
\frac{(x^2+y^2)^{3/2}}{3x^3}
&=\ln|x|+C.
\end{aligned}
\]

Thus one implicit solution family is

\[
\boxed{\frac{(x^2+y^2)^{3/2}}{3x^3}-\ln|x|=C,\qquad x\ne0.} \tag{1}
\]

The formula works on either sign of \(x\); \(C\) can differ between disconnected intervals.

### Check and divided-out case

Along a differentiable curve, use the chain rule \(d[w^{3/2}]/dx=\tfrac32w^{1/2}w'\), product rule \((uv)'=u'v+uv'\), and \(d\ln|x|/dx=1/x\). With \(r=\sqrt{x^2+y^2}\), \(d(x^2+y^2)/dx=2x+2yy'\), so

\[
\begin{aligned}
\frac{d}{dx}\left(\frac{r^3}{3x^3}-\ln|x|\right)
&=\frac{r(x+yy')}{x^3}-\frac{r^3}{x^4}-\frac1x\\
&=\frac{xr(x+yy')-r^3-x^3}{x^4}\\
&=\frac{x^2r+xyry'-r(x^2+y^2)-x^3}{x^4}\\
&=\frac{xyry'-y^2r-x^3}{x^4}.
\end{aligned}
\]

Setting this to zero recovers the original equation in derivative form. The division by \(y\) excludes \(y=0\) during the derivation, but \(y\equiv0\) is not a solution on any interval with \(x\ne0\): substitution into the original derivative form gives \(x^3=0\), which is false there. An implicit curve may meet \(y=0\) at a singular point where it cannot be represented as a differentiable graph; do not automatically infer a graph solution there. The line \(x=0\) is outside the graph calculation and the original differential form degenerates there.

## 12(ii)

\[
\frac{dy}{dx}=\frac{y^3+3x^2y}{x^3+3xy^2}.
\]

### Step 1: substitute and simplify

For real \(x,y\), the denominator is \(x(x^2+3y^2)\). It is nonzero whenever \(x\ne0\). Use \(y=vx\) and [product rule: \(dy/dx=v+x\,dv/dx\)]:

\[
\begin{aligned}
v+x\frac{dv}{dx}
&=\frac{(vx)^3+3x^2(vx)}{x^3+3x(vx)^2}\\
&=\frac{v^3x^3+3vx^3}{x^3+3v^2x^3}\\
&=\frac{x^3(v^3+3v)}{x^3(1+3v^2)}\\
&=\frac{v^3+3v}{1+3v^2}.
\end{aligned}
\]

Subtract \(v\), using the same denominator:

\[
\begin{aligned}
x\frac{dv}{dx}
&=\frac{v^3+3v}{1+3v^2}-v\\
&=\frac{v^3+3v-v(1+3v^2)}{1+3v^2}\\
&=\frac{v^3+3v-v-3v^3}{1+3v^2}\\
&=\frac{2v-2v^3}{1+3v^2}\\
&=\frac{2v(1-v^2)}{1+3v^2}.
\end{aligned}
\]

For \(v\ne0,\pm1\), separate:

\[
\frac{1+3v^2}{2v(1-v^2)}\,dv=\frac{dx}{x}.
\]

The values \(v=0,\pm1\) were divided out, so we will check them separately.

### Step 2: split the fraction

The left-hand fraction is easier to integrate when split into two familiar pieces:

\[
\frac{1+3v^2}{2v(1-v^2)}
=\frac1{2v}+\frac{2v}{1-v^2}.
\]

Check by putting them over a common denominator:

\[
\begin{aligned}
\frac1{2v}+\frac{2v}{1-v^2}
&=\frac{1-v^2}{2v(1-v^2)}+\frac{4v^2}{2v(1-v^2)}\\
&=\frac{1-v^2+4v^2}{2v(1-v^2)}\\
&=\frac{1+3v^2}{2v(1-v^2)}.
\end{aligned}
\]

### Step 3: integrate

Use \(\int dv/v=\ln|v|+C\). For the second term set \(u=1-v^2\); [power rule: \(du=-2v\,dv\); logarithm rule: \(\int du/u=\ln|u|+C\)]. Therefore

\[
\begin{aligned}
\int\left(\frac1{2v}+\frac{2v}{1-v^2}\right)dv
&=\int\frac{dx}{x},\\
\frac12\ln|v|-\ln|1-v^2|
&=\ln|x|+K.
\end{aligned}
\]

Multiply by 2, using \(2\ln|z|=\ln|z|^2\) and \(\ln a-\ln b=\ln(a/b)\) for positive \(a,b\):

\[
\begin{aligned}
\ln|v|-2\ln|1-v^2|&=2\ln|x|+2K,\\
\ln\left(\frac{|v|}{(1-v^2)^2}\right)
&=\ln(x^2)+2K.
\end{aligned}
\]

Exponentiating and absorbing the sign of \(v\) into a nonzero constant \(C\) gives

\[
\frac{v}{(1-v^2)^2}=Cx^2.
\]

Substitute \(v=y/x\):

\[
\begin{aligned}
\frac{y/x}{\left(1-y^2/x^2\right)^2}&=Cx^2,\\
\frac{y/x}{\left((x^2-y^2)/x^2\right)^2}&=Cx^2,\\
\frac{y}{x}\frac{x^4}{(x^2-y^2)^2}&=Cx^2,\\
\frac{yx^3}{(x^2-y^2)^2}&=Cx^2,\\
\boxed{\frac{xy}{(x^2-y^2)^2}&=C.} \tag{2}
\end{aligned}
\]

Equation (2) applies on intervals with \(x\ne0\) and \(x^2-y^2\ne0\). Although separation assumed \(y\ne0\), setting \(C=0\) in (2) gives \(y=0\), which we still check below.

### Step 4: check the divided-out lines

\(v=0,1,-1\) correspond to \(y=0,x,-x\). [Rule: \(d(kx)/dx=k\) for constant \(k\).] In the original equation, with \(x\ne0\):

\[
\begin{aligned}
y=0:&\quad y'=0,\quad
\frac{0^3+3x^2(0)}{x^3+3x(0)^2}=0;\\
y=x:&\quad y'=1,\quad
\frac{x^3+3x^3}{x^3+3x^3}=1;\\
y=-x:&\quad y'=-1,\quad
\frac{-x^3-3x^3}{x^3+3x^3}=-1.
\end{aligned}
\]

All three are solutions. The line \(y=0\) is included in (2) with \(C=0\). The lines \(y=\pm x\) make its denominator zero, so **include them separately**. The original equation is undefined at \(x=0\), so none of these are solutions across that point as written.

### Step 5: verify the implicit family

Write \(F=xy/(x^2-y^2)^2\). Along a differentiable curve with \(x\ne0\), \(x^2-y^2\ne0\), apply the product and chain rules \((uv)'=u'v+uv'\), \(d(w^{-2})/dx=-2w^{-3}w'\), and \(d(y^2)/dx=2yy'\):

\[
\begin{aligned}
\frac{dF}{dx}
&=(y+xy')(x^2-y^2)^{-2}
-2xy(x^2-y^2)^{-3}(2x-2yy')\\
&=\frac{(y+xy')(x^2-y^2)-2xy(2x-2yy')}{(x^2-y^2)^3}\\
&=\frac{yx^2-y^3+x^3y'-xy^2y'-4x^2y+4xy^2y'}{(x^2-y^2)^3}\\
&=\frac{(x^3+3xy^2)y'-(y^3+3x^2y)}{(x^2-y^2)^3}.
\end{aligned}
\]

So \(F=C\) implies the numerator is zero, exactly the original ODE after multiplying by its nonzero denominator.
