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
>Let $E$ be the $m\times m$ matrix with ones along the diagonal, $c$ in the entry row at $i$ and column $j$ with $i>j$ and all other entries are zeros
>$$E=\begin{bmatrix}1 &  &  &  &  \\  & \dots &  &  &  \\
 &  & \dots &  &  \\
  \\  & c & & \dots  &  \\  &  &  &  & 1\end{bmatrix}$$
  >Then for any $m\times n$ matrix $A$, matrix multiplication $EA$ applies to $A$ the elementary row row operation: add $c$ times row $j$ to $i$
  >$\\$
  >Furthermore, the inverse of $E$ is given by
>$$E^{-1}=\begin{bmatrix}1 &  &  &  &  \\  & \dots &  &  &  \\
 &  & \dots &  &  \\
  \\  & -c & & \dots  &  \\  &  &  &  & 1\end{bmatrix}$$
>Where $-c$ is the entry at row $i$ and column $j$.

>[!example]
>Consider the following matrix
>$A=\begin{bmatrix} 1 & -1 & 1 & -2  \\ -1 & 1 & 1 & 1 \\ -1 & 2 & 3 & 1 \\ 1 & -1 & 2 & 1\end{bmatrix}$
>The elementary matrix which adds $-1$ times row $1$ to row $4$ is the following
>$\\$
>Perform matrix multiplication to verify
>$EA=\begin{bmatrix}1 & -1 & 1 & -2 \\ -1 & 1 & 1 & 1 \\ -1 & 2 & 3 & 1 \\ 0 & 0 & 1 & 3\end{bmatrix}$

>[!theorem]
>If $A$ can be reduced by Gaussian elimination to row echelon form _only_ with operations "add $c$ times row $j$ to row $i$" (in other words, without scaling rows and without interchanging rows), then $A$ has an <b> LU decomposition </b> of the form
>$$A=LU$$
>Where $L$ is a unit lower triangular matrix. In particular, after performing Gaussian elimination on $A$, the matrix $U$ is the corresponding row echelon form of $A$ and $L$ is given by
>$$L=\begin{bmatrix}1 &  &  &  &  \\ -c_{2,1} & 1 &  &  &  \\ -c_{3,1} & -c_{3,2} & 1 &  &  \\ \dots & \dots & \dots & \dots &  \\ -c_{m,1} & -c_{m,2} & \dots & -c_{m,m-1} & 1\end{bmatrix}$$
>where each entry corresponds to the elementary row operation add "$c_{i,j}$ times row $j$ to row $i$" performed during Gaussian elemintation

>[!example]
>Compute the **LU** decomposition of 
>$$A=\begin{bmatrix}2 & 1 & 1 \\ 2 & 0 & 2 \\ 4 & 3 & 4\end{bmatrix}$$
>Add $-1$ times row $1$ to row $2$ and add $-2$ times row $1$ to row $3$
>$$\begin{bmatrix}2 & 1 & 1 \\ 2 & 0 & 2 \\ 4 & 3 & 4\end{bmatrix}\to \begin{bmatrix}2 & 1 & 1 \\ 0 & -1 & 1 \\ 0 & 1 & 2\end{bmatrix}$$
>Add row $2$ to row $3$ to get the following
>$$\begin{bmatrix}2 & 1 & 1 \\ 0 & -1 & 1 \\ 0 & 1 & 2\end{bmatrix}\to \begin{bmatrix}2 & 1 & 1 \\ 0 & -1 & 1 \\ 0 & 0 & 3\end{bmatrix}$$
>In terms of elementary matrices we have just shown that 
>$$E_{3,2}E_{3,1}E_{2,1}A=U$$
>$$\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 1 & 1\end{bmatrix}\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ -2 & 0 & 1\end{bmatrix}\begin{bmatrix}1 & 0 & 0 \\ -1 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}\begin{bmatrix}2 & 1 & 1 \\ 2 & 0 & 2 \\ 4 & 3 & 4\end{bmatrix}=\begin{bmatrix}2 & 1 & 1 \\ 0 & -1 & 1 \\ 0 & 0 & 3\end{bmatrix}$$
>We can rearrange the system to get $A=E^{-1}_{2,1}E_{3,1}^{-1}E^{-1}_{3,2}U$
>$$\begin{bmatrix}2 & 1 & 1 \\ 2 & 0 & 2 \\ 4 & 3 & 4\end{bmatrix}=\begin{bmatrix}1 & 0 & 0 \\ 1 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ 2 & 0 & 1\end{bmatrix}\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & -1 & 1\end{bmatrix}\begin{bmatrix}2 & 1 & 1 \\ 0 & -1 & 1 \\ 0 & 0 & 3\end{bmatrix}$$
>We can combine the matrices as in the proof of the **LU** decomposition to find $A=LU$
>$$\begin{bmatrix}2 & 1 & 1 \\ 2 & 0 & 2 \\ 4 & 3 & 4\end{bmatrix}=\begin{bmatrix}1 & 0 & 0 \\ 1 & 1 & 0 \\ 2 & -1 & 1\end{bmatrix}\begin{bmatrix}2 & 1 & 1 \\ 0 & -1 & 1 \\ 0 & 0 & 3\end{bmatrix}$$
>Note that we can construct the matrix $L$ directly from the list of operations
>1. Add $-1$ times row $1$ to row $2$
>2. Add $-2$ times row $1$ to row $3$
>3. Add $1$ times row $2$ to row $3$


>[!theorem]
>Suppose $A$ has an **LU** decomposition $A=LU$
>1. $\text{rank}(A)=\text{rank}(U)$
>2. det$(A)=$det$(U)=u_{1,1}\dots u_{m,m}$ which are the diagonal entries of $U$
>Note not all matrices have na **LU** decomposition. For example,
>$$A=\begin{bmatrix}0 & 1  \\ 1 & 0\end{bmatrix}$$
>does not  have an **LU** decomposition, why? However if we allow partial pivoting (ie. interchanging rows during Gaussian elimination), then Gaussian elimination with partial pivoting computes for *any* matrix $A$
