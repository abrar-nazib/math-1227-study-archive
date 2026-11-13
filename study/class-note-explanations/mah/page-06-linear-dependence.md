# MAH notes, page 6: linear dependence

For the background on vectors and the dependence test, read [linear independence of vectors](../../concepts/vectors-and-planes.md#6-linear-independence-of-vectors).


Page 6 of **Math MAH Notes** gives the vectors

\[
\begin{aligned}
\vec r_1&=2\hat i-\hat j+\hat k,\\
\vec r_2&=\hat i+3\hat j-2\hat k,\\
\vec r_3&=-2\hat i+\hat j-3\hat k,\\
\vec r_4&=3\hat i+2\hat j+5\hat k.
\end{aligned}
\]

The page is testing one simple idea: can \(\vec r_4\) be made by mixing the first three arrows? If it can, it gives no new direction. The set is then linearly dependent.

The notes write this as

\[
\vec r_4=\alpha_1\vec r_1+\alpha_2\vec r_2+\alpha_3\vec r_3.
\]

Here \(\alpha_1,\alpha_2,\alpha_3\) are ordinary numbers, called **scalars**. Think of them as knobs: each knob says how much to stretch a vector, and a negative setting reverses it.

Substitute the component forms, without combining anything yet:

\[
\begin{aligned}
3\hat i+2\hat j+5\hat k
&=\alpha_1(2\hat i-\hat j+\hat k)
+\alpha_2(\hat i+3\hat j-2\hat k)
+\alpha_3(-2\hat i+\hat j-3\hat k).
\end{aligned}
\]

Now collect the \(\hat i\), \(\hat j\), and \(\hat k\) parts separately:

\[
\begin{aligned}
3\hat i+2\hat j+5\hat k
={}&(2\alpha_1+\alpha_2-2\alpha_3)\hat i\\
&+(-\alpha_1+3\alpha_2+\alpha_3)\hat j\\
&+(\alpha_1-2\alpha_2-3\alpha_3)\hat k.
\end{aligned}
\]

The vectors \(\hat i\), \(\hat j\), and \(\hat k\) point in three independent coordinate directions. Therefore two vectors written in this basis are equal only when their matching components are equal. This is what the handwritten note means by “\(\hat i,\hat j,\hat k\) are non-coplanar.” Equate the three components:

\[
\begin{aligned}
2\alpha_1+\alpha_2-2\alpha_3&=3,\\
-\alpha_1+3\alpha_2+\alpha_3&=2,\\
\alpha_1-2\alpha_2-3\alpha_3&=5.
\end{aligned}
\]

### How are the scalars found?

They are found by solving those three simultaneous equations. The handwritten notes skip that calculation; the values are not chosen by intuition. Let us eliminate one unknown at a time.

Add the second equation to the third. Their \(\alpha_1\) terms cancel:

\[
\begin{aligned}
(-\alpha_1+3\alpha_2+\alpha_3)
+(\alpha_1-2\alpha_2-3\alpha_3)&=2+5,\\
\alpha_2-2\alpha_3&=7. \tag{4}
\end{aligned}
\]

Add twice the second equation to the first. Again \(\alpha_1\) cancels:

\[
\begin{aligned}
(2\alpha_1+\alpha_2-2\alpha_3)
+2(-\alpha_1+3\alpha_2+\alpha_3)&=3+2(2),\\
2\alpha_1+\alpha_2-2\alpha_3-2\alpha_1+6\alpha_2+2\alpha_3&=7,\\
7\alpha_2&=7,\\
\alpha_2&=1.
\end{aligned}
\]

Substitute \(\alpha_2=1\) into equation (4):

\[
\begin{aligned}
1-2\alpha_3&=7,\\
-2\alpha_3&=6,\\
\alpha_3&=-3.
\end{aligned}
\]

Finally substitute both values into the third original equation:

\[
\begin{aligned}
\alpha_1-2(1)-3(-3)&=5,\\
\alpha_1-2+9&=5,\\
\alpha_1+7&=5,\\
\alpha_1&=-2.
\end{aligned}
\]

Thus the scalars in the notes are

\[
\alpha_1=-2,\qquad \alpha_2=1,\qquad \alpha_3=-3.
\]

Check each coordinate, rather than merely trusting the solved values:

\[
\begin{aligned}
2\alpha_1+\alpha_2-2\alpha_3
&=2(-2)+1-2(-3)\\
&=-4+1+6\\
&=3,\\[4pt]
-\alpha_1+3\alpha_2+\alpha_3
&=-(-2)+3(1)+(-3)\\
&=2+3-3\\
&=2,\\[4pt]
\alpha_1-2\alpha_2-3\alpha_3
&=-2-2(1)-3(-3)\\
&=-2-2+9\\
&=5.
\end{aligned}
\]

So the complete relation is

> [!IMPORTANT]
> **MAH page 6 result**
>
> \[
> \vec r_4=-2\vec r_1+\vec r_2-3\vec r_3.
> \]

That one equation is enough to settle the question: \(\vec r_4\) can be assembled from the other three vectors, so the four vectors are **linearly dependent**. Written in the formal “combination equals zero” test, move everything to one side:

\[
2\vec r_1-\vec r_2+3\vec r_3+\vec r_4=\vec0.
\]

The coefficients \(2,-1,3,1\) are not all zero. That is exactly the required evidence of linear dependence.

### A small correction to the top diagram on that page

The determinant statement is correct when \(\vec A,\vec B,\vec C\) are the **position vectors from the origin**:

\[
\det\begin{pmatrix}
a_1&a_2&a_3\\
b_1&b_2&b_3\\
c_1&c_2&c_3
\end{pmatrix}=0
\]

means the three vectors are linearly dependent, equivalently they lie in one plane **through the origin**. The phrase “the points \(A,B,C\) are coplanar” by itself is not useful here: any three ordinary points always lie in at least one plane. What matters is that their position vectors and the origin lie in one common plane.
