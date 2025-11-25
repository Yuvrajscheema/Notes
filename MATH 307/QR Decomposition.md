__Big Idea__
If $A$ is a $m\times m$ matrix with rank $n$ then the decomposition $A=QR$ provides orthonormal bases of both $R(A)$ and $R(A)^{\perp}$. In particular write $Q=[Q_{1}, Q_{2}]$ where $Q_{1}$ is the first $n$ columns of $Q$, then the columns of $Q_{1}$ provide an orthonormal basis of $R(A)$ and the columns of $Q_{2}$ provide an orthonormal basis of $R(A)^{\perp}$

# Orthogonal matrices

>[!definition]
>A matrix is orthogonal if $A^{T}A=AA^{T}=I$

Note the condition $A^{T}A=I$ implies that the columns of $A$ are orthonormal and $AA^{T}=I$ implies the rows of $A$ are orthonormal

>[!theorem]
>If $A$ is an orthogonal matrix, then $\|Ax\|=\|x\|\forall x \in \mathbb{R}^{n}$
>
>>[!proof]
>>Compute 
>>$\|Ax\|^{2}=(Ax)^{T}Ax=x^{T}A^{T}Ax=x^{T}x=\|x\|^{2}$
>>

Rotations and reflection are examples of orthogonal matrices

An orthogonal matrix and an [[Orthogonal Projection#Projection onto a subspace |orthogonal projector]] are not the same thing
they are related.
If $P$ is an orthogonal projector then $Q=I-2P$ is an orthogonal (and symmetric) matrix.
In fact if $P$ projects onto a subspace then $Q$ is the reflection through $U^{\perp}$

# QR by Gram-Schmidt

>[!definition]
>Let $A$ be an $m\times n$ matrix with $\text{rank}(A)=n$ and let $a_{1},\dots,a_{n}$ be the columns of $A$
>Apply the Gram-Schmidt algorithm to the columns and construct and orthonormal basis $\{ w_{1},\dots,w_{n} \}$ of $\mathcal{R}(A)$
>Project the columns onto the basis
>
>$$
>\begin{align}
> \boldsymbol{a_{1}}&=\braket{ \boldsymbol{w_{1}} | \boldsymbol{a_{1}} } \boldsymbol{w_{1}}  \\ \boldsymbol{a_{2}}&=\braket{ \boldsymbol{w_{1}} | \boldsymbol{a_{2}} } \boldsymbol{w_{1}} + \braket{ \boldsymbol{w_{2}} | \boldsymbol{a_{2}} } \boldsymbol{w_{2}} \\ &\vdots \\ \boldsymbol{a_{3}}&= \braket{ \boldsymbol{w_{1}} | \boldsymbol{a_{n}} }\boldsymbol{w_{1}}+\braket{ \boldsymbol{w_{2}} | \boldsymbol{a_{n}} } \boldsymbol{w_{2}}+\dots+\braket{ \boldsymbol{w_{n}} | \boldsymbol{a_{n}} } \boldsymbol{w_{n}} 
\end{align}$$
>where $\boldsymbol{a_{k}}\in\text{span}(\boldsymbol{w_{1}},\dots,\boldsymbol{w_{k}})$  by construction. Write as matrix multiplication $A=Q_{1}R_{1}$
>where
>
>$$
>Q_{1}=\begin{bmatrix}\\\boldsymbol{w_{1}}  &  \dots & \boldsymbol{w_{n}}\\  & \end{bmatrix} \quad R_{1}=\begin{bmatrix}\braket{ \boldsymbol{w_{1}} | \boldsymbol{a_{1}} }  & \braket{ \boldsymbol{w_{1}} | \boldsymbol{a_{2}} }  & \dots & \braket{ \boldsymbol{w_{1}} | \boldsymbol{a_{n}} } \\  & \braket{ \boldsymbol{w_{2}} | \boldsymbol{a_{2}} }  & \dots & \braket{ \boldsymbol{w_{2}} | \boldsymbol{a_{n}} } \\  &  & \ddots  & \vdots \\  &  &  & \braket{ \boldsymbol{w_{n}} | \boldsymbol{a_{n}}  } \end{bmatrix}$$
>
>Extend the basis to an orthonormal basis $\{ \boldsymbol{w_{1}},\dots,\boldsymbol{w_{n}},\boldsymbol{w_{n+1}},\dots,\boldsymbol{w_{m}} \}$ where $\{ \boldsymbol{w_{n+1},\dots,\boldsymbol{w_{m}}} \}$ is any orthonormal basis of the orthogonal complement $\mathcal{R}(A)^{\perp}$ and let
>
>$Q_{2}=\begin{bmatrix} \\\boldsymbol{w_{n+1}} & \dots & \boldsymbol{w_{m}} \\  & \end{bmatrix}$
>
>Finally the __QR decomposition__ of $A$ is 
>
>$$A=QR=[Q_{1}\quad Q_{2}]\begin{bmatrix}R_{1}\\0\end{bmatrix}$$
>
>Where $Q$ is a $m\times m$ orthogonal matrix and $R$ is a $m\times n$ upper triangle matrix
>The decomposition $A=Q_{1}R_{1}$ is called the thin QR decomposition
>


>[!Example]
>Compute the QR decomposition for the matrix $A=\begin{bmatrix}1 & 1 & 1 \\ 0 & 1 & 1 \\ 1 & 1 & 0\end{bmatrix}$

Apply Gram Schmidt to find an orthonormal basis of the column space

$\boldsymbol{w_{1}=\frac{1}{\sqrt{ 2 }}}\begin{bmatrix}1 \\ 0 \\ 1\end{bmatrix}\quad \boldsymbol{w_{2}}=\begin{bmatrix}0 \\ 1 \\ 0\end{bmatrix}\quad \boldsymbol{w_{3}}=\frac{1}{\sqrt{ 2 }}\begin{bmatrix}1 \\ 0 \\ -1\end{bmatrix}$

Therefore:
$$Q=\begin{bmatrix}  \frac{1}{\sqrt{ 2 }} & 0 & \frac{1}{\sqrt{ 2 }} \\ 0 & 1 & 0 \\ \frac{1}{\sqrt{ 2 }}  & 0 & -\frac{1}{\sqrt{ 2 }}\end{bmatrix}$$
and 

$$R=\begin{bmatrix}\sqrt{ 2 } & \sqrt{ 2 } & \frac{1}{\sqrt{ 2 }} \\ 0 & 1 & 1 \\
0 & 0 & \frac{1}{\sqrt{ 2 }}\end{bmatrix}$$

The Gram-Schmidt algorithm shows that the QR decomposition exists but is not the most efficient way to compute the QR decomposition. MATLAB `qr` SciPy `scipy.linalg.qr` and LACKPACK use elementary reflectors to construct the matrices $Q$ and $R$

# Orthogonal Projection by QR

>[!theorem]
>Let $A$ be a $m\times n$ matrix such that $\text{rank}(A)=n$ and let $A=QR$ be the QR decomposition
>The projection of $\boldsymbol{x}\in R^{m}$ onto $\mathcal{R}(A)$ is given by 
>$$\text{proj}_{\mathcal{R}(A)^{}}(\boldsymbol{x})=Q_{1}Q_{1}^{T}\boldsymbol{x}$$
>and the projection onto $\mathcal{R}(A)^{\perp}$ is given by
>$$\text{proj}_{\mathcal{R}(A)^{\perp}}(\boldsymbol{x})=Q_{2}Q_{2}^{T}\boldsymbol{x}$$