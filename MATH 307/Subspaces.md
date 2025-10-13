**Big Idea**: Subspace of $\mathbb{R}^{n}$ include lines, planes and hyperplanes through the origin. A basis of a subspace is a linearly independent set of spanning vectors. The Rank-Nullity Theorem describes the dimensions of the nullspace and range of a matrix

# Subspaces

>[!defintion]
>A subset $U\subseteq \mathbb{R}^{n}$ is a subspace *if*
>1. $U$ contains the zero vector $\vec{0}$
>2. $\vec{u_{1}}+\vec{u_{2}}\in U\,\forall \vec{u_{1}}, \vec{u_{2}}\in U$
>3. $c \vec{u}\in U\,\forall c\in \mathbb{R}, \vec{u}\in U$

Condition 2 is called closed under addition and condition 3 is called closed under scalar multiplication. Condition 3 with $c=0$ implies condition 1

 Example 
- The zero subspace $\{ 0 \}$ and the entire space $\mathbb{R}^{n}$ are both subspaces of $\mathbb{R}^{n}$
- Subspaces of $\mathbb{R}^{2}$ include any line through the origin
- Subspaces of $\mathbb{R}^{3}$ include any line or plane through the origin
- In general, subspaces of $R^{n}$ are any hyperplanes of any dimension through the origin
>[!example]
>Consider the set
>$$U=\bigg\{ \begin{bmatrix}x \\ y\end{bmatrix}:y\geq{0} \bigg\}$$
>Then $U$ contains the zero vector
>$U$ is also closed under vector addition since
>$\vec{\forall}u_{1}, \vec{u_{2}}\in U\quad \vec{u_{1}}+ \vec{u_{2}}= \vec{u}\in U$ since $\vec{u}=[x,y]$ where $y\geq{0}$
>But $U$ is not closed under scalar multiplication as $[1,1]\in U$ but $(-1)[1,1]=[-1,-1]\not\in U$
>Therefore $U$ is not a subset of $\mathbb{R}^{2}$

# Linear Independence and Span

>[!definition]
>A linear combination of vectors $\vec{u_{1}},\dots,\vec{u_{2}}\in R^{n}$ is a vector
>$$c_{1} \vec{u_{1}}+\dots+c_{m} \vec{u_{m}}$$
>where $c_{1},\dots,c_{m}\in \mathbb{R}$. The **span** of vectors $\vec{u_{1}},\dots, \vec{u_{m}}\in R^{n}$ is the set of all linear combinations 
>$$\text{span}\{\vec{u_{1}},\dots,\vec{u_{m}}\}=\{ c_{1} \vec{u_{1}}+\dots+c_{m} \vec{u_{m}}\in \mathbb{R}^{n}:c_{1},\dots c_{m}\in \mathbb{R}\}$$

>[!theorem]
>Let $\vec{u_{1}},\dots,\vec{u_{m}}\in R^{n}$. Then $\text{span}\{ \vec{u_{1}},\dots,\vec{u_{m}} \}$ is a subspace of $\mathbb{R}^{n}$

>[!example]
>The span of a single non zero vector $\vec{u}$ is a line with direction $\hat{u}$. The span of two nonzero vectors $\vec{u}$ and $\vec{v}$ is a plane as long as the two vectors are **not** collinear

>[!definition]
>A set of vectors $\{ \vec{u_{1}},\dots, \vec{u_{m}} \}\subset \mathbb{R}^{n}$ forms a linearly independent set if the vectors satisfy the property $$c_{1} \vec{u_{1}}+\dots+c_{m} \vec{u_{m}}=\vec{0}\iff c_{1}=\dots=c_{m}=0$$
>In other words $\{ \vec{u_{1}},..,\vec{u_{m}} \}$ is a linearly independent set if no vector in the set can be expressed as a linear combination of the others

How do we know if a set of vectors is linearly independent? Create a matrix where the columns are the given vectors 
$$
A=\begin{bmatrix}\vec{u_{1}}\quad \dots \quad \vec{u_{m}}\end{bmatrix}
$$
Then the vectors are linearly independent iff the linear system $A \vec{x}=\vec{0}$ has only the trivial solution $\vec{x}=\vec{0}$

# Basis and Dimension

>[!definition]
>Let $U\subseteq \mathbb{R}^{n}$ be a subspace. A set of vectors forms a **Basis** of $U$ if:
>1. $\{ \vec{u_{1}},\dots,\vec{u_{m}} \}$ is a linearly independent set
>2. $\text{span}\{ \vec{u_{1}},\dots,\vec{u_{m}} \}=U$
>
>The dimension of $U$ is the number $m$ of vectors in a basis

# Nullspace and Range

>[!definition]
>The nullspace of a $m\times n$ matrix $A$ is
>$$N(A)=\{ \vec{x} \in \mathbb{R}^{n}: A \vec{x}=\vec{0} \}$$

>[!theorem]
>Let $A$ be an $m\times n$ matrix. The nullspace $N(A)$ is a subspace of $\mathbb{R}^{n}$

>[!theorem]
>Let $A$ be an $m\times n$ matrix and let $A=LU$ be the [[LU Decomposition]] (if it exists). Then $N(A)=N(U)$.

>[!definition]
>The range of an $m\times n$ matrix is:
>$$R(A)=\{ A \vec{x}:\vec{x}\in \mathbb{R}^{n} \}$$
>The range is also called the [[Functions| image]] or column space of A

Matrix multiplication can be written as 

$$A \vec{x}=\begin{bmatrix} \\ \vec{a_{1}} & \dots & \vec{a_{n}} \\ \quad\end{bmatrix}\begin{bmatrix}x_{1} \\ \vdots  \\ x_{m}\end{bmatrix}=x_{1} \vec{a_{1}}+\dots+x_{n} \vec{a_{n}}$$
Therefore the range of $A$ is equal to the span of the columns
$$R(A)=\text{span}\{ \vec{a_{1}},..,\vec{a_{n}} \}$$
and that's why $R(A)$ is sometimes called the column space

>[!theorem]
>Let $A$ be an $m\times n$ matrix. The range $R(A)$ is a subspace of $\mathbb{R}^{m}$

>[!theorem]
>Let $A$ be an $m\times n$ matrix. Then
>$$\text{dim}(R(A))=\text{rank}(A)$$
>>[!proof]
>>The rank of $A$ is the number of nonzero rows in the row echelon form of $A$. The dimension of $R(A)$ is the number of linearly independent columns in $A$ which also equal the number of nonzero rows in $A$.

>[!theorem]
> Let $A=LU$ be the [[LU Decomposition]] of $A$ if it exists and let $r=\text{rank(A)}$. Then 
> $$R(A)=\text{span}\{ \vec{l_{1}},\dots,\vec{l_{r}} \}$$
>where $\vec{l_{1}},\dots,\vec{l_{r}}$ are the first $r$ columns of $L$ In particular, $\vec{l_{1}},\dots,\vec{l_{r}}$ is a [[Subspaces#Basis and Dimension | basis]] of $R(A)$
>>[!proof]
>>If $\text{rank}(A)=r$ then only the first $r$ entries of the vector $U \vec{x}$ are nonzero
>>$$U \vec{x}=\begin{bmatrix}* & * & \dots & * \\ 0 & \ddots  & \ddots & \vdots \\ \vdots & \ddots & * & * \\
0 & \dots & 0 & 0 \end{bmatrix} \vec{x}=\begin{bmatrix}* \\
\vdots \\ * \\
0\end{bmatrix} $$
>>Therefore
>>$$ LU \vec{x}=\bigg[ \vec{l_{1}},\dots,\vec{l_{n}} \bigg]\begin{bmatrix}* \\ \vdots \\ \end{bmatrix} = (*) \vec{l_{1}}+\dots+(*) \vec{l_{r}}$$

# Rank Nullity Theorem

>[!theorem]
>Let $A$ be an $m\times n$ matrix. Then
>$$
>\dim(R(A))+\dim(N(A))=n$$
>>[!proof]
>>The dimension of $N(A)$ is equal to the number of columns in row echelon form of $A$ without a leading nonzero entry
>> $\text{rank}(A)=\dim(R(A))$ is equal to the number of columns of the row echelon form with a leading non zero entry and there are $n$ total columns


