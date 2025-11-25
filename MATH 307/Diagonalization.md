__Big Idea__: An $n\times n$ matrix $A$ is diagonalizable iff $A$ has $n$ linearly independent eigenvectors
If a matrix $A$ is real and symmetric then it is diagonalizable
The eigenvalues are real numbers and the eigenvectors are orthogonal

# Eigenvalues and Eigenvectors

>[!definition]
>A eigenvalue of a matrix $A$ is a number $\lambda$ such that $A\boldsymbol{v}=\lambda \boldsymbol{v}$
>for some nonzero vector $\boldsymbol{v}$, this vector is an eigenvector for the eigenvalue $\lambda$
>Eigenvalues of a real matrix may be real or complex numbers

If $\lambda$ is an eigenvalue of $A$ with eigenvector $\boldsymbol{v}$ then $(A-\lambda I)\boldsymbol{v}=\boldsymbol{0}$ 
This implies that $A-\lambda I$ is not invertible and $\det(A-\lambda I)=0$

This suggests that to find eigenvalues and eigenvectors of $A$ we should:
1. Find $\lambda$ such that $\det(A-\lambda I)=0$
2. Find solutions of the linear system $(A-\lambda I)\boldsymbol{v}=\boldsymbol{0}$
This works when A is a small matrix and we have done this in previous linear algebra courses
However this is impractical when $A$ is a large matrix

For example if $A$ is $5\times 5$ the we have a polynomial equation of degree $5$ and there is no formula for the roots, we will see better algorithms for computing eigenvalues in later sections

>[!definition]
>Let $A$ be an $n\times n$ matrix
>The characteristic polynomial of $A$ is $c_{A}(x)=\det(A-xI)$
>The characteristic polynomial $c_{A}(x)$ has degree $n$ and the roots of are the eigenvalues
>of $A$


# Diagonalization

>[!definition]
>A matrix $A$ is diagonalizable if $\exists$ and invertible matrix $P$ and a diagonal matrix $D$ s.t. 
>$$A=PDP^{-1}$$

>[!theorem]
>If $A$ is a diagonalizable with $A=PDP^{-1}$ then diagonal entries of $D$ are eigenvalues of $A$ and the columns of $P$ are the corresponding eigenvectors
>
>>[!proof]
>>Let $\boldsymbol{v}_{1},\dots,\boldsymbol{v}_{n}$ be the columns of $P$ and let $\lambda_{1},\dots,\lambda_{n}$ be the diagonal entries of $D$
>>$$P=\begin{bmatrix} & \\\boldsymbol{v}_{1} & \dots & \boldsymbol{v}_{n} \\  & \end{bmatrix}\quad  D=\begin{bmatrix}\lambda_{1} &  &  & \\ & \ddots & \\ &  & \lambda_{n}\end{bmatrix}$$
>>matrix multiplication $AP=PD$ yields the equation
>>$$A\begin{bmatrix} & \\\boldsymbol{v}_{1} & \dots & \boldsymbol{v}_{n}\\ & \end{bmatrix}=\begin{bmatrix} & \\ \lambda_{1}\boldsymbol{v}_{1} & \dots & \lambda_{n}\boldsymbol{v}_{n}\\ & \end{bmatrix}$$
>>Therefore $A\boldsymbol{v}_{i}=\lambda_{i}\boldsymbol{v}_{i}$ for each $i=1,\dots,n$

>[!theorem]
>If $A$ has distinct eigenvalues then $A$ is diagonalizable
>
>>[!proof]
>>Consider distinct eigenvalues and eigenvectors $\lambda_{i}\text{ and }\boldsymbol{v}_{i}$
>>Construct $P$ with eigenvectors
>>$$P=\begin{bmatrix} & \\ \boldsymbol{v}_{1} & \dots & \boldsymbol{v}_{n}\\ & \end{bmatrix}$$
>>and construct $D$ with eigenvalues
>>
>>$$D=\begin{bmatrix}\lambda_{1} &  & \\ & \ddots & \\ &  & \lambda_{n}\end{bmatrix}$$
>>Then $A=PDP^{-1}$ by construction


>[!definition]
>By the fundamental theorem of algebra, the characteristic polynomial of a matrix $A$ factors as product
>
>$$c_{A}(x)=\pm \prod_{i=1}^{k}(x-\lambda_{i})^{m_{i}} $$
>where the eigenvalues are distinct and the algebraic multiplicity of $\lambda_{i}$ is the power $m_{i}$
>In the factored characteristic polynomial.
>In other words the algebraic multiplicity i the number of times it occurs as a root of the characteristic polynomial

>[!definition]
>The geometric multiplicity of $\lambda$ is the number of linearly independent 
>eigenvectors corresponding to the eigenvalue
>In other words its the dimension of the eigenspace of $\lambda$
>
>$E_{\lambda}=N(A-\lambda I)=\{ \boldsymbol{v}\in \mathbb{R}^{n}:(A-\lambda I)\boldsymbol{v} =\boldsymbol{0}\}$


Note every matrix is diagonalizable
Consider the matrix $A=\begin{bmatrix}3 & 1 \\0 & 3\end{bmatrix}$
The only eigenvalue is $\lambda=3$ with an algebraic multiplicity of $2$ but it only has a geometric multiplicity of $1$ so $A$ does not have enough eigenvectors to be diagonalizable

>[!theorem]
>A matrix is diagonalizable if, $\forall \lambda$ the algebraic multiplicity of $\lambda$ equals the geometric multiplicity of $\lambda$


# Spectral Theorem

>[!theorem]
>All eigenvalues of a symmetric matrix are real numbers
>
>>[!proof]
>>Let $\lambda$ be an eigenvalue of a symmetric matrix $A$ with eigenvector $\boldsymbol{v}$ compute the complex inner product $\braket{ \boldsymbol{v} | A\boldsymbol{v} }=\boldsymbol{v}^{T}\overline{A\boldsymbol{v}}$ in two different ways
>>
>>First compute 
>>
>>$$\braket{ \boldsymbol{v} | A\boldsymbol{v} } =\braket{ \boldsymbol{v} | \lambda \boldsymbol{v} } =\overline{\lambda}\braket{ \boldsymbol{v} | \boldsymbol{v} } =\overline{\lambda}\|v\|^{2}$$
>>Since $A$ is real and symmetric, we have $\overline{A}^{T}=A$ and we compute
>>$$\braket{ \boldsymbol{v} | A\boldsymbol{v} } =\braket{ \overline{A}^{T}\boldsymbol{v} |\boldsymbol{v}  }=\braket{ A\boldsymbol{v} | \boldsymbol{v} } =\lambda \braket{ \boldsymbol{v} | \boldsymbol{v} } =\lambda\|\boldsymbol{v}\|^{2}$$
>>Since $\|\boldsymbol{v}\|^{2}\neq{0}$ we have $\lambda=\bar{\lambda}$ and therefore $\lambda$ is a real number


>[!theorem]
>Let $A$ be a symmetric matrix and let $\lambda_{1},\quad \lambda_{2}$ be distinct real eigenvalues of $A$ with eigenvectors $\boldsymbol{v}_1$ and $\boldsymbol{v}_{2}$ respectively, Then $\boldsymbol{v}_{1}$ and $\boldsymbol{v}_{2}$ are orthogonal
>>[!proof]
>>See the math 307 github

>[!theorem]
>Let $A$ be a symmetric matrix. Then there exists an orthogonal matrix $P$ and a diagonal matrix $D$ such that $A=PDP^{T}$ 
>In other words $A$ is orthogonally diagonalizable

