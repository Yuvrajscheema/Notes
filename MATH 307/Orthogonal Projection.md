**Big Idea**. The point in a [[Subspaces | subspace]] $U\subseteq \mathbb{R}^{n}$ nearest to $\boldsymbol{x}\in \mathbb{R}^{n}$ is the projection $\text{proj}_{U}(\boldsymbol{x})$ of $\boldsymbol{x}$ onto $U$

# Projection onto a Vector

>[!definition]
>The projection of a vector $\boldsymbol{x}$ onto a vector $\boldsymbol{u}$ is $$\text{proj}_{\boldsymbol{u}}(\boldsymbol{x})=\frac{\braket{ \boldsymbol{x} | \boldsymbol{u} }}{\braket{ \boldsymbol{u} | \boldsymbol{u} } }\boldsymbol{u}$$

Projection onto $\boldsymbol{u}$ is given by matrix multiplication $$\text{proj}_{\boldsymbol{u}}(x)=P\boldsymbol{x}\text{ where }P=\frac{1}{\|\boldsymbol{u}\|^{2}}\boldsymbol{u}\boldsymbol{u}^{T}$$
Note that $P^{2}=P,P^{T}$ and $\text{rank}(P)=1$

# Orthogonal Bases

>[!definition]
>Let $U\subseteq \mathbb{R}^{n}$ be a subspace.
>A set of vectors $\sum_{m}\boldsymbol{w}_{m}$ is an [[Orthogonal Complement#Orthogonal Vectors | orthogonal basis]] for $U$ if it is a basis for $U$ and the vectors in the set are orthogonal
>Furthermore, if each $\boldsymbol{w}_{j}$ is a unit vector, $\|\boldsymbol{w}_{j}\|=1$ then the set is an orthonormal basis

>[!theorem]
>Let $\sum_{m}\boldsymbol{u}_{m}$ be a basis of the subspace $U\subseteq \mathbb{R}^{n}$ The __Gram-Schmidt orthogonalization algorithm__ constructs an orthogonal basis of $U$:
>$\begin{align}\boldsymbol{v}_{1}&=\boldsymbol{u}_{1} \\ \boldsymbol{v}_{2}&=\boldsymbol{u}_{2}-\text{proj}_{\boldsymbol{v}_{1}}(\boldsymbol{u}_{2}) \\ \boldsymbol{v}_{3 }&=\boldsymbol{u}_{3}-\text{proj}_{\boldsymbol{v}_{1}}(\boldsymbol{u}_{3})-\text{proj}_{\boldsymbol{v}_{2}}(\boldsymbol{u}_{3}) \\ &\,\,\,\vdots \\ \boldsymbol{v}_{m}&=\boldsymbol{u}_{m}=\text{proj}_{\boldsymbol{v}_{1}}(\boldsymbol{u}_{m})-\text{proj}_{\boldsymbol{v}_{2}}(\boldsymbol{u}_{m})-\dots-\text{proj}_{\boldsymbol{v}_{m-1}}(\boldsymbol{u}_{m})\end{align}$
>Then $\{ \boldsymbol{v}_{1},\dots,\boldsymbol{v}_{m} \}$ is an orthogonal basis of $U$. Furthermore let $$\boldsymbol{w}_{k}=\frac{\boldsymbol{v}_{k}}{\|\boldsymbol{v}_{k}\|},\quad k=1,\dots,m$$
>Then $\{ \boldsymbol{w}_{1},\dots,\boldsymbol{w}_{m} \}$ is an orthonormal basis of $U$

>[!example]
>Construct an orthonormal basis of the subspace $U$ spanned by 
>$$\boldsymbol{u}_{1}=\begin{bmatrix}1 \\ 0\\1\\0\end{bmatrix}\quad \boldsymbol{u}_{2}=\begin{bmatrix}1\\1\\1\\0\end{bmatrix}\quad \boldsymbol{u}_{3}=\begin{bmatrix}1\\1\\0\\0\end{bmatrix}$$
>Compute the orthogonal basis of $U$ $\{ \boldsymbol{v}_{1},\boldsymbol{v}_{2}, \boldsymbol{v}_{3} \}$
>$\begin{align}\boldsymbol{v}_{1}&=\boldsymbol{u}_{1} \\ \boldsymbol{v}_{2}&=\boldsymbol{u}_{2}-\text{proj}_{\boldsymbol{v}_{1}}(\boldsymbol{u}_{2}) \\ \boldsymbol{v}_{3 }&=\boldsymbol{u}_{3}-\text{proj}_{\boldsymbol{v}_{1}}(\boldsymbol{u}_{3})-\text{proj}_{\boldsymbol{v}_{2}}(\boldsymbol{u}_{3})\end{align}$
>We find an orthogonal basis $$\boldsymbol{v}_{1}=\begin{bmatrix}1\\0\\1\\0\end{bmatrix}\quad \boldsymbol{v}_{2}=\begin{bmatrix}0\\1\\0\\0\end{bmatrix}\quad \boldsymbol{v}_{3}=\frac{1}{2}\begin{bmatrix}1\\0\\-1\\0\end{bmatrix}$$
>And an orthonormal basis $$\boldsymbol{w}_{1}=\frac{1}{\sqrt{ 2 }}\begin{bmatrix}1\\0\\1\\0\end{bmatrix}\quad \boldsymbol{w}_{2}=\begin{bmatrix}0\\1\\0\\0\end{bmatrix}\quad \boldsymbol{w}_{3}=\frac{1}{\sqrt{ 2 }}\begin{bmatrix}1\\0\\-1\\0\end{bmatrix}$$

# Projection onto a subspace

>[!definition]
>Let $U\subseteq \mathbb{R}^{n}$ be a subspace and let $\{ \boldsymbol{u}_{1},\dots,\boldsymbol{u}_{m} \}$ be an orthogonal basis of $U$. The projection of a vector $\boldsymbol{x}$ onto $U$ is
>$$\text{proj}_{U}(\boldsymbol{x})=\frac{\braket{ \boldsymbol{x} | \boldsymbol{u}_{1} }}{\braket{ \boldsymbol{u}_{1} | \boldsymbol{u}_{1} } }\boldsymbol{u}_{1}+\dots+\frac{\braket{ \boldsymbol{x} | \boldsymbol{u}_{m} }}{\braket{ \boldsymbol{u}_{m} | \boldsymbol{u}_{m} } }\boldsymbol{u}_{m}$$

Projection onto $U$ is given by matrix multiplication
$$\text{proj}_{U}(\boldsymbol{x})=P\boldsymbol{x}\text{ where }P=\frac{1}{\|\boldsymbol{u}_{1}\|^{2}}\boldsymbol{u}_{1}\boldsymbol{u}_{1}^{T}+\dots+\frac{1}{\|\boldsymbol{u}_{m}^{2}\|}\boldsymbol{u}_{m}\boldsymbol{u}_{m}^{T}$$
Note that $P^{2}=P,P^{T}=P$ and $\text{rank(P)=m}$

>[!definition]
>A matrix $P$ is an orthogonal projector (or orthogonal projection matrix) if $P^{2}=P$ and $P^{T}=P$

>[!theorem]
>Let $P$ be the orthogonal projection onto $U$. Then $I-P$ is the orthogonal projection matrix onto $U^{\perp}$

>[!example]
>Find the orthogonal matrix $P$ which projects onto the subspace spanned by the vectors $$\boldsymbol{u}_{1}=\begin{bmatrix}1\\0\\-1\end{bmatrix}\quad \boldsymbol{u}_{2}=\begin{bmatrix}1\\1\\1\end{bmatrix}$$
>Compute $\braket{ \boldsymbol{u}_{1} | \boldsymbol{u}_{2} }=0$ therefore the vectors are orthogonal. Compute
>$$\begin{align}P&=\frac{1}{\|\boldsymbol{u}_{1}\|^{2}}\boldsymbol{u}_{1}\boldsymbol{u}_{1}^{T}+\frac{1}{\|\boldsymbol{u}_{2}\|^{2}}\boldsymbol{u}_{2}\boldsymbol{u}_{2}^{T}  \\
&=\frac{1}{2}\begin{bmatrix}1\\0\\-1\end{bmatrix}\begin{bmatrix}1 & 0 & -1\end{bmatrix}+\frac{1}{3}\begin{bmatrix}1\\1\\1\end{bmatrix}\begin{bmatrix}1 & 1 & 1\end{bmatrix} \\ &=\frac{1}{2}\begin{bmatrix}1 & 0 & -1\\0 & 0 & 0\\-1 & 0 & 1\end{bmatrix}+\frac{1}{3}\begin{bmatrix}1 & 1 & 1\\1 & 1 & 1\\1 & 1 & 1\end{bmatrix}\\&=\frac{1}{6}\begin{bmatrix}5 & 2 & -1\\2 & 2 & 2\\-1 & 2 & 5\end{bmatrix}\end{align}$$
>

>[!example]
>Find the orthogonal projection matrix $P_{\perp}$ which projects onto $U_{\perp}$ where $U$ is the subspace spanned by the vectors
>$$\boldsymbol{u}_{1}=\begin{bmatrix}1\\0\\-1\end{bmatrix}\quad \boldsymbol{u}_{2}=\begin{bmatrix}1\\1\\1\end{bmatrix}$$
>In the last example we found $P$ so $P_{\perp}=I-P$
>
>$P_{\perp}=\begin{bmatrix}1 & 0 & 0\\0 & 1 & 0\\0 & 0 & 1 \end{bmatrix}-\frac{1}{6}\begin{bmatrix}5 & 2 & -1\\2 & 2 & 2\\-1 & 2 & 5\end{bmatrix}=\frac{1}{6}\begin{bmatrix}1 & -2 & 1\\-2 & 4 & -2\\1 & -2 & 1\end{bmatrix}$
>
>Note that $$\boldsymbol{u}_{3}=\begin{bmatrix}1\\-2\\1\end{bmatrix}$$
>is orthogonal to $\boldsymbol{u}_{1}$ and $\boldsymbol{u}_{2}$ and is a basis of the orthogonal complement $U^{\perp}$. Therefore we could also compute $$P_{\perp}=\frac{1}{\|\boldsymbol{u}_{3}\|^{2}}\boldsymbol{u}_{3}\boldsymbol{u}_{3}^{T}$$

# Projection theorem

>[!theorem]
>Let $U\subseteq \mathbb{R}^{n}$ be a subspace and let $\boldsymbol{x}\in \mathbb{R}^{n}$. Then $$\boldsymbol{x}-\text{proj}_{U}(\boldsymbol{x})\in U^{\perp}$$
>and $\text{proj}_{U}(\boldsymbol{x})$ is the closest vector in $U$ to $\boldsymbol{x}$ in the sense that 
>$$\|\boldsymbol{x}-\text{proj}_{U}(\boldsymbol{x})\|<\|\boldsymbol{x}-\boldsymbol{y}\|\quad \forall \,\boldsymbol{y}\in U\,,\,\boldsymbol{y}\neq\text{proj}_{U}(\boldsymbol{x})$$