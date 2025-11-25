__Big Idea__ Find the least squares approximation of the system $A \boldsymbol{x}\approx \boldsymbol{b}$ by minimizing the distance $\|A\boldsymbol{x}-\boldsymbol{b}\|$
There are several methods to find the approximation including the normal equations and the [[QR Decomposition|QR]] equations

>[!definition]
>Let $A$ be an $m\times n$ matrix with $m>n$ and $\text{rank}(A)=n$. The least squares approximation of the system $A\boldsymbol{x}\approx \boldsymbol{b}$ is the vector$\boldsymbol{x}$ which minimizes the distance $\|A\boldsymbol{x}-\boldsymbol{b}\|$

# Normal Equations

>[!theorem]
>Let $A$ be an $m\times n$ matrix with $m>n$ and $\text{rank}(A)=n$. The least squares approximation of the system $A\boldsymbol{x}\approx \boldsymbol{b}$ is the solution of the system $A^{T}A\boldsymbol{x}=A^{T}\boldsymbol{b}$
>The system is called the normal equations
>
>>[!proof]
>>Of $\boldsymbol{x}\in \mathbb{R}^{n}$, then $A\boldsymbol{x}\in \mathcal{R}(A)$. The [[Orthogonal Projection#Projection theorem|projection theorem]] states that the point in $\mathcal{R}(A)$ nearest to $\boldsymbol{b}\in \mathbb{R}^{m}$ is the orthogonal projection of $\boldsymbol{b}$ onto $\mathcal{R}(A)$
>>If $\boldsymbol{x}$ is the vector such that $A\boldsymbol{x}=\text{proj}_{\mathcal{R}(A)}(\boldsymbol{b})$ then $A\boldsymbol{x}-\boldsymbol{b}\in \mathcal{R}(A)^{\perp}$ and therefore 
>>$$A^{T}(A\boldsymbol{x}-\boldsymbol{b})=0\implies A^{T}A\boldsymbol{x}=A^{T}\boldsymbol{b}$$
>>We assume $\text{rank}(A)=n$ therefore $A^{T}A$ is nonsingular and the solution exists and is unique

# QR equations

>[!theorem]
>Let $A$ be an $m\times n$ matrix with $m>n$ and $\text{rank}(A)=n$. The least squares approximation of the system $A\boldsymbol{x}\approx \boldsymbol{b}$ is the solution of the system of equations 
>$$R_{1}\boldsymbol{x}=Q^{T}_{1}\boldsymbol{b}$$
>where $A=Q_{1}R_{1}$ is the [[QR Decomposition#QR by Gram-Schmidt|thin QR decomposition]]. The system is called the __QR equations__
>Furthermore the residual is given by $\|A\boldsymbol{x}-\boldsymbol{b}\|=\|Q_{2}^{T}\boldsymbol{b}\|$
>where $A=QR$ is the QR decomposition with $Q=[Q_{1}\quad Q_{2}]$
>
>>[!proof]
>>The matrix $Q$ is orthogonal therefore
>>$\|A\boldsymbol{x}-\boldsymbol{b}\|^{2}=\|Q(R\boldsymbol{x}-Q^{T}\boldsymbol{b})\|^{2}=\|R\boldsymbol{x}-Q^{T}\boldsymbol{b}\|^{2}$
>>
>>$=\bigg\|\begin{bmatrix}R_{1}\end{bmatrix}\boldsymbol{x}-\begin{bmatrix}Q_{1}^{T}\\Q_{2}^{T} & \end{bmatrix}\boldsymbol{b}\bigg\|^{2}$ $=\bigg\|\begin{bmatrix}R_{1}\boldsymbol{x}\\\boldsymbol{0}\end{bmatrix}-\begin{bmatrix}Q_{1}^{T}\boldsymbol{b}\\Q_{2}^{T}\boldsymbol{b}\end{bmatrix}\bigg\|^{2}$
>>
>>$=\bigg\|\begin{bmatrix}R_{1}\boldsymbol{x}-Q_{1}^{T}\boldsymbol{b}\\-Q_{2}^{T}\boldsymbol{b}\end{bmatrix}\bigg\|^{2}$
>>
>>$=\|R_{1}\boldsymbol{x}-Q_{1}^{T}\boldsymbol{b}\|^{2}+\|Q_{2}^{T}\boldsymbol{b}\|^{2}$
>>where we use the [[Orthogonal Complement#Orthogonal Vectors|Pythagoras theorem]] in the last equality. 
>>The vector $Q_{2}^{T}\boldsymbol{b}$ does not depend on $\boldsymbol{x}$ therefore the minimum value of the error occurs when $R_{1}\boldsymbol{x}=Q_{1}^{T}\boldsymbol{b}$ and he residual is $\|A\boldsymbol{x}-\boldsymbol{b}\|=\|Q_{2}^{T}\boldsymbol{b}\|$


# Fitting models to data
>[!definition]
>Suppose we have $m$ points $(t,y)$ and we want to find a line $y=c_{1}+c_{2}t$
>that best fits the data
>There are different ways to quantify what best fits means but the most common method is called __least squares linear regression___.
>In the least squares linear regression we want to minimize the sum of the squared errors
>$$SSE=\sum_{i}(y_{i}-(c_{1}+c_{2}t_{i}))^{2}$$
>In matrix notation the sum of squared error is $SSE = \|\boldsymbol{y}-A \boldsymbol{c}\|^{2}$
>where 
>$$\boldsymbol{y}=\begin{bmatrix}y_{1}\\y_{2}\\ \vdots \\ y_{m}\end{bmatrix}\quad  A=\begin{bmatrix}1 & t_{1}\\1 & t_{2}\\ \vdots & \vdots \\1 & t_{m}\end{bmatrix} \quad  \boldsymbol{c}=\begin{bmatrix}c_{1}\\c_{2}\end{bmatrix}$$
>We assume that $m\geq 2$ and $t_{i}\neq t_{j}\iff t\neq j$ which implies $\text{rank}(A)=2$ Therefore the vector coefficients
>$\boldsymbol{c}=\begin{bmatrix}c_{1}\\c_{2} \end{bmatrix}$
>is the least squares approximation of the system $A \boldsymbol{c}\approx \boldsymbol{y}$

More generally, given $m$ points and a __model function__ $f(t,c)$ which depends on parameters $c_{1},\dots,c_{n}$ the __least squares data fitting problem__ consists of computing parameters $c_{1},\dots,c_{n}$ which minimize the sum of the squared errors $SSE$

If the model function is of the form $f(t,c)=c_{1}f_{1}(t)+\dots+c_{n}f_{n}(t)$ then we say the 
data fitting problem is __linear__. In this case, use matrix notation to write the sum of squared errors as

$SSE=\|\boldsymbol{y}-A \boldsymbol{c}\|^{2}$ Where

$$\boldsymbol{y} = \begin{bmatrix}y_{1}\\y_{2}\\ \vdots \\ y_{m}\end{bmatrix}\quad  A=\begin{bmatrix}f_{1}(t_{1}) & f_{2}(t_{1}) & \dots & f_{n}(t_{1}) \\ f_{1}(t_{2}) & f_{2}(t_{2}) & \dots & f_{2}(t_{2}) \\ \vdots & \vdots & \ddots & \vdots \\ f_{1}(t_{m}) & f_{2}(t_{m}) & \dots & f_{n}(t_{m})\end{bmatrix}\quad  \boldsymbol{c}=\begin{bmatrix}c_{1}\\c_{2}\\  \vdots \\ c_{n}\end{bmatrix}$$

We assume that $m\geq n$ and $f_{1}, \dots,f_{n}$ are linearly independent (which implies $\text{rank}(A)=n$) 
Therefore the vector coefficients $\boldsymbol{c}$ is the least squares approximation of the system $A \boldsymbol{c}\approx \boldsymbol{y}$
