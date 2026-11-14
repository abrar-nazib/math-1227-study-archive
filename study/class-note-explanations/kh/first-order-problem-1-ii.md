# KH first-order ODE notes: Problem 1(ii), every simplification

This explains Problem 1(ii) on PDF pages 1–2 of **First Order Ordinary Differentiation Equations.pdf**. The notes ask us to form a differential equation from

\[
\sqrt{1-x^2}+\sqrt{1-y^2}=a(x-y),
\]

where \(a\) is an arbitrary constant and \(y\) is a function of \(x\). The goal is an equation involving \(x,y\), and \(dy/dx\), with no \(a\). For the background meaning of a differential equation, see [Differential equations: the ground floor](../../concepts/differential-equations-foundations.md).

Think of \(a\) as a setting that picks one curve from a family. We differentiate the relation along one chosen curve, treating that setting as constant. The original and differentiated relations both contain the same \(a\); we combine them to remove it.

We work on a differentiable real branch with \(-1<x<1\) and \(-1<y<1\). In this interior region the square roots below are positive, so divisions by them are valid. Endpoints need separate analysis.

## 1. Differentiate the original equation

Write the original relation as

\[
\sqrt{1-x^2}+\sqrt{1-y^2}=a(x-y). \tag{1}
\]

Remember that \(y\) depends on \(x\), even though we write just \(y\). We need the chain rule:

\[
\frac{d}{dx}f(u(x))=f'(u(x))\frac{du}{dx},\qquad
\frac{d}{du}\sqrt{u}=\frac1{2\sqrt{u}},\qquad
\frac{d}{dx}(x^2)=2x.
\]

For the first square root:

\[
\begin{aligned}
\frac{d}{dx}\sqrt{1-x^2}
&=\frac{1}{2\sqrt{1-x^2}}\frac{d}{dx}(1-x^2)\\
&=\frac{1}{2\sqrt{1-x^2}}(-2x)\\
&=-\frac{x}{\sqrt{1-x^2}}.
\end{aligned}
\]

For the second, the inner expression depends on \(y(x)\). Applying the same chain rule, \(d(y^2)/dx=2y\,dy/dx\):

\[
\begin{aligned}
\frac{d}{dx}\sqrt{1-y^2}
&=\frac{1}{2\sqrt{1-y^2}}\frac{d}{dx}(1-y^2)\\
&=\frac{1}{2\sqrt{1-y^2}}\left(-2y\frac{dy}{dx}\right)\\
&=-\frac{y}{\sqrt{1-y^2}}\frac{dy}{dx}.
\end{aligned}
\]

The extra derivative appears because \(y\) itself changes as \(x\) changes. On the right, use \(d[a f(x)]/dx=a f'(x)\) for constant \(a\), along with \(d(x-y)/dx=1-dy/dx\):

\[
\frac{d}{dx}[a(x-y)]=a\left(1-\frac{dy}{dx}\right).
\]

Putting the pieces together:

\[
-\frac{x}{\sqrt{1-x^2}}
-\frac{y}{\sqrt{1-y^2}}\frac{dy}{dx}
=a\left(1-\frac{dy}{dx}\right). \tag{2}
\]

## 2. Remove the constant without a risky division

To make the algebra easier to see, temporarily abbreviate

\[
U=\sqrt{1-x^2},\qquad V=\sqrt{1-y^2},\qquad p=\frac{dy}{dx}.
\]

These are abbreviations, not new constants: \(U,V,p\) can all vary. In our interior region \(U>0\) and \(V>0\). Equations (1) and (2) become

\[
U+V=a(x-y), \tag{3}
\]

\[
-\frac{x}{U}-\frac{yp}{V}=a(1-p). \tag{4}
\]

The notes divide one equation by the other. Instead, multiply (3) by \((1-p)\) and (4) by \((x-y)\). Their right sides become identical, so their left sides must be equal:

\[
\begin{aligned}
(U+V)(1-p)
&=(x-y)\left(-\frac{x}{U}-\frac{yp}{V}\right),\\
(U+V)(1-p)
+(x-y)\left(\frac{x}{U}+\frac{yp}{V}\right)&=0. \tag{5}
\end{aligned}
\]

This eliminates \(a\) without dividing by \(a\), \(x-y\), or \(1-p\). Those quantities might be zero.

## 3. The missing “on simplifying” lines

Expand equation (5), one product at a time:

\[
\begin{aligned}
(U+V)-p(U+V)
+\frac{x(x-y)}{U}
+\frac{yp(x-y)}{V}&=0.
\end{aligned}
\]

Group the terms without \(p\) and those with \(p\):

\[
\left(U+V+\frac{x(x-y)}{U}\right)
+p\left(-U-V+\frac{y(x-y)}{V}\right)=0. \tag{6}
\]

Simplify the first bracket. Since \(U^2=1-x^2\),

\[
\begin{aligned}
U+V+\frac{x(x-y)}{U}
&=\frac{U^2}{U}+V+\frac{x(x-y)}{U}\\
&=\frac{U^2+x(x-y)}{U}+V\\
&=\frac{1-x^2+x^2-xy}{U}+V\\
&=\frac{1-xy}{U}+V\\
&=\frac{1-xy+UV}{U}.
\end{aligned}
\]

Now the second bracket. Since \(V^2=1-y^2\),

\[
\begin{aligned}
-U-V+\frac{y(x-y)}{V}
&=-U-\frac{V^2}{V}+\frac{y(x-y)}{V}\\
&=-U+\frac{-V^2+y(x-y)}{V}\\
&=-U+\frac{-(1-y^2)+xy-y^2}{V}\\
&=-U+\frac{-1+y^2+xy-y^2}{V}\\
&=-U+\frac{xy-1}{V}\\
&=-\frac{UV+1-xy}{V}.
\end{aligned}
\]

Both brackets contain the same expression. Call it \(K=1-xy+UV\). Substituting into (6):

\[
\begin{aligned}
\frac{K}{U}-p\frac{K}{V}&=0,\\
K\left(\frac1U-\frac{p}{V}\right)&=0.
\end{aligned}
\]

Why may we divide by \(K\)? Our domain has \(|x|<1\) and \(|y|<1\), so \(xy<1\), hence \(1-xy>0\). Also \(U,V>0\), so \(UV>0\). Therefore \(K=1-xy+UV>0\). It cannot vanish here.

\[
\begin{aligned}
\frac1U-\frac{p}{V}&=0,\\
\frac{p}{V}&=\frac1U,\\
p&=\frac{V}{U}.
\end{aligned}
\]

Replace the abbreviations:

\[
\boxed{\frac{dy}{dx}=\frac{\sqrt{1-y^2}}{\sqrt{1-x^2}}.}
\]

This is the result printed at the top of PDF page 2, now with the omitted steps shown.

## 4. A check and a subtle limitation

To check, substitute \(p=V/U\) into the left side of (4):

\[
\begin{aligned}
-\frac{x}{U}-\frac{y}{V}\left(\frac{V}{U}\right)
&=-\frac{x}{U}-\frac{y}{U}\\
&=-\frac{x+y}{U}.
\end{aligned}
\]

From (3), and because \(x\ne y\) for any point of the original family in this interior region (its left side is positive),

\[
a=\frac{U+V}{x-y}.
\]

Also, \(U^2-V^2=y^2-x^2=-(x-y)(x+y)\), so

\[
\begin{aligned}
a(1-p)
&=\frac{U+V}{x-y}\left(1-\frac{V}{U}\right)\\
&=\frac{(U+V)(U-V)}{U(x-y)}\\
&=\frac{U^2-V^2}{U(x-y)}\\
&=\frac{-(x-y)(x+y)}{U(x-y)}\\
&=-\frac{x+y}{U}.
\end{aligned}
\]

Both sides of (4) agree. The formed differential equation gives a **necessary** relation for the original family in the stated region; eliminating a parameter can introduce extra curves. For instance, \(y=x\) satisfies the formed differential equation in the interior, but cannot satisfy the original equation there because the original left side is positive while its right side is zero. Thus do not assume every solution of the formed equation belongs to the original family.
