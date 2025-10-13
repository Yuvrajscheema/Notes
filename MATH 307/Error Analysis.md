# Big Idea

The condition number if a nonsingular matrix $A$ is $\text{cond}(A)=||A||||A^{-1}||$.
Given a linear system $Ax=b$, the condition number of $A$ quantifies how sensitive the solution $x$ is relative to changes in $b$

# Vector norms

>[!definition]
>
>The **Euclidean** norm of a vector $x \in \mathbb{R}^{n}$ is 
>$$
>||x||=\sqrt{ |x_{1}|^{2} +\dots+|x_{n}|^{2}}=\sqrt{ \sum_{k=1}^{n} |x_{k}|^{2} }
>$$
>Note the Euclidean norm assigns a magnitude or length to a vector but it turns out that there are many different ways to define the "magnitude" of a vector!

>[!definition]
>A norm on $\mathbb{R}^{n}$ is a function $\big{|}\big{|}\cdot\big{|}\big{|}$ such that:
> 1. $||x|| \geq{0}\forall x \in \mathbb{R}^{n}$
> 2. $||x|| = 0 \iff x=0$
> 3. $||cx||=|c| ||x||$ for any $c\in \mathbb{R}$ and $x \in \mathbb{R}^{n}$
> 4. $||x+y||\leq||x||+||y||\forall x,y \in \mathbb{R}^{n}$

Condition 4 is called the triangle inequality

>[!definition]
>Let $1\leq p<\infty$ the $p$-norm of a vector $x \in \mathbb{R}^{n}$ is given by 
>$$||x||_{p}=\left( \sum_{k=1}^{n} |x_{k}|^{p} \right)^{1/p}$$
>In particular the 1-norm is given by 
>$$||x||_{1}=|x_{1}|+\dots+|x_{n}|$$
>and the 2-norm is the familiar Euclidean norm given by
>$$||x||_{2}=\sqrt{ |x_{1}|^{2} +\dots+|x_{n}|^{2}}$$
>
>The $\infty$-norm of a vector $x\in \mathbb{R}^{n}$ is given by
>$$||x||_{\infty}=\max\{|x_{1}|,\dots,|x_{2}|\}$$

# Matrix norms

>[!definition]
>A matrix norm is a function on matrices that satisfies the properties:
>1. $||A||>0\forall A\neq0$
>2. $||A||=0\iff A=0$
>3. $||cA||=|c|||A||$ for any $c\in \mathbb{R}$
>4. $||A+B||\leq||A||+||B||$
>5. $||AB||\leq\|A\|\|B\|$
## Frobenius norm

The **Frobenius norm** of a matrix $A$ is given by
$$\|A\|_{F}=\sqrt{ \sum_{i=1}^{m} \sum_{j=1}^{n} \|a_{i,j}\|^{2} }$$
where $a_{i,j}$ are entries of $A$

## Operator norm

The operator norm of a matrix $A$ is given by
$$\|A\|=\max_{\boldsymbol{x} \not= \boldsymbol{0}} \frac{\|Ax\|}{\|x\|}  $$
where $\|\cdot\|$ is the 2-norm

Note the operator norm satisfies the property $\|Ax\|\leq\|A\|\|x\|\forall x\in \mathbb{R}^{n}$

>[!theorem]
>Let $A$ be a nonsingular matrix. Then
>$$\|A\|=\max_{\|x\|=1}\|Ax\|\quad \text{and}\quad \|A^{-1}\|=\frac{1}{\min_{\|x\|=1}\|A\|}$$
>In other words, $\|A\|$ is the _maximum_ stretch of a unit vector by the linear transformation $A$ and $\|A^{-1}\|$ is the reciprocal of the minimum stretch of a unit vector by the linear transformation $A$

>[!proposition]
>Let $D$ be a diagonal matrix and let $d$ be the vector of diagonal entries of $D$:
>Then $\|D\|=\|d\|_{\infty}=\max\{|d_{1}|,\dots,|dn|\}$ and $\|D\|_{F}=\|d\|_{2}$


Note. How do we compute the matrix norm $\|A\|$ for a general matrix? This is a nontrivial problem we will later see how to use the singular values of $A$ to determine the matrix norm


# Condition number

The condition number of a nonsingular square matrix $A$ is 
$$\text{cond}=\|A\\\|A^{-1}\|\|$$
By convention we define $\text{cond}(A)=\infty$ if $\det(A)=0$

Note if $A$ is nonsingular we have 
$$\text{cond}=\|A\\\|A^{-1}\|\|=\frac{\text{maximum stretch of a unit vector}}{\text{minimum stretch of a unit vector}}$$

# Relative Errors

Let $A$ be a non singular matrix and consider the linear system $Ax=b$. If a small change $\Delta b$ corresponds to a change $\Delta x$ in the sense that $A(x+{\Delta}x)=b+\Delta b$ then
$$\frac{\|\Delta x\|}{\|x\|}\leq\text{cond}(A) \frac{\|\Delta b\|}{\|b\|}$$

Given a vector $b$ and small change $\Delta b$ the relative change (or relative error) is
$$\frac{\|\Delta b\|}{\|b\|}$$

Note the error bound

$$\frac{\|\Delta x\|}{\|x\|}\leq\text{cond}(A) \frac{\|\Delta b\|}{\|b\|}$$
implies that if $A$ has a large condition number then a small changes in $b$ may result in _very_ large changes in the solution $x$. In other words, the solution $x$ is sensitive to errors in $\Delta b$
