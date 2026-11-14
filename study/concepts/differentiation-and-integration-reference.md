# Differentiation and Integration: Quick Reference

Use this as a glance sheet. Here \(C\) is an arbitrary constant, \(u=u(x)\), and \(u'=du/dx\). For partial derivatives, treat all variables other than the differentiated one as constants.

> [!IMPORTANT]
> **Revision formula sheet**
>
> These are the rules to recognize and name in the `[Using: …]` annotations of worked solutions.

## Differentiation

### Core rules

| Rule | Formula |
| --- | --- |
| Constant | \(\frac{d}{dx}(c)=0\) |
| Power | \(\frac{d}{dx}(x^n)=nx^{n-1}\) |
| Constant multiple | \(\frac{d}{dx}[cf(x)]=cf'(x)\) |
| Sum / difference | \(\frac{d}{dx}[f\pm g]=f'\pm g'\) |
| Product | \(\frac{d}{dx}(uv)=u'v+uv'\) |
| Quotient | \(\frac{d}{dx}\left(\frac uv\right)=\frac{vu'-uv'}{v^2}\) |
| Chain | \(\frac{d}{dx}[f(u)]=f'(u)u'\) |

### Common functions

| Function | Derivative |
| --- | --- |
| \(e^x\) | \(e^x\) |
| \(e^{u}\) | \(e^{u}u'\) |
| \(a^x\) | \(a^x\ln a\) |
| \(\ln x\) | \(1/x\) |
| \(\ln\lvert u\rvert\) | \(u'/u\) |
| \(\sin u\) | \(\cos u\,u'\) |
| \(\cos u\) | \(-\sin u\,u'\) |
| \(\tan u\) | \(\sec^2u\,u'\) |
| \(\cot u\) | \(-\csc^2u\,u'\) |
| \(\sec u\) | \(\sec u\tan u\,u'\) |
| \(\csc u\) | \(-\csc u\cot u\,u'\) |
| \(\sin^{-1}u\) | \(u'/\sqrt{1-u^2}\) |
| \(\cos^{-1}u\) | \(-u'/\sqrt{1-u^2}\) |
| \(\tan^{-1}u\) | \(u'/(1+u^2)\) |

### Partial derivatives and gradient

For \(f(x,y,z)\), \(\partial f/\partial x\) means differentiate with respect to \(x\) while holding \(y,z\) fixed.

\[
\nabla f=\frac{\partial f}{\partial x}\hat i+
\frac{\partial f}{\partial y}\hat j+
\frac{\partial f}{\partial z}\hat k.
\]

Example: \(\partial(x^2y+3z)/\partial x=2xy\), because \(y,z\) are constants with respect to \(x\).

## Integration

### Core rules

| Rule | Formula |
| --- | --- |
| Constant | \(\int c\,dx=cx+C\) |
| Power \((n\ne-1)\) | \(\int x^n\,dx=\frac{x^{n+1}}{n+1}+C\) |
| Log case | \(\int\frac1x\,dx=\ln\lvert x\rvert+C\) |
| Constant multiple | \(\int cf(x)\,dx=c\int f(x)\,dx\) |
| Sum / difference | \(\int(f\pm g)dx=\int fdx\pm\int gdx\) |

### Common antiderivatives

| Integrand | Antiderivative |
| --- | --- |
| \(e^x\) | \(e^x+C\) |
| \(e^{ax}\) | \(e^{ax}/a+C\) |
| \(a^x\) | \(a^x/\ln a+C\) |
| \(\sin x\) | \(-\cos x+C\) |
| \(\cos x\) | \(\sin x+C\) |
| \(\cot x\) | \(\ln\lvert\sin x\rvert+C\) |
| \(\sec^2x\) | \(\tan x+C\) |
| \(\csc^2x\) | \(-\cot x+C\) |
| \(\sec x\tan x\) | \(\sec x+C\) |
| \(\csc x\cot x\) | \(-\csc x+C\) |
| \(1/(1+x^2)\) | \(\tan^{-1}x+C\) |
| \(x/(1+x^2)\) | \(\frac12\ln(1+x^2)+C\) |
| \(1/\sqrt{1-x^2}\) | \(\sin^{-1}x+C\) |

### Reverse chain rule: integration by substitution

When an integrand contains a function of an **inside expression** and the derivative of that inside expression, substitute \(u=g(x)\). Then \(du=g'(x)\,dx\). If \(F'(u)=f(u)\), the general rule is

> [!IMPORTANT]
> **Exam formula — substitution (reverse chain rule)**
>
> \[
> \int f(g(x))g'(x)\,dx=F(g(x))+C.
> \]

The inside derivative may be present only up to a constant multiplier; adjust for that constant. Useful patterns are

\[
\int [g(x)]^n g'(x)\,dx=\frac{[g(x)]^{n+1}}{n+1}+C\quad(n\ne-1),
\]

\[
\int\frac{g'(x)}{g(x)}\,dx=\ln\lvert g(x)\rvert+C\quad(g(x)\ne0),
\]

\[
\int e^{g(x)}g'(x)\,dx=e^{g(x)}+C,\qquad
\int\cos(g(x))g'(x)\,dx=\sin(g(x))+C.
\]

For a linear inside expression, its derivative is the constant \(a\), so for \(a\ne0\):

\[
\int f(ax+b)\,dx=\frac1aF(ax+b)+C,\qquad F'=f.
\]

Do not simply integrate the outside function and ignore the inside derivative. For example, \(\int\cos(3x)\,dx=\frac13\sin(3x)+C\), since \(d[\sin(3x)]/dx=3\cos(3x)\).

#### Example: cotangent

Use \(\cot x=\cos x/\sin x\), then set \(u=\sin x\). [Derivative rule: \(d(\sin x)/dx=\cos x\), so \(du=\cos x\,dx\); logarithm rule: \(\int du/u=\ln\lvert u\rvert+C\).]

\[
\begin{aligned}
\int\cot x\,dx
&=\int\frac{\cos x}{\sin x}\,dx\\
&=\int\frac1u\,du\\
&=\ln\lvert u\rvert+C\\
&=\boxed{\ln\lvert\sin x\rvert+C}.
\end{aligned}
\]

This holds on any interval where \(\sin x\ne0\); cotangent is undefined at integer multiples of \(\pi\). The absolute value allows intervals where sine is negative.

#### Example: numerator is half the inside derivative

For \(\int x/(x^2+1)\,dx\), let \(u=x^2+1\). [Power rule: \(d(x^2+1)/dx=2x\), so \(du=2x\,dx\) and \(x\,dx=\tfrac12du\); logarithm rule: \(\int du/u=\ln\lvert u\rvert+C\).]

\[
\begin{aligned}
\int\frac{x}{x^2+1}\,dx
&=\frac12\int\frac1u\,du\\
&=\frac12\ln\lvert u\rvert+C\\
&=\boxed{\frac12\ln(x^2+1)+C}.
\end{aligned}
\]

Here \(x^2+1>0\) for every real \(x\), so the absolute-value signs are unnecessary. Notice that the different integrand \(1/(1+x^2)\) has the arctangent antiderivative listed above.

### Techniques

| When you see | Use | Formula / action |
| --- | --- | --- |
| A function and its inner derivative | Substitution | Set \(u=g(x)\), so \(du=g'(x)dx\) |
| Product of two different types, e.g. \(xe^x\) | Integration by parts | \(\int u\,dv=uv-\int v\,du\) |
| Rational function \(P(x)/Q(x)\) | Partial fractions | Factor \(Q(x)\), then decompose into simpler fractions |
| Powers of trig functions | Trig identities | Convert using identities before integrating |

## Definite integrals

> [!IMPORTANT]
> **Exam formula — Fundamental Theorem of Calculus**

\[
\int_a^b f(x)\,dx=F(b)-F(a),\qquad F'(x)=f(x).
\]

Useful properties:

\[
\int_a^a f(x)\,dx=0,\qquad
\int_a^b f(x)\,dx=-\int_b^a f(x)\,dx.
\]

## Quick decision guide

- A bracket or exponent contains another function: try the **chain rule** when differentiating, or **substitution** when integrating.
- Two functions multiplied: try the **product rule** when differentiating; consider **integration by parts** when integrating.
- \(\partial/\partial x\): hold every variable except \(x\) constant.
- An indefinite integral needs \(+C\). A definite integral uses limits instead.

## Optional fuller references

For a broader downloadable cheat sheet, see [Paul’s Online Notes: Common Derivatives and Integrals](https://tutorial.math.lamar.edu/). MIT also provides structured notes on [differentiation and integration](https://ocw.mit.edu/courses/18-01-single-variable-calculus-fall-2005/pages/lecture-notes/).
