__Big Idea__ If $A$ is any $m\times n$ matrix then $AA^{T}$ and $A^{T}A$ are symmetric matrices therefore both are [[Diagonalization#Spectral Theorem |orthogonally diagonalizable]] ,
$AA^{T}=PD_{1}P^{T}$ and $A^{T}A=QD_{2}Q^{T}$ and these decompositions lead to singular value decomposition $A=P\Sigma Q^{T}$ where $\Sigma$ is a diagonal $m\times n$ matrix containing the singular values (the square roots of the eigenvalues in $D_{1}$ and $D_{2}$)

# SVD Construction

Note throughout this section __$A$ is a real $m\times n$ matrix__

>[!theorem]
>All eigenvalues of $AA^{T}$ and $A^{T}A$ are non-negative i.e. $\lambda\geq{0}$
>
>>[!proof]
>>Let $\lambda$ be an eigenvalue of $AA^{T}$ with eigenvector $\boldsymbol{p}$ Compute
>>$$\|A^{T}\boldsymbol{p}\|^{2}=\braket{ A^{T}\boldsymbol{p} | A^{T}\boldsymbol{p} } =\braket{ \boldsymbol{p} | AA^{T}\boldsymbol{p} } =\lambda \braket{ \boldsymbol{p} | \boldsymbol{p} } =\lambda\|\boldsymbol{p}\|^{2}$$
>>Since $\boldsymbol{p}$ is a nonzero vector we can write 
>>
>>$$\lambda=\frac{\|A^{T}\boldsymbol{p}\|^{2}}{\|\boldsymbol{p}\|^{2}}$$
>>therefore $\lambda$ is a real number squared and must be non-negative. The same calculation works for $A^{T}A$

>[!theorem]
>Let $\lambda$ be a positive eigenvalue of $AA^{T}$ with unit eigenvector $\boldsymbol{p}$. Then $\lambda$ is an eigenvalue of $A^{T}A$ with unit eigenvector 
>$$\boldsymbol{q}=\frac{1}{\sigma}A^{T}\boldsymbol{p},\quad \sigma=\sqrt{ \lambda }$$
>Conversely, let $\lambda$ be a positive eigenvalue of $A^{T}A$ with (unit) eigenvector $\boldsymbol{q}$. Then $\lambda$ is an eigenvalue of $AA^{T}$ with eigenvector 
>$$\boldsymbol{p}=\frac{1}{\sigma}A\boldsymbol{q},\quad  \sigma=\sqrt{ \lambda }$$
>>[!proof]
>>Compute
>>$$A^{T}A\boldsymbol{q}=\frac{1}{\sqrt{ \lambda }}A^{T}AA^{T}\boldsymbol{p}=\frac{1}{\sqrt{ \lambda }}A^{T}AA^{T}\boldsymbol{p}=\sqrt{ \lambda }A^{T\boldsymbol{p}}=\lambda \boldsymbol{q}$$
>>Therefore $\boldsymbol{q}$ is an eigenvector for $A^{T}A$ with eigenvalue $\lambda$. Now lets verify it is a unit vector, compute
>>
>>$$\|\boldsymbol{q}\|^{2}=\braket{ \boldsymbol{q} | \boldsymbol{q} } =\frac{1}{\sigma^{2}}\braket{ A^{T}\boldsymbol{p} |A^{T}\boldsymbol{p}  }=\frac{1}{\lambda}\braket{ \boldsymbol{p} | AA^{T}\boldsymbol{p} } =\braket{ \boldsymbol{p} | \boldsymbol{p} } =1 $$
>>Similar computations prove the second statement regarding $\boldsymbol{p}=\frac{1}{\sigma}A\boldsymbol{q}$

The formulas relating $\boldsymbol{p}$ and $\boldsymbol{q}$ above for $\lambda>0$ imply that the multiplicity of the eigenvalue $\lambda$ for $AA^{T}$ is equal to the multiplicity of the eigenvalue $\lambda$ for $A^{T}A$

>[!definition]
>The matrices $AA^{T}$ and $A^{T}A$ have the same set of positive eigenvalues
>Label the eigenvalues in decreasing order $\lambda_{1}\geq \lambda_{2}\geq\dots\geq \lambda _r>0$ 
>The __singular values__ of $A$ are
>$$\sigma_{i}=\sqrt{ \lambda_{i} },\quad  i=1,\dots,r$$

>[!theorem]
>$\mathcal{N}(AA^{T})=\mathcal{N}(A^{T})$ and $\mathcal{N}(A^{T}A)=\mathcal{N}(A)$
>
>>[!proof]
>>If $\boldsymbol{v}\in \mathcal{N}(A^{T})$ then we have $AA^{T}\boldsymbol{v}=A \boldsymbol{0}=0$ which implies that $\mathcal{N}(A^{T})\subset \mathcal{N}(AA^{T})$
>>
>>If $\boldsymbol{v}\in \mathcal{N}(AA^{T})$ then we have that $\|A^{T}\boldsymbol{v}\|^{2}=\braket{ A^{T}\boldsymbol{v} | A^{T}\boldsymbol{v} }=\braket{ \boldsymbol{v} | AA^{T}\boldsymbol{v} }=0$
>Therefore $A^{T}\boldsymbol{v}=\boldsymbol{0}\quad\boldsymbol{v}\in \mathcal{N}(A^{T})$ so the [[Subspaces#Nullspace and Range|nullspaces]] are equal
>>
>>Similar calculations can prove the second identity

>[!theorem]
>Let the singular values of $A$ be $\sigma_{1}\geq \sigma_{2}\geq\dots\geq \sigma _{r}>{0}$. 
>There exists matrices $Q$ and $P$ such that
>
>$$A=P\Sigma Q^{T}\quad  \text{where}\quad 
\Sigma =
\left[
\begin{array}{ccc|c}
\sigma_1 & & & \\
& \ddots & & \boldsymbol{0} \\
& & \sigma_r & \\ \hline
& \boldsymbol{0} & & \boldsymbol{0}
\end{array} \right]_{m \times n}$$
>>[!proof]
>>Look on math 307 github


>[!definition]
>The equation $A=P\Sigma Q^{T}$ is the singular value decomposition
>- The diagonal entries of $\Sigma$ are the singular values
>- The columns of $P$ are the left singular vectors
>- The columns of $Q$ are the right singular vectors

In the construction of the SVD we may choose to calculate $P$ or $Q$ first
The connections between the columns for $i=1,\dots r$ is given by 

$$\boldsymbol{q}_{i}=\frac{1}{\sigma_{i}}A^{T}\boldsymbol{p}_{i}\quad A^{T}A\boldsymbol{q}_{i}=\sigma_{i}^{2}\boldsymbol{q}_{i}\quad  \|\boldsymbol{q}_{i}\|^{2}=1$$
$$\boldsymbol{p}_{i}=\frac{1}{\sigma_{i}}A^{}\boldsymbol{q}_{i}\quad AA^{T}\boldsymbol{p}_{i}=\sigma_{i}^{2}\boldsymbol{p}_{i}\quad  \|\boldsymbol{p}_{i}\|^{2}=1$$
>[!example]
>Construct the SVD for $A=\begin{bmatrix}1 & 1\\1 & -1\\0 & 1\end{bmatrix}$

$A^{T}A^{}=\begin{bmatrix}2 & 0\\0 & 3\end{bmatrix}$
So the singular values are $\sqrt{ 2 },\sqrt{ 3 }$
$\boldsymbol{q}_{1}=\begin{bmatrix}0\\1\end{bmatrix}\quad \boldsymbol{q}_{2}=\begin{bmatrix}1\\0\end{bmatrix}$
So $Q=\begin{bmatrix}0 & 1\\1 & 0\end{bmatrix}$
Now we make matrix $P$

$\boldsymbol{p}_{1}=\frac{1}{\sqrt{ 3 }}A\begin{bmatrix}0\\1\end{bmatrix}=\frac{1}{\sqrt{ 3 }}\begin{bmatrix}1\\-1\\1\end{bmatrix}\quad \quad \boldsymbol{p}_{2}=\frac{1}{\sqrt{ 2 }}A\boldsymbol{q}_{2}=\frac{1}{\sqrt{ 2 }}\begin{bmatrix}1\\1\\0\end{bmatrix}$
We must find the last eigenvector, we know it is orthonormal to both of the others
so we can set up a linear equation

$$\bigg[\begin{array}{rrr|r}1 & -1 & 1 & 0\\1 & 1 & 0 & 0\end{array}\bigg]$$
which gives us the vector $\boldsymbol{p}_{3}=\frac{1}{\sqrt{ 6 }}\begin{bmatrix} -1\\ 1\\ 2\end{bmatrix}$
So $P=\begin{bmatrix} \frac{1}{\sqrt{ 3 }} & \frac{1}{\sqrt{ 2 }} & -\frac{1}{\sqrt{ 6 }}\\ -\frac{1}{\sqrt{ 3 }} & \frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 6 }}\\ \frac{1}{\sqrt{ 3 }}  & 0 & \frac{2}{\sqrt{ 6 }}\end{bmatrix}$
and $\Sigma=\begin{bmatrix}\sqrt{ 3} & 0\\0 & \sqrt{ 2 }\\0 & 0\end{bmatrix}$
And thus we get our SVD $A=P\Sigma Q^{T}$

# Corollaries of SVD

>[!theorem]
>Let $A=P\Sigma Q^{T}$
>- $\mathcal{N}(A)=\text{span}\{ \boldsymbol{q}_{r+1},\dots,\boldsymbol{q}_{n} \}$
>- $\mathcal{R}(A)=\text{span}\{ \boldsymbol{p}_{1},\dots,\boldsymbol{p}_{r} \}$
>- $\mathcal{N}(A^{T})=\text{span}\{ \boldsymbol{p}_{r},\dots,\boldsymbol{p}_{m} \}$
>- $\mathcal{R}(A^{T})=\text{span}\{ \boldsymbol{q}_{1},\dots,\boldsymbol{q}_{r} \}$
>- $\text{rank}(A)=r$

>[!theorem]
>Let $\sigma_{1}$ be the largest singular value of $A$. Then $\|A\|=\sigma_{1}$
>
>>[!proof]
>>Since $P$ is an orthogonal matrix then we know that $\|P\Sigma Q^{T}\boldsymbol{x}\|=\|\Sigma Q^{T}\boldsymbol{x}\|$
>>$$\|A\|=\max{x\neq_{0}}\|A\boldsymbol{x}\|=\max_{x\neq 0}\|P\Sigma Q^{T}\boldsymbol{x}\|=\max_{x\neq{0}}\|\Sigma Q^{T}\boldsymbol{x}\|$$
>>Let $\boldsymbol{y}=Q^{T}\boldsymbol{x}$
>>$$\max_{y\neq 0}\|\Sigma \boldsymbol{y}\|=\max_{y\neq{0}} \|\Sigma\|=\sigma_{1}$$
>>Since $\Sigma$ is diagonal the norm is equal to the maximum value of the entries

>[!theorem]
>Let $A$ be an $n\times n$ invertible matrix, let $\sigma_{1}$ be the largest singular value of $A$ and let $\sigma_{n}$ be the smallest.
>$\|A^{-1}\|=\frac{1}{\sigma_{n}}\sigma_{n}$ and thus $\text{cond}(A)=\frac{\sigma_{1}}{\sigma_{n}}$ gives us the [[Error Analysis#Condition number|condition number]] 
>
>>[!proof]
>>Since the singular values of $A$ are $\sigma_{1},\dots,\sigma _n$ in decreasing order
>>Then for $A^{-1}$ the singular values in decreasing order are $\frac{1}{\sigma_{n}},\dots, \frac{1}{\sigma_{1}}$

# Principal component analysis

>[!definition]
>Let $\boldsymbol{x}_{1},\dots,\boldsymbol{x}_{n}\in \mathbb{R}^{p}$ (viewed as row vectors) and let $X$ be the $n\times p$ matrix where row $k$ is given by $\boldsymbol{x}_{k}$ 
>Assume the data is normalized such that the mean value of each column is zero
>The unit vector $\boldsymbol{w}_{1}$ which maximizes the sum
>$$\sum_{i=1}^{n} \braket{ \boldsymbol{x}_{i} | \boldsymbol{w}_{1} }^{2}=\|X\boldsymbol{w}_{1}\|^{2}$$
>Is called the first weight vector of $X$
>More generally given weight vectors $\boldsymbol{w}_{1},\dots,\boldsymbol{w}_{k-1}$ the $k$th weight vector of $X$ is the unit vector $\boldsymbol{w}_{k}$ which maximizes
>$$\|X_{k}\boldsymbol{w}_{k}\|^{2}$$
>where $X_{k}$ is the projection of the data matrix $X$ onto $\text{span}\{ \boldsymbol{w}_{1},\dots,\boldsymbol{w}_{k-1} \}^{\perp}$
>$$X_{k}=X-\sum_{j=1}^{k-1} X\boldsymbol{w}_{j}\boldsymbol{w}_{j}^{T}$$
>The projection coefficient $\braket{ \boldsymbol{x}_{i} | \boldsymbol{w}_{i} }$ is called the $k$-th principal component of a data vector $\boldsymbol{x}_{i}$

Each $\braket{ \boldsymbol{x}_{i} | \boldsymbol{w}_{1} }^{2}$ is the length squared of the [[Orthogonal Projection]] of $\boldsymbol{x}_{i}$ onto $\boldsymbol{w}_{i}$
Therefore the first weight vector points in the direction which captures the most information i.e. the most variance of the data, and
the second weight vector is [[Orthogonal Projection#Orthogonal Bases|orthogonal]] to the first

>[!theorem]
>The weight vectors $\boldsymbol{w}_{1},\dots \boldsymbol{w}_{p}$ are the right singular vectors of the matrix $X$
>In other words let $X=P\Sigma Q^{T}$, let $\boldsymbol{q}_{1},\dots,\boldsymbol{q}_{p}$ be the column vectors of $Q$ then $\forall i\in \mathbb{Z},\quad i\leq p \quad \boldsymbol{w}_{i}=\boldsymbol{q}_{i}$
>>[!proof]
>>Found on math 307 github

More example shown on the [github](https://ubcmath.github.io/MATH307/eigenvalues/svd.html)

# Pseudo Inverse and least squares

>[!definition]
>Let $A=P\Sigma Q^{T}$and let $\text{rank}(A)=r$
>the pseudoinverse is given by $A^{+}=P\Sigma^{+} Q^{T}$ where 
>
>$$\Sigma^{+}=\left[ \begin{array}{rrr|r}\sigma_{1}^{-1} &  &  & \\ & \ddots &  & \boldsymbol{0} \\  &  & \sigma_{r} & \\ \hline   & \boldsymbol{0}  & & \boldsymbol{0}\end{array}\right]_{n\times m}$$


If $A$ is invertible then $A^{+}=A^{-1}$

>[!theorem]
>Let $A$ be an $m\times n$ matrix with $\text{rank}(A)=n$ and let $\boldsymbol{b}\in \mathbb{R}^{m}$ 
>The least squares approximation of the system $A\boldsymbol{x}\cong \boldsymbol{b}$ is given by $A^{+}\boldsymbol{b}=\boldsymbol{x}$


>[!theorem]
>$AA^{+}$ is the projection matrix onto $\mathcal{R}(A)$ and $A^{+}A$ is the projection onto $\mathcal{R}(A^{T})$

>[!theorem]
>$AA^{+}A=A$ and $A^{+}AA^{+}=A^{+}$


# SVD Expansion

>[!theorem]
>$\text{rank}(A)=r$, $A=P\Sigma Q^{T}$ is the singular value decomposition, we have that
>
>$$A=\sum_{i=1}^{r} \sigma_{i}\boldsymbol{p}_{i}\boldsymbol{q}_{i}^{T}$$
>Where $\boldsymbol{p}_{1},\dots,\boldsymbol{p}_{r}$ are the first $r$ columns of $P$ and the same for $Q$

>[!definition]
>The SVD expansion of $A$ is given by
>$$A=\sum_{i=1}^{r} \sigma_{i}\boldsymbol{p}_{i}\boldsymbol{q}_{i}^{T}$$
>Note that $\boldsymbol{p}_{i}\boldsymbol{q}_{i}^{T}$ are $m\times n$ matrices

>[!definition]
>The truncated SVD expansion of rank $k$ of $A$ is given by
>$$A_{k}=\sum_{i=1}^{k} \sigma_{i}\boldsymbol{p}_{i}\boldsymbol{q}_{i}^{T}$$

Suppose we want to solve the system $A\boldsymbol{x}=\boldsymbol{b}$ however the right side is corrupted by noise $\boldsymbol{e}$ and we must work with the system $A\hat{x}=\boldsymbol{b}+\boldsymbol{e}$
Solving directly we get

$$\hat{x}=A^{-1}(\boldsymbol{b}+\boldsymbol{e})$$
The term $A^{-1}\boldsymbol{e}$ is called the inverted noise which may dominate the true solution
From SVD we see that most of $A$ is composed of the terms $\sigma_{i}\boldsymbol{p}_{i}\boldsymbol{q}_{i}^{T}$ for large singular values
If we know the error is unrelated to $A$ in the sense that $\boldsymbol{e}$ is mostly orthogonal to the singular vectors $\boldsymbol{p}_{i}$ corresponding to large singular values
Then the truncated SVD expansion of the pseudoinverse gives a better solution

$$A_{k}^{+}=\sum_{i=1}^{k} \frac{1}{\sigma_{i}}\boldsymbol{p}_{i}\boldsymbol{q}_{i}^{T}$$
$$\hat{\boldsymbol{x}}=A_{k}^{+}(\boldsymbol{b}+\boldsymbol{e})$$
Since the term $A^{+}_{k}\boldsymbol{e}$ will be smaller.

In other worse we avoid term $\sigma_{i}^{-1}\boldsymbol{p}_{i}\boldsymbol{q}_{i}^{T}$ in the SVD expansion of $A^{-1}$ for small singular values which produce large values $\sigma_{i}^{-1}$ which may amplify the error
This is the strategy for image deblurring and computed tomography in the next sections

