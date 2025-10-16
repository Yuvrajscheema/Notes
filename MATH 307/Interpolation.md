**Big Idea**. An interpolating function provides information about values between points and beyond the range of data. There are infinitely many different ways to interpolate a set of data! Polynomial interpolation is the simplest method whereas cubic spline interpolation provides much more flexibility

# Interpolating Functions

An interpolating function (or interpolant) for points $(t_{0},y_{0}),\dots,(t_{d},y_{d})$ is a function $f(t)$ such that $f(t_{k})=y_{k}$ for $k=0,\dots,d$

Note that there are _infinitely_ many different interpolating functions for any set of data.
We impose different kinds of constraints on the form of the interpolant to ensure there is a unique solution which is meaningful for the data and can be computed efficiently. In the following sections we describe two kinds of interpolation _polynomial_ and _cubic spline_

# Polynomial interpolation

A polynomial of degree (at most) $d$ is a function of the form
$$p(t)=c_{0}+c_{1}t+\dots+c_{d}t^{d}$$
where $c_{0},c_{1},\dots,c_{d}\in \mathbb{R}$ the collection of all polynomials of degree (at most) $d$ is denoted by 
$$\mathbb{P}_{d}=\{c_{0}+c_{1}t+,\dots+c_{d}t^{d}:c_{0},c_{1},\dots,c_{d}\in \mathbb{R}\}$$
Note that $\mathbb{P}_{d}$ is a vector space of dimension $d+1$


Fix a positive integer $d$ and let $\phi_{k}(t)=t^{k}$ for $k=0,\dots,d$ in other words consider
the polynomials

$$\phi_{0}(t)=1,\quad \phi _{1(t)=t},\quad \dots,\quad \phi_{d}(t)=t^{d}$$
Since a polynomial $p(t)$ of degree (at most) $d$ is of the form
$$p(t)=c_{0}\phi_{0}(t)+c_{1}\phi_{1}(t)+\dots+c_{d}\phi_{d}(t)$$
we see that the polynomials $\phi_{k}(t)$ form a basis of $\mathbb{P}_{d}$. Then the set $\{ \phi_{0} (t),\dots,\phi_{d}(t)\}$ is called the **monomial basis** of $\mathbb{P}_{d}$

Given $d+1$ points $\left( t_{0},y_{0} \right),\dots,(t_{d},y_{d})$, polynomial interpolation (with respect to the monomial basis) is a polynomial of the form 
$$p(t)-c_{0}+c_{1}t+\dots+t_{d}t^{d}$$
such that $p(t_{k})=y_{k}$ for each $k=0,\dots d$. Each point defines an equation 
$$p(t_{k})=y_{k}\quad ,\quad k=0,\dots,d$$
therefore the coefficients $c_{0},c_{1},\dots,c_{d}$ satisfy the system of linear equations $A \vec{c}=\vec{y}$
where 
$$A=\begin{bmatrix}1 & t_{0} & \dots & t^{d}_{0} \\
1 & t_{1} & \dots & t^{d}_{1} \\
\vdots & \vdots & \ddots & \vdots \\
1 & t_{d} & \dots & t_{d}^{d}\end{bmatrix}\quad c=\begin{bmatrix}c_{0} \\
c_{1} \\
\vdots \\
c_{d}\end{bmatrix}
\quad y=\begin{bmatrix}y_{0} \\
y_{1} \\ \vdots \\
y_{d}
\end{bmatrix}$$
The matrix $A$ is called the Vandermonde matrix for $t_{0},\dots,t_{d}$.

>[!theorem]
>Let $A$ be the Vandermonde matrix for points $(t_{0},y_{0}),\dots,(t_{d},y)d$ Then
>$$\det(A)=\prod_{0\leq i<j\leq d}(t_{j}-t_{i})$$

>[!example]
>Compute the formula for the cases $d=1$ and $d=2$
>
>$d=1$
>$$\det(\begin{bmatrix}1 & t_{0} \\
> 1 & t_{1}\end{bmatrix})=t_{1}-t_{0}$$
>
>$d=2$
>Use $\det(A)=\det(U)$ from the LU decomposition. Compute
>
>$\begin{bmatrix}1 & t_{0} & t_{0}^{2} \\ 1 & t_{1} & t_{1}^{2} \\ 1 & t_{2} & t_{2}^{2}\end{bmatrix}\to \begin{bmatrix}1 & t_{0} & t_{0}^{2}  \\ 0 & t_{1}-t_{0} & t_{1}^{2}-t_{0}^{2} \\ 0 & t_{2}-t_{0} & t_{2}^{2}-t_{0}^{2}\end{bmatrix}\to \begin{bmatrix}1 & t_{0} & t_{0}^{2} \\ 0 & t_{1}-t_{0} & t_{1}^{2}-t_{0}^{2} \\ 0 & 0 & \star \end{bmatrix}$
>
>where $\star =t_{2}^{2}-t_{0}^{2}-\frac{{t_{2}-t_{0}}}{t_{1}-t_{0}}(t_{1}^{2}-t_{0}^{2})=(t_{2}-t_{0})(t_{2}-t_{1})$
>
>The determinant is the product of the diagonal entries of $U$
>$\det(U)=(t_{1}-t_{0})(t_{2}-t_{0})(t_{2}-t_{1})$

Consider $d+1$ data points $(t_{0},y_{0}),\dots,(t_{d}y_{d})$ such that $t_{i}\not=t_{j}$ for $i\neq j$. There exist a unique polynomial $p(t)$ of degree ( at most ) $d$ such that $p(t_{k})=y_{k}$ for each $k$

>[!proof]
>The formula for the determinant of the Vandermonde matrix shows that $\det(A)\neq{0}$ when the values $t_{k}$ are distinct therefore it is invertible and so there is a unique solution of the system $A\vec{c}=\vec{y}$


>[!example]
>Find the unique polynomial of degree $3$ which interpolates the points
>$$(0,-1),(1,-1),(2,1),(3,-1)$$
>
>Solve the system $A\vec{c}=\vec{y}$
>
>$$
>A=\begin{bmatrix}1 & 0 & 0 & 0 \\
1 & 1 & 1 & 1 \\
1 & 2 & 4 & 8 \\
1 & 3 & 9 & 27\end{bmatrix}
>\quad y=\begin{bmatrix}-1 \\
-1 \\
1 \\
-1\end{bmatrix}
>
>$$
>Lets compute the [[LU Decomposition]] of the Vandermonde matrix $A$ so that we can reuse the result in our other examples
>
>$$L=\begin{bmatrix}1 & 0 & 0 & 0 \\
1 & 1 & 0 & 0 \\
1 & 2 & 1 & 0 \\
1 & 3 & 3 & 1\end{bmatrix}
\quad U=\begin{bmatrix}1 & 0 & 0 & 0 \\
0 & 1 & 1 & 1 \\
0 & 0 & 2  & 6 \\
0 & 0 & 0 & 6\end{bmatrix}$$
>
>Solve the systems $Lx=y$ and $Uc=x$ to find
>$$c=\begin{bmatrix}-1 & -3 & 4 & -1\end{bmatrix}$$
>
>Therefore the interpolating polynomial is $p(t)=-1-3t+4t^{2}-t^{3}$

Note. The [[Error Analysis#Condition number | condition number]] of a Vandermonde matrix gets very large as the size of the matrix increases.
This means that interpolation by the monomial basis is very sensitive to change on the data for polynomials of large degree. For example, for $11$ equally spaced points $t_{0}=0,\dots,t_{10}=10$ the Vandermonde matrix $A$ is $11\times 11$ and has a condition number larger than $10^{12}$

# Cubic spline interpolation

Consider $N+1$ points $(t_{0},y_{0}),\dots,(t_{N},y_{N})$. A cubic spline is a function $p(t)$ defined piecewise by $N$ cubic polynomials $p_{1}(t),\dots,p_{N}(t)$ where
$$
p_{k}(t)=a_{k}(t-t_{k-1})^{3}+b_{k}(t-t_{k-1})^{2}+c_{k}(t-t_{k-1})+d_{k}\quad ,\quad t\in[t_{k-1},t_{k}]
$$
such that $p(t),p'(t),p''(t)$ are continuous functions

Each polynomial $p_{k}(t)$ is defined by our four coefficients therefore we require $4N$ equations to specify the $4N$ unknowns

Interpolation at the left endpoints yields $N$ equations:
$$p_{k}(t_{k-1})=y_{k-1}\quad ,\quad k=1,\dots,N$$
Interpolation at the right endpoints yields $N$ equations:
$$p_{k}(t_{k})=y_{k}\quad ,\quad k=1,\dots N$$
Continuity of $p'(t)$ yields $N-1$ equations:
$$p_{k}'(t_{k})=p'_{k+1}(t_{k})\quad ,\quad k=1,\dots,N-1$$
Continuity of $p''(t)$ yields $N-1$ equations:
$$p_{k}''(t_{k})=p_{k+1}''(t_{k})\quad ,\quad k=1,\dots,N-1$$

The conditions impose only $4N-2$ equations therefore we need two more to determine the cubic spline uniquely. There are different choices such as the natural cubic spline and the "not-a-knot" condition

>[!defintion]
>A natural cubic spline satisfies $p''_{1}(t_{0})=p_{N}''(t_{N})=0$


Represent a cubic spline $p(t)$ by the coefficient matrix
$$C=\begin{bmatrix}a_{1} & a_{2} & \dots & a_{N} \\
b_{1} & b_{2} & \dots & b_{N} \\
c_{1} & c_{2} & \dots & c_{N} \\
d_{1} & d_{2} & \dots & d_{N}\end{bmatrix}$$
where the $k\text{th}$ column consists of the coefficients for the $k\text{th}$ cubic polynomial in the spline

Consider $N+1$ points $(t_{0},y_{0}),\dots,(t_{N},y_{N})$ with $t_{i}\neq t_{j}$ for $i\neq j$. The unique natural cubic spline $p(t)$ which interpolates the points is given by the matrix $C$
$$C=\begin{bmatrix}a_{1} & a_{2} & \dots & a_{N} \\
b_{1} & b_{2} & \dots & b_{N} \\
c_{1} & c_{2} & \dots & c_{N} \\
d_{1} & d_{2} & \dots & d_{N}\end{bmatrix}$$
where $d_{k}=y_{k-1}$ for $k=1,\dots,N$ and the coefficients $a_{1},b_{1},c_{1},\dots,a_{N},b_{N},c_N$ are the solutions of the linear system 

$$
\renewcommand{\arraystretch}{1.5}
\left[ \begin{array}{c|c|c|c|c}
A(L_1) & B & & & \\ \hline
& A(L_2) & B & & \\ \hline
& & \ddots & \ddots & \phantom{A(L_{N-1})} \\ \hline
\phantom{A(L_{N-1})} & \phantom{A(L_{N-1})} & \phantom{A(L_{N-1})} & A(L_{N-1}) & B \\ \hline
T & & & & V
\end{array} \right]
\renewcommand{\arraystretch}{1}
\begin{bmatrix} a_1 \\ b_1 \\ c_1 \\ \vdots \\ a_N \\ b_N \\ c_N \end{bmatrix}
=
\begin{bmatrix} y_1 - y_0 \\ 0 \\ 0 \\ \vdots \\ y_N - y_{N-1} \\ 0 \\ 0 \end{bmatrix}
$$
where $L_{k}=t_{k}-t_{k-1}$ is the length of the subinterval $[t_{k-1},t_{k}]$ and

$$A(L)=\begin{bmatrix}L^{3} & L^{2} & L \\
3L^{2} & 2L & 1 \\
6L & 2 & 0\end{bmatrix}\quad B=\begin{bmatrix}0 & 0 & 0 \\
0 & 0 & -1 \\
0 & -2 & 0\end{bmatrix}$$
$$T=\begin{bmatrix}0 & 0 & 0 \\
 0 & 2 & 0 \\
0 & 0 & 0\end{bmatrix}\quad V=\begin{bmatrix}L^{3}_{N} & L^{2}_{N} & L_{N} \\
0 & 0 & 0 &  \\
6L_{N} & 2 & 0\end{bmatrix}$$

>[!example]
>Let $p(t)$ be the natural cubic spline which interpolates the data
>$$(0,1),(1,3),(2,8),(3,10),(4,9),(5,-1),(6,-17)$$
>Suppose the coefficient matrix of $p(t)$ is 
>
>$$C=\begin{bmatrix}1 & -2 & 1 & a_{4} & 1 & 1 \\
0 & 3 & -3 & b_{4} & -6 & -3 \\
1 & 4 & 4 & c_{4} & -5 & -14 \\
1 & 3 & 8 & 10 & 9 & -1\end{bmatrix}$$
>
>Determine the coefficients $a_{4},b_{4},c_{4}$ and then compute the value $p''(2.5)$
>First note that the $t$ values are equally spaced therefore $L_{k}=t_{k}-t_{k-1}=1$ for each $k$. Continuity of $p(t),p't$ and $p''(t)$ yields the equations
>$$\begin{align}p_{k}(t_{k})=p_{k+1}(t_{k}) & \implies a_{k}+b_{k}+c_{k}+d_{k}=d_{k+1} \\ p'_{k}(t_{k}=p_{k+1}''(t_{k}) & \implies3a_{k}+2b_{k}+c_{k}=c_{k+1} \\ p''_{k}(t_{k})=p''_{k+1}(t_{k})&\implies 6a_{k}+2b_{k}=2b_{k+1}\end{align}$$
>From these equations we can read that $b_{4}=0,\quad c_{4}=0,\quad a_{4}=-2$ from the equation $6a_{4}+2b_{4}=2b_{5}$
>The value $t=2.5$ is in the interval $[t_{2},t_{3}]$ therefore we compute
>$p''(2.5)=p_{3}''(2.5)=6a_{3}(2.5-2)+2b_{3}=-3$

Note the condition number of the matrix for constructing the natural cubic spline does not increase as drastically with the number of points $N+1$ as compared with the Vandermonde matrix. For example, for $11$ equally spaced points $t_{0}=0,\dots,t_{10}=10$, the Vandermonde matrix is $11$ by $11$ and has the $\text{cond}(A)\approx{1}0^{12}$ whereas the cubic spline matrix is $30$ by $30$ and the condition number is only around $33$.