# Some Matrix Definitions

>[!Definition]
>Let $A$ be a matrix and let $U$ be the matrix obtained in row echelon form
>the **rank** of $A$ is given by the number of non-zero rows in $U$. We denote the 
>rank of a matrix by rank($A$)

>[!Definition]
>Let $A$ be an $n\times m$ matrix with rank($A$)$=r$
>The system $Ax=b$ is **<u>inconsistent</u>** (i.e. no solution) if rank($A$)$<$rank$(A|b)$
>because that means there exists at least one row with $\begin{matrix}0 & 0 & 0 & \dots & 0\mid 1\end{matrix}$
>which implies that $0=1$
>The system has a **<u>unique solution</u>** when rank$(A)=$rank$(A\mid b)=n$, in other words the system is consistent and the rank of $A$ is equal to the number of variables in the system
>The system has <u>**infinitely many solutions**</u> when the system is consistent but
>rank$(A)<n$

# What is LU decomposition?

>[!definition]
>A unit lower triangular matrix is a *square* matrix with ones on the diagonal
>
> $$\begin{bmatrix}1 & 0 & 0 & 0 \\ * & 1 & 0 & 0 \\ * & * & 1 & 0 \\ * & * & * & 1\end{bmatrix}$$
> An upper triangle matrix is the same but in the top right section

>[!theorem]
>







