**Big Idea**. The orthogonal complement $U^\perp$ of a subspace $U$ is the collection of all vectors which are orthogonal to every vector in $U$

# Orthogonal Vectors

>[!definition]
>The **inner product** of vectors $\vec{x},\vec{y}\in \mathbb{R}^{n}$ is
>$$\braket{ x , y } =\sum_{k=1}^{n} x_{k}y_{k}=x_{1}y_{1}+\dots+x_{n}y_{n}$$

Lets summarize various properties of the inner product:
1. The inner product is symmetric $$\braket{ x | y }=\braket{ y | x }\forall \vec{x},\vec{y}\in \mathbb{R}^{n}$$
2. The inner product of column vectors is the same as matrix multiplication $$\braket{\boldsymbol{x}  |\boldsymbol{y}  }=\boldsymbol{x}^{T}\boldsymbol{y} $$
3. The inner product satisfies the usual distributive rule of multiplication $$\braket{ \boldsymbol{x} | c\boldsymbol{y}+d\boldsymbol{z} } =c \braket{ \boldsymbol{x} | \boldsymbol{y} } +d\braket{ \boldsymbol{x} | \boldsymbol{z} } $$
4. The square root of the inner product of a vector with itself is equal to the 2-norm $$\sqrt{ \braket{ \boldsymbol{x} | \boldsymbol{x} }  }=\|\boldsymbol{x}\|$$
5. We can also write the inner product in terms of the angle between vectors $$\braket{ \boldsymbol{x} | \boldsymbol{y} } =\|\boldsymbol{x}\\\|\boldsymbol{y}\|\|\cos \theta$$
6. Let $A$ be an $m\times n$ matrix, ket $\boldsymbol{u}\in \mathbb{R}^{n}$ and let $\boldsymbol{v}\in \mathbb{R}^{n}$. Then $$\braket{ A\boldsymbol{u}|\boldsymbol{v} } =\braket{ \boldsymbol{u} | A^{T}\boldsymbol{v} } $$
7. Let us have $A=\begin{bmatrix}\boldsymbol{u}_{1}^{T}\\ \vdots \\ \boldsymbol{u}_{m}^{T}\end{bmatrix}\in \mathbb{R}^{m\times n}$, where $\boldsymbol{u}_{1},\dots,\boldsymbol{u}_{m}\in \mathbb{R}^{n}$, that is $\boldsymbol{u}_{i}^{T}$ is the $i\text{-th}$ row of $A$. Then for any $\boldsymbol{x}\in \mathbb{R}^{n}$, we have $$A\boldsymbol{x}=\begin{bmatrix}\braket{ \boldsymbol{u}_{1} | \boldsymbol{x} } \\ \vdots \\ \braket{ \boldsymbol{u}_{m} | \boldsymbol{x} } \end{bmatrix}$$ which follows directly from the definition of the matrix vector product

>[!defintion]
>Vectors are orthogonal if the inner product between them is zero $\braket{ \boldsymbol{x} | \boldsymbol{y} }=0$
>More generally vectors $\boldsymbol{x}_{1},\dots,\boldsymbol{x}_{m}\in \mathbb{R}^{n}$ are orthogonal if
>$\braket{ \boldsymbol{x}_{i} | \boldsymbol{x}_{j} }=0$ for all $i\neq j$
>In other words each vector is orthogonal to every other vector in the set
>Furthermore the are orthonormal if $\braket{ \boldsymbol{x}_{i} | \boldsymbol{x}_{i} }=1=\|\boldsymbol{x}\|$ if each vector is orthogonal to the others and is a unit vector

Vectors $\boldsymbol{x},\boldsymbol{y}$ are orthogonal iff the acute angle between them is $\pi / 2$ radians or $90\degree$

>[!theorem]
>Let the $\sum_{n}\boldsymbol{x}_{n}$ form an orthogonal basis, then
>$$\|\boldsymbol{x}_{1}+\dots+\boldsymbol{x}_{m}\|^{2}=\|\boldsymbol{x}_{1}\|^{2}+\dots+\|\boldsymbol{x}_{m}\|^{2}$$
>This is called the Pythagorean theorem

# Orthogonal subspaces

>[!defintion]
>let $U_{1},U_{2}\subseteq \mathbb{R}^{n}$ be [[Subspaces| subspaces]]. Then $U_{1}$ and $U_{2}$ are orthogonal if $\braket{ \boldsymbol{x}_{1} | \boldsymbol{x}_{2} }=0$ 
>for all $\boldsymbol{x}_{1}\in U_{1}$ and $\boldsymbol{x}_{2}\in U_{2}$. If $U_{1}$ and $U_{2}$ are orthogonal subspaces then we write
>$U_{1}\perp U_{2}$

>[!theorem]
>Let $\{ \boldsymbol{u}_{1},\dots,\boldsymbol{u}_{2} \}$ be a basis of a subspace $U_{1}\subseteq \mathbb{R}^{n}$ and let $\{ \boldsymbol{v}_{1},\dots,\boldsymbol{v}_{l} \}$ be a basis of a subspace $U_{2}\subseteq \mathbb{R}^{n}$. Then $U_{1}\perp U_{2}\iff \braket{ \boldsymbol{u}_{i} | \boldsymbol{v}_{j} }=0\quad\forall i,j$
>In other words, every $\boldsymbol{u}_{i}$ in the $U_{1}$ basis is orthogonal to each $\boldsymbol{v} _j$ in the basis $U_{2}$
>

>[!example]
>Let $U_{1}\subset \mathbb{R}^{3}$ and $U_{2}\subset \mathbb{R}^{3}$ be 2-dimensional subspaces, planes. Is it possible that $U_{1}\perp U_{2}$?
>No!

# Orthogonal Complement

>[!defintion]
>Let $U\subseteq \mathbb{R}^{n}$ be a subspace. The orthogonal complement of $U$ is given by 
>$$U^{\perp}=\{ \boldsymbol{x}\in \mathbb{R}^{n}:\braket{ \boldsymbol{x} | \boldsymbol{y} } =0\,\forall\,\boldsymbol{y}\in U \}$$

Note
- If $U\subseteq \mathbb{R}^{n}$ is any subspace then $U=(U^{\perp})^{\perp}$ and also $U\cap U^{\perp}=\{ \vec{0} \}$
- $\{ \boldsymbol{0} \}^{\perp}=\mathbb{R}^{n}$
>[!theorem]
>Let $U\subseteq R^{n}$ is a subspace, then $U^{\perp}\subseteq \mathbb{R}^{n}$ is a subspace
>>[!proof]
>>Let us verify that $U^{\perp}$ satisfies the properties of a subspace
>>clearly $\braket{ \vec{0} | \boldsymbol{x} }=0\,\forall \boldsymbol{x}\in U$ therefore $\vec{0}\in U^{\perp}$
>>Let $\boldsymbol{x}_{1},\boldsymbol{x}_{2}\in U^{\perp}$. Then $$\braket{ \boldsymbol{x}_{1}+\boldsymbol{x}_{2} | \boldsymbol{y} } =\braket{ \boldsymbol{x}_{1} | \boldsymbol{y} } +\braket{ \boldsymbol{x}_{2} | \boldsymbol{y} } =0+0=0\forall \boldsymbol{y}\in U$$
>>Therefore $\boldsymbol{x}_{1}+\boldsymbol{x}_{2}\in U^{\perp}$
>>Let $c\in \mathbb{R},\quad \boldsymbol{u}\in U^{\perp}$. Then $$\braket{ c\boldsymbol{x} | \boldsymbol{y} } =c \braket{ \boldsymbol{x} | \boldsymbol{y} } =c(0)=0\,\forall \boldsymbol{y}\in U$$
>>Therefore $c\boldsymbol{x}\in U^{\perp}$
>>Therefore $U^{\perp}$ is a subspace

# Fundamental subspaces

>[!definition]
>Let $A$ be a $m\times n$ matrix, The fundamental subspaces of $A$ are $N(A),\,R(A)\,,N(A^{T})$ and $R(A^{T})$

>[!theorem]
>Let $A$ be an $m\times n$ matrix. Then $N(A)=R(A^{T})^{\perp}$ and $R(A)=N(A^{T})^{\perp}$
>>[!proof]
>>The _second_ equality follows from the first by replacing $A$ with $A^{T}$ therefore it is sufficient to prove $N(A)=R(A^{T})^{\perp}$
>>A general strategy to prove equality of sets is to show that each set contains the other therefore lets prove $N(A)\subseteq R(A^{T})^{\perp}$ and then the reverse
>>
>>Let $\boldsymbol{x}\in N(A)$. Then $A\boldsymbol{x}={0}$ and so $\braket{ A\boldsymbol{x} | \boldsymbol{y} }={0}$ for all $\boldsymbol{y}\in \mathbb{R}^{m}$
>>Using properties of the inner product we see that $\braket{ \boldsymbol{x} | A^{T}\boldsymbol{y} }={0}\,\forall \boldsymbol{y}\in \mathbb{R}^{m}$
>>$\therefore \boldsymbol{x}\in R(A^{T})^{\perp}$
>>
>>Let $\boldsymbol{x}\in R(A^{T})^{\perp}$. Then $\braket{ \boldsymbol{x} | A^{T}\boldsymbol{y} }=0$ and so $\braket{ A\boldsymbol{x} |\boldsymbol{y}  }=0\,\forall \boldsymbol{y}\in \mathbb{R}^{m}$. Choose $\boldsymbol{y}=A\boldsymbol{x}\in \mathbb{R}^{m}$
>>and then $\braket{ A\boldsymbol{x} | A\boldsymbol{x} }=0\implies\|A\boldsymbol{x}\|=0\implies A\boldsymbol{x}=\vec{0}$ and finally $\boldsymbol{x}\in N(A)$
>>

>[!theorem]
>Let $U\subseteq \mathbb{R}^{n}$ be a subspace. Then $$\dim(U)+dim(U^{\perp})=n$$
>>[!proof]
>>Let $\dim (U)=m$ and let $\sum_{m}\boldsymbol{u}_{m}$ be a basis of $U$ and define $$A=\begin{bmatrix}\boldsymbol{u}^{T}_{1}\\ \vdots \\ \boldsymbol{u}_{m}^{T}\end{bmatrix}$$
>>Then $U=R(A^{T})$ and $U^{\perp}=R(A^{T})^{\perp}=N(A)$ and we know $\text{rank}(A)=m=\dim(U)$
>>therefore $$\dim(U)+\dim(U^{\perp})=\text{rank}(A)+\dim(N(A))=n$$
>> by the [[Subspaces#Rank Nullity Theorem| Rank Nullity Theorem]]

>[!example]
>Let $A$ be a matrix such that its [[LU Decomposition]] is of the form
>$$A=LU=\begin{bmatrix}1 & 0 & 0 \\ * & 1 & 0 \\ * & * & 1\end{bmatrix}\begin{bmatrix}* & * & * & *\\0 & * & * & * \\ 0 & 0 & * & *\end{bmatrix}$$
>where $*$ denotes a non zero number. Find the dimension of each subspace $N(A), R(A), N(A^{T})$ and $R(A^{T})$
>
>Clearly $\dim(N(A))=1$ and $\dim(R(A))=3$ therefore
>$$\dim(N(A^{T}))=\dim(R(A)^{\perp})=3-3=0$$
>and $$\dim(R(A^{T}))=\dim(N(A)^{\perp})=4-1=3$$
