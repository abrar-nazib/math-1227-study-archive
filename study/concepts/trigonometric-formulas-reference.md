# Trigonometric Formulas: Quick Reference

Use this page when a trigonometric expression appears in a parameterization or an integral. First identify its shape: a square, a product, a sum/difference, or a double angle.

## 1. The basic relationships

> [!IMPORTANT]
> **Exam formula — Pythagorean identity**

\[
\sin^2\theta+\cos^2\theta=1.
\]

For example,

\[
\begin{aligned}
1-\sin^2\theta
&=\sin^2\theta+\cos^2\theta-\sin^2\theta\\
&=\cos^2\theta.
\end{aligned}
\]

The related quotient identities are

\[
\tan\theta=\frac{\sin\theta}{\cos\theta},
\qquad
1+\tan^2\theta=\sec^2\theta,
\qquad
1+\cot^2\theta=\cosec^2\theta.
\]

## 2. Double-angle formulas

“Double angle” means the input is \(2\theta\), twice the original angle. Use these for expressions with \(\sin\theta\cos\theta\), \(\cos^2\theta-\sin^2\theta\), or squares.

> [!IMPORTANT]
> **Exam formulas — double-angle identities**

\[
\sin2\theta=2\sin\theta\cos\theta,
\]

\[
\cos2\theta=\cos^2\theta-\sin^2\theta,
\]

\[
\cos2\theta=2\cos^2\theta-1,
\qquad
\cos2\theta=1-2\sin^2\theta.
\]

The three forms of \(\cos2\theta\) are equal. Choose the one that matches the expression already present.

### The two identities used in 2024 Q1(c)

The line-integral expression was

\[
\cos^2\theta-\sin^2\theta-\sin\theta\cos\theta.
\]

Apply the first two double-angle formulas separately:

\[
\begin{aligned}
\cos^2\theta-\sin^2\theta
&=\cos2\theta,\\
\sin\theta\cos\theta
&=\frac12\sin2\theta
&&\text{[Divide both sides of \(\sin2\theta=2\sin\theta\cos\theta\) by \(2\).]}
\end{aligned}
\]

Therefore

\[
\cos^2\theta-\sin^2\theta-\sin\theta\cos\theta
=\cos2\theta-\frac12\sin2\theta.
\]

The exact identity is

\[
\boxed{\cos^2\theta-\sin^2\theta=\cos2\theta.}
\]

It is not “\(\cos2\theta-\sin2\theta=\cos2\theta\).” The small raised \(2\) in \(\cos^2\theta\) means “square the value of \(\cos\theta\).” The \(2\theta\) in \(\cos2\theta\) means “take cosine at the doubled angle.”

## 3. Power-reduction formulas

When integrating a square such as \(\sin^2\theta\) or \(\cos^2\theta\), use these to remove the square:

> [!IMPORTANT]
> **Exam formulas — power reduction**

\[
\sin^2\theta=\frac{1-\cos2\theta}{2},
\qquad
\cos^2\theta=\frac{1+\cos2\theta}{2}.
\]

Example:

\[
\begin{aligned}
\int\cos^2\theta\,d\theta
&=\int\frac{1+\cos2\theta}{2}\,d\theta\\
&=\frac12\int1\,d\theta+\frac12\int\cos2\theta\,d\theta\\
&=\frac\theta2+\frac12\left(\frac12\sin2\theta\right)+C
&&\text{[Formulas: \(\int1\,d\theta=\theta+C\), \(\int\cos(a\theta)\,d\theta=\sin(a\theta)/a+C\).]}\\
&=\frac\theta2+\frac{\sin2\theta}{4}+C.
\end{aligned}
\]

## 4. Sum and difference formulas

> [!IMPORTANT]
> **Exam formulas — sine and cosine of a sum or difference**

\[
\sin(A+B)=\sin A\cos B+\cos A\sin B,
\]

\[
\sin(A-B)=\sin A\cos B-\cos A\sin B,
\]

\[
\cos(A+B)=\cos A\cos B-\sin A\sin B,
\]

\[
\cos(A-B)=\cos A\cos B+\sin A\sin B.
\]

Putting \(A=B=\theta\) in the sine-sum formula gives

\[
\begin{aligned}
\sin(\theta+\theta)
&=\sin\theta\cos\theta+\cos\theta\sin\theta\\
&=2\sin\theta\cos\theta,\\
\sin2\theta&=2\sin\theta\cos\theta.
\end{aligned}
\]

## 5. Product-to-sum formulas

Use these when a product of sine and cosine functions is difficult to integrate directly:

\[
\sin A\sin B=\frac12\big[\cos(A-B)-\cos(A+B)\big],
\]

\[
\cos A\cos B=\frac12\big[\cos(A-B)+\cos(A+B)\big],
\]

\[
\sin A\cos B=\frac12\big[\sin(A+B)+\sin(A-B)\big].
\]

The special case \(A=B=\theta\) in the last formula gives

\[
\begin{aligned}
\sin\theta\cos\theta
&=\frac12\big[\sin2\theta+\sin0\big]\\
&=\frac12\sin2\theta,
\end{aligned}
\]

because \(\sin0=0\).

## 6. Common exact values

| \(\theta\) | \(0\) | \(\pi/6\) | \(\pi/4\) | \(\pi/3\) | \(\pi/2\) |
| --- | --- | --- | --- | --- | --- |
| \(\sin\theta\) | \(0\) | \(1/2\) | \(\sqrt2/2\) | \(\sqrt3/2\) | \(1\) |
| \(\cos\theta\) | \(1\) | \(\sqrt3/2\) | \(\sqrt2/2\) | \(1/2\) | \(0\) |
| \(\tan\theta\) | \(0\) | \(1/\sqrt3\) | \(1\) | \(\sqrt3\) | undefined |

For angles in other quadrants, use the signs below:

| Quadrant | I | II | III | IV |
| --- | --- | --- | --- | --- |
| \(\sin\theta\) | positive | positive | negative | negative |
| \(\cos\theta\) | positive | negative | negative | positive |
| \(\tan\theta\) | positive | negative | positive | negative |

## 7. Derivatives and integrals frequently used with these identities

> [!IMPORTANT]
> **Exam formulas — basic trigonometric differentiation and integration**

\[
\frac{d}{d\theta}(\sin\theta)=\cos\theta,
\qquad
\frac{d}{d\theta}(\cos\theta)=-\sin\theta,
\]

\[
\int\sin\theta\,d\theta=-\cos\theta+C,
\qquad
\int\cos\theta\,d\theta=\sin\theta+C.
\]

When the angle is \(a\theta\), use the chain rule in differentiation and reverse it in integration:

\[
\frac{d}{d\theta}\big[\sin(a\theta)\big]=a\cos(a\theta),
\qquad
\int\cos(a\theta)\,d\theta=\frac{\sin(a\theta)}{a}+C
\quad(a\ne0),
\]

\[
\frac{d}{d\theta}\big[\cos(a\theta)\big]=-a\sin(a\theta),
\qquad
\int\sin(a\theta)\,d\theta=-\frac{\cos(a\theta)}{a}+C
\quad(a\ne0).
\]

## 8. Fast choice guide

| If you see... | First try... |
| --- | --- |
| \(\sin^2\theta+\cos^2\theta\) | Replace it by \(1\). |
| \(\cos^2\theta-\sin^2\theta\) | Replace it by \(\cos2\theta\). |
| \(\sin\theta\cos\theta\) | Replace it by \(\tfrac12\sin2\theta\). |
| \(\sin^2\theta\) or \(\cos^2\theta\) inside an integral | Use a power-reduction formula. |
| \(\sin A\cos B\), \(\sin A\sin B\), or \(\cos A\cos B\) inside an integral | Consider a product-to-sum formula. |
