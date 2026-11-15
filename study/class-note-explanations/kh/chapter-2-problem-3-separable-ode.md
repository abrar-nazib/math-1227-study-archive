# KH Chapter 2, Problem 3: a separable ODE

The question on PDF page 4 asks us to solve

\[
\frac{dy}{dx}=\frac{1+y^2}{1+x^2}.
\]

Here \(y\) is an unknown function of \(x\), and \(dy/dx\) is its derivative. The fraction on the right is a product of a function of \(y\) and a function of \(x\), so we can **separate variables**: put the \(y\)-part with \(dy\), and the \(x\)-part with \(dx\). For the background on separable equations, see [the ODE foundations](../../concepts/differential-equations-foundations.md); the inverse-tangent integration rule is in the [calculus reference](../../concepts/differentiation-and-integration-reference.md).

## Before looking at the answer

Try these moves: divide both sides by \(1+y^2\); integrate both sides; then find a way to remove the inverse tangents. Keep the first integrated equation, because it remains valid even where a later fraction is undefined.

## 1. Separate the variables

Begin with the equation and divide both sides by \(1+y^2\):

\[
\begin{aligned}
\frac{dy}{dx}&=\frac{1+y^2}{1+x^2},\\
\frac{1}{1+y^2}\frac{dy}{dx}
&=\frac{1}{1+x^2}.
\end{aligned}
\]

This division is safe for real \(y\): \(1+y^2\ge1\), so it is never zero. In differential notation we write

\[
\boxed{\frac{dy}{1+y^2}=\frac{dx}{1+x^2}.}
\]

This is shorthand for the preceding derivative equation: it groups the \(y\)-dependent expression with \(dy\) and the \(x\)-dependent one with \(dx\).

## 2. Integrate both sides

The rule being applied is

\[
\int\frac{du}{1+u^2}=\tan^{-1}u+C,
\qquad
\frac{d}{du}(\tan^{-1}u)=\frac1{1+u^2}.
\]

The notation \(\tan^{-1}u\) means **arctangent**, the angle whose tangent is \(u\); it does not mean \(1/\tan u\). Integrating gives

\[
\begin{aligned}
\int\frac{dy}{1+y^2}&=\int\frac{dx}{1+x^2},\\
\tan^{-1}y+C_1&=\tan^{-1}x+C_2,\\
\tan^{-1}y-\tan^{-1}x&=C_2-C_1.
\end{aligned}
\]

The difference of two arbitrary constants is another arbitrary constant; call it \(K\):

\[
\boxed{\tan^{-1}y-\tan^{-1}x=K.} \tag{A}
\]

This is already a complete implicit general solution on any interval where \(y(x)\) is real and differentiable. It tells us that the difference between two angles remains constant along a solution curve. No initial condition was given, so we cannot find a numerical value for \(K\).

## 3. Why do the notes introduce another constant?

The notes write the angle constant as \(\tan^{-1}c\). That makes a later step neat because its tangent is \(c\). More generally, start with \(K\), and when \(\cos K\ne0\), define

\[
c=\tan K.
\]

Apply tangent to both sides of (A). Use the identity

\[
\tan(\alpha-\beta)
=\frac{\tan\alpha-\tan\beta}{1+\tan\alpha\tan\beta},
\]

where the displayed denominator is nonzero. With \(\alpha=\tan^{-1}y\), \(\beta=\tan^{-1}x\), we have \(\tan\alpha=y\) and \(\tan\beta=x\). Thus

\[
\begin{aligned}
\tan(\tan^{-1}y-\tan^{-1}x)&=\tan K,\\
\frac{\tan(\tan^{-1}y)-\tan(\tan^{-1}x)}
{1+\tan(\tan^{-1}y)\tan(\tan^{-1}x)}&=c,\\
\frac{y-x}{1+xy}&=c,\\
y-x&=c(1+xy),\\
\boxed{y&=x+c(1+xy).} \tag{B}
\end{aligned}
\]

This is the expression in the class notes, for finite \(c\). Note that \(K\) and \(c\) are different constants: \(K\) is an angle, and \(c\) is its tangent. The class notes' step using an inverse-tangent subtraction identity needs branch care; taking the tangent as above avoids claiming that inverse tangents always subtract without a possible multiple of \(\pi\).

### If you want \(y\) by itself

Starting from (B), distribute and collect the terms containing \(y\):

\[
\begin{aligned}
y&=x+c+cxy,\\
y-cxy&=x+c,\\
y(1-cx)&=x+c,\\
\boxed{y&=\frac{x+c}{1-cx}}\qquad(1-cx\ne0).
\end{aligned}
\]

The denominator restriction matters: a particular solution is taken on an interval that does not cross a point where its denominator vanishes.

## 4. The case missed by the notes

When \(\cos K=0\), \(\tan K\) is not a finite number, so the substitution \(c=\tan K\) does not cover that case. Equation (A) still covers it. Equivalently, using \(\cos(\alpha-\beta)=\cos\alpha\cos\beta+\sin\alpha\sin\beta\), the condition \(\cos K=0\) yields

\[
\begin{aligned}
\cos(\tan^{-1}y-\tan^{-1}x)&=0,\\
\frac{1+xy}{\sqrt{1+y^2}\sqrt{1+x^2}}&=0,\\
1+xy&=0,\\
\boxed{y&=-\frac1x}\qquad(x\ne0).
\end{aligned}
\]

Why does the numerator become \(1+xy\)? For \(\alpha=\tan^{-1}y\), \(\cos\alpha=1/\sqrt{1+y^2}\) and \(\sin\alpha=y/\sqrt{1+y^2}\); use the corresponding formulas for \(\beta=\tan^{-1}x\), then add the two products.

The class notes divide by \(1+xy\), so they cannot retain this case. The separate solution is valid on an interval entirely in \(x>0\) or entirely in \(x<0\). The earlier implicit equation (A) captures both it and the finite-\(c\) solutions; the value of \(K\) need not be the same on disconnected intervals.

## 5. Check by substitution

For the finite-\(c\) family \(y=(x+c)/(1-cx)\), use the quotient rule

\[
\frac{d}{dx}\left(\frac{u}{v}\right)
=\frac{vu'-uv'}{v^2}.
\]

Here \(u=x+c\), \(v=1-cx\), \(u'=1\), and \(v'=-c\), because \(c\) is constant. Therefore

\[
\begin{aligned}
\frac{dy}{dx}
&=\frac{(1-cx)(1)-(x+c)(-c)}{(1-cx)^2}\\
&=\frac{1-cx+cx+c^2}{(1-cx)^2}\\
&=\frac{1+c^2}{(1-cx)^2}.
\end{aligned}
\]

Now calculate the original right side:

\[
\begin{aligned}
\frac{1+y^2}{1+x^2}
&=\frac{1+\left(\frac{x+c}{1-cx}\right)^2}{1+x^2}\\
&=\frac{(1-cx)^2+(x+c)^2}{(1-cx)^2(1+x^2)}\\
&=\frac{1-2cx+c^2x^2+x^2+2cx+c^2}{(1-cx)^2(1+x^2)}\\
&=\frac{1+c^2+x^2+c^2x^2}{(1-cx)^2(1+x^2)}\\
&=\frac{(1+c^2)(1+x^2)}{(1-cx)^2(1+x^2)}\\
&=\frac{1+c^2}{(1-cx)^2}.
\end{aligned}
\]

The two sides match. For the missing case, [power rule: \(d(x^n)/dx=nx^{n-1}\)]

\[
\begin{aligned}
\frac{d}{dx}\left(-\frac1x\right)
&=\frac{d}{dx}(-x^{-1})\\
&=x^{-2}\\
&=\frac1{x^2},
\end{aligned}
\]

and

\[
\begin{aligned}
\frac{1+y^2}{1+x^2}
&=\frac{1+1/x^2}{1+x^2}\\
&=\frac{(x^2+1)/x^2}{1+x^2}\\
&=\frac1{x^2}.
\end{aligned}
\]

It therefore satisfies the original ODE wherever \(x\ne0\).
