# Matrix rank, echelon form, and normal form

This is the foundation for 2024 Q6(a). Read [Matrix adjoint, symmetry, and Hermitian matrices](matrix-adjoint-symmetry-and-hermitian.md) first if matrix rows, columns, or transpose are unfamiliar.

## 1. What rank is trying to measure

A matrix can contain rows that do not add genuinely new information. For example, the row \((2,4,6)\) says exactly the same directional information as \((1,2,3)\): it is just twice that row. It is **dependent** on the first row.

The **rank** counts the number of independent directions of information in the matrix. Imagine each row as an instruction. If one instruction can be built from earlier instructions, it does not increase rank. Row reduction exposes those redundant rows as zero rows.

> [!IMPORTANT]
> **Exam definition — rank**
>
> The rank of a matrix is the number of linearly independent rows (equivalently, columns). It is also the number of nonzero rows in row-echelon form, or the number of leading \(1\)s in normal form.

For example,

\[
\begin{pmatrix}1&2&3\\2&4&6\\0&1&1\end{pmatrix}
\xrightarrow{R_2\to R_2-2R_1}
\begin{pmatrix}1&2&3\\0&0&0\\0&1&1\end{pmatrix}.
\]

Only two nonzero independent rows remain, so its rank is \(2\).

## 2. Elementary operations: safe simplifications

An **elementary row operation** changes the way the same row information is written; it does not change rank. The matching statement holds for elementary column operations.

> [!IMPORTANT]
> **Exam rules — elementary operations**
>
> \[
> R_i\leftrightarrow R_j,\qquad
> R_i\to cR_i\ (c\ne0),\qquad
> R_i\to R_i+cR_j.
> \]
>
> The same three operations are valid with \(C\) in place of \(R\).

- Swapping only changes order.
- Multiplying by a nonzero constant changes the scale, not the direction represented by that row.
- Adding a multiple of one row to another is reversible: subtract that multiple again to undo it.

This reversibility is why such operations preserve the number of independent directions.

## 3. Pivot and row-echelon form

A **pivot** is the first nonzero entry in a nonzero row after reduction. In **row-echelon form**, pivots move to the right as you go down, and every entry below a pivot is zero. Any all-zero rows sit at the bottom.

For instance,

\[
\begin{pmatrix}
1&-1&-2&-4\\
0&5&3&7\\
0&0&33&22\\
0&0&0&0
\end{pmatrix}
\]

is in echelon form. It has three pivots, hence rank \(3\). You can already read rank at this point.

## 4. Normal form

For an \(m\times n\) matrix of rank \(r\), elementary row **and column** operations can reduce it to

> [!IMPORTANT]
> **Exam form — normal form of a rank-\(r\) matrix**
>
> \[
> \begin{pmatrix}I_r&0\\0&0\end{pmatrix}.
> \]
>
> \(I_r\) is the \(r\times r\) identity matrix.

For Q6(a), the target is \(\operatorname{diag}(1,1,1,0)\). The first three pivot columns represent the three independent directions; the final zero row and column contain no fourth independent direction.

### Echelon form versus normal form

- **Echelon form** uses row operations and is enough to count rank.
- **Normal form** uses row and column operations and has an identity block plus zeros. It is what Q6(a) explicitly asks for.

Do not confuse normal form with reduced row-echelon form. RREF uses rows only and can retain nonzero entries in non-pivot columns. Normal form clears those with column operations too.

## 5. Practical Q6(a) plan

1. Make a convenient first pivot, often by swapping a row containing \(1\) upward.
2. Zero entries below it using row operations.
3. Repeat for the next pivot columns until zero rows appear at the bottom.
4. Scale pivots to \(1\) and clear entries above them to reach RREF-like form.
5. Use column operations to clear remaining non-pivot columns and obtain normal form.
6. Count the identity entries: that count is the rank.

### Common mistakes

- A zero determinant only says a square matrix does not have full rank; it does not by itself tell you the exact rank.
- Never divide a row by zero.
- Keep a row operation applied to every entry in that row, not just the coefficient entries you are watching.
- Do not stop at echelon form when the question specifically says “reduce into normal form.”
