# 1 Carefully define or restate each statement
## a) A rational number $q\in\mathbb{Q}$
I don't know the actual answer lmao
<mark style="background: #FF5582A6;">Solution:</mark> $q\in\mathbb{Q}$ if there exists co-prime $a,b \in \mathbb{Z}$ where $b\neq=$ such that $q=\frac{a}{b}$
## b) Bezouts lemma
For some $a,b\in\mathbb{Z}, \quad \exists x,y\in \mathbb{Z}$ s.t. $ax+by=\gcd(a,b)$
## c) The Fundamental Theorem of Arithmetic
IDK
<mark style="background: #FF5582A6;">Solution:</mark>   Let $n\in\mathbb{N}$. Then $n$ can be uniquely factorized into a product of prime powers $p_{1}^{e_{1}}p_{2}^{e_{2}}\dots p_{n}e^{e_{n}}$ up to order where $p_{i}$ are distinct primes and $e_{i}\in\mathbb{Z}$
## d) A convergent sequence $(x_{n})_{n\in\mathbb{N}}:\mathbb{N}\mapsto \mathbb{R}$
IDK!!!!! confusing ass questions
<mark style="background: #FF5582A6;">Solution:</mark> $(x_{n})_{n\in\mathbb{N}}:\mathbb{N}\mapsto\mathbb{R}$ converges to $L\in\mathbb{R}$ if for all $\varepsilon > 0\in\mathbb{R}$, there exists $n\in\mathbb{N}$ such that for all $n>N,|x_{n}-L|<\varepsilon$.

## e)The principle of mathematical induction
Given a base case, assume that the statement holds for some value $k$, show that that implies that it also holds for $k+1$
<mark style="background: #FF5582A6;">Solution:</mark> Let $l\in\mathbb{Z}$ and let $S=\{ k\in\mathbb{Z} | n\geq l\}$. If $P(l)$ is true and $P(k)$ being true implies $P(k+1)$ being true for some $k\in S$, then $P(n)$ is true for all $n\in S$

# 2 Write the negation of each the following and prove or disprove the original statement
## a) For all $x \in\mathbb{R}$, there exists $y\in\mathbb{R}$ such that for all $z\in\mathbb{R}$, if $x+y<z$, then $x-y>z$
Take the negation $\exists x\in\mathbb{R}$ s.t. $\forall y\in\mathbb{R}$, $\exists z\in\mathbb{R}$ s.t. $(x+y<z)\wedge(x-y\leq z)$
Let $x=0$, then let $z=|y|+1$, then $x+y=y<|y|+1$ and $x-y=-y\leq|y|<|y|+1$ showing that the negation is true, thus the original statement is false.

## b) $\exists x\in\mathbb{R}$ s.t. $\forall y\in\mathbb{R}$, for all $z\in\mathbb{R},xy>z$
Take the negation, $\forall x\in\mathbb{R},\exists y\in \mathbb{R}$ s.t. $\exists z\in\mathbb{R}$ s.t. $xy\leq z$
Let $y=0$ and let $z=1$, then $xy=0<1=z$ so $xy\leq z$ holds and the original statement is false

# 3 Let $f:A\mapsto B$ and $g:B\mapsto C$ be functions. Prove or disprove each of the following: 
## a) $\forall U \subseteq C,(g\circ f)^{-1}(U)=f^{-1}(g^{-1}(U))$
<mark style="background: #FF5582A6;">Solution:</mark> Assume the original statement, we show each inclusion in turn
- Assume $x \not\in f^{-1}(g^{-1}(U))$, so $f(x)\not\in g^{-1}(U)$ and $g(f(x))\not\in U$. It follows that $x\not\in(g\circ f)^{-1}(U)$, so by contrapositive, $(g\circ f)^{-1}(U)\subseteq f^{-1}(g^{-1}(U))$
- Assume $x\in f^{-1}(g^{-1}(U))$. Then $f(x)\in g^{-1}(U)$ and $g(f(x))\in U$ so $g\circ f)^{-1}(U)\subseteq f^{-1}(g^{-1}(U))$