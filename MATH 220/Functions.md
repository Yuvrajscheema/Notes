>[!Definition]
For non empty sets $A$ and $B$, a **function**  $f$ from $A$ to $B$ written $f:A \rightarrow B$ is a subset of $A\times B$ with two further properties
>- for every a in A there is some b in B such that $(a,b) \in f$
>- If $(a,b) \in f \text{ and } (a,c) \in f \text{ then } b = c$
>In other words, any input has exactly one output

- $A$ is the domain and $B$ is the co-domain
- The range of $f$ is the set of elements in $B$ that are mapped to by 
  $f$: range($f$) $= \{ b\in B \mid \exists a\in A \text{ s.t. } f(a) = b \}$
 - *Image* and *pre-image*, Let $f: A \rightarrow B$  be a function, and let $C \subseteq A$ and let $D\subseteq B$ 
	 - The set $f(C) = \{ f(x) \mid x \in C \}$ is the **image** of $C$ in $B$
	 - The set $f^{-1}(D) = \{ x \in A \mid f(x)\in D \}$ is the **preimage** of $D$ in $A$
	 - $f^{-1}$ does not necessarily represent the inverse function
>[!example] 
>$A = \{ a,b,c,d,e \}, B = \{ 1,2,3,4,5 \}$
>$a \rightarrow 1, b \rightarrow 1, c \rightarrow 4, d,e \rightarrow 5$
>Image of $\{ a,b,c \}:f(\{ a,b,c \}) = \{ 1,4 \}$
>Image of $(a,b) = \{ 1 \}$
>Pre-Image of $\{ 4,5 \}:f^{-1}(\{ 4,5 \}) = \{ c,d,e \}$
>Pre-Image of $\{ 2,3 \}:f^{-1}(\{ 2,3 \}) = \varnothing$
>Pre-Image of $\{ 1,2 \}:f^{-1}(\{ 1,2 \}) = \{ a,b \}$

>[!Problem 1]
>Suppose that $f:A\rightarrow B$ is a function and let $C$ be a subset of $A$. Prove that $f(A) - f(C) \subseteq f(A-C)$
>Let $y \in f(A) - f(C)$. We want to show $y \in f(A-C)$ Lowkey don't know how to do this
>So  $y \in f(A) \text{ and } y \not\in f(C)$
>Since $y\in f(A) \text{ then } \exists x \in A \text{ s.t. } f(x) = y$
>Since $y \not\in f(C)$, there does not exist $z\in C$ s.t. $f(z) = y$
>We know $x\in A$ and $x\not\in C$ given the line above, So $x \in A-C$
>Therefore $f(x) \in f(A-C)$
>Since $f(x) \in y$, then $y\in f(A-C)$

>[!Problem 2]
>Suppose that $f:A\rightarrow B$ is a function and let $C$ be a subset of $A$.
>Prove that $f(A) - f(C) \supseteq f(A-C)$ does not always hold
>Let $A = \{ 1,2,3 \}$, $B = \{ 4,5,6 \}$, $C = \{ 3 \}$
>Define $f$ to be such that $f(1) = 5, f(2) = f(3) = 6$
>Then $f(A) = \{ 5,6 \}$, $f(C) = \{ 6 \}$ and $f(A) - f(C) = \{ 5 \} \not\supset f(A-C) = {5,6}$
- Injective $\Rightarrow$ **no overlap**, everything maps to a distinct value, nothing in the range has more than one corresponding domain value, $f(a_{1}) = f(a_{2)} \Rightarrow a_{1} = a_2$ and $a_{1}\neq a_{2} \Rightarrow f(a_{1}) \neq f(a_{2})$
- Surjective $\Rightarrow$ **every** point in $B$ is mapped to by $f$, $\forall b \in B, \exists a \in A \text{ s.t. } f(a) = b$ 
>[!Example]
>(a) Find a function $f: \mathbb{Z} \rightarrow \mathbb{Z}$ which is injective but not surjective
>(b) Surjective but not injective
>(c) What would happen if we replaced $\mathbb{Z}$ with a finite set in the questions above

- (a) $f(x) = 5x$, $\checkmark$
- (b) $g(x) = x^3-4x$, $\checkmark$
- (c) No clue
>[!Answer]
>(a) Define $f(n) = 2n, \forall n \in \mathbb{Z}$ 
><u>**Prove that it is injective**</u>: Assume $f(a_{1}) = f(a_{2})$ for some $a_{1}, a_{2} \in \mathbb{Z}$. Then $2a_{1} = 2a_{2} \Rightarrow a_{1} = a_{2}$ as required so $f$ is injective
><u>**Prove that it is not surjective**</u>: Consider $1 \in \mathbb{Z}$. If $1 \in \text{ range}(f)\dots$
>(b) $g(m) \begin{cases} m, m \leq 0 \\ m-1, m > 0 \end{cases}$ 
><u>**Prove that it is surjective**</u>: Given $y \in \mathbb{Z}$, we will show that $\exists x\in \mathbb{Z}$ s.t. $g(x) = y$
> Case 1: $y \leq 0$: Let $x = y$, then $g(x) = g(y) = y \checkmark$ 
> Case 2: $y > 0$: Let $x = y+1$, then $g(x) = g(y+1) \checkmark$
> <u>**Prove that it is not injective**</u>: Note that $g(0) = 0$ and $g(1) = 0$
>(c) Not possible if domain $=$ co-domain
- **Bijections**: If $f$ is both surjective and injective then $f$ is bijective
>[!Example]
>(a) Prove that the function $f: \mathbb{R} \rightarrow \mathbb{R}, f(x) = x^3$ is bijective
>(b) Prove that the function $f: \mathbb{R} \rightarrow \mathbb{R}, f(x) = x^4$ is not bijective
- (a) $x^3$
	- **Injective**: Given $a,b \in \mathbb{R}$ s.t. $f(a) = f(b)$, we have $a^{3}= b^{3}\Rightarrow a = b$ so $f$ is injective
		- **Surjective**: Given $y \in \mathbb{R}$, let $x = \sqrt[3]{  y} = y$, so $f$ is surjective
- (b) $x^4$ 
	- **Injective**: $f(-1) = f(1) =1$ so $\exists a,b \in \mathbb{R}$ s.t. $f(a) = f(b) \wedge a \neq b$ so $f$ is not injective
>[!Problem 3]
>Prove that the function $f: \mathbb{R} - {1} \rightarrow \mathbb{R} - \{ 2 \}$ given by $f(x) = \frac{2x}{x - 1}$ is bijective
><u>**Injective**</u>: Assume $f(a) = f(b)$ for some $a,b \in \mathbb{R} - \{ 1 \}$
>$\Rightarrow \frac{2a}{a-1} = \frac{2b}{b-1}$
>$\Rightarrow 2a(b-1) = 2b(a-1)$
>$\Rightarrow ab -a = ab - b$
>$\Rightarrow a = b$ so $f$ is injective
><u>**Surjective**</u>: Given $y \in \mathbb{R} - \{ 2 \}$ let $x = \frac{y}{y-2}$
>$\Rightarrow x-1 = \frac{2}{y-2}$
>$\Rightarrow \frac{1}{x-1} = \frac{y-2}{2}$ We can divide by $y-2$ as $y \neq 2$
>$\Rightarrow \frac{y}{2} = 1+\frac{1}{x-1}$ 
>$\Rightarrow \frac{y}{2} = \frac{x}{x-1}$
>$\Rightarrow y = \frac{2x}{x-1} = f(x)$, so $f$ is surjective
>Since $f$ is injective and surjective, $f$ is bijective


Scratch for problem 3
	We want $x$ s.t. $y = \frac{2x}{x-1} \Rightarrow \frac{y}{2} = \frac{x}{x-1}$ Now we do something funny $\frac{y}{2} = \frac{x-1+1}{x-1} = 1+\frac{1}{x-1}$ $\frac{y-2}{2} = \frac{1}{x-1} \Rightarrow x-1 = \frac{2}{y-2}$ so we have $x = \frac{y}{y-2}$

>[!Problem 4]
>(a) Let $f: A \rightarrow B$ be a surjection and let $D_{1},D_{2}\subseteq B$. Show that if $f^{-1}(D_{1})\subseteq f^{-1}(D_{}2)$ then $D_{1}\subseteq D_{2}$.
>Let $y\in D_{1}$. Consider $f^{-1}(\{ y \})$. Since $\{ y \}\subseteq D_{1}$, we have $f^{-1}(\{ y \})\subseteq f^{-1}(D_{1})$, and since $f^{-1}(D_{1}) = f^{-1}(D_{2})$, we have $f^{-1}(\{ y \})\subseteq f^{-1}(D_{2})$, let $x\in f^{-1}(\{ y \})$. Then $f(x) = y$, since $f$ is a surjection, $f^{-1}(\{ y \}) \neq \{  \}$ $x\in f^{-1}(D_{2})$, so let $f(x)\in D_{2}$. So $y\in D_{2}$. So $D_{1}\subseteq D_{2}$
>(b), posted online

>[!Definition]
>**Compositions**
>Let $f: A \rightarrow B$ and $g: B \rightarrow C$. The **composition** of $f$ and $g$ is 
>$g \circ f: A \rightarrow C$
>where $(g \circ f)(a) = g(f(a)), \forall a, \in A$

- **Order Matters!!**, $f(x) = x^3$ & $g(x) = 2x$, $g \circ f = g(f(x)) = 2x^3$ and $f \circ g = 8x^3$
# Inverses
>[! Definition]
><u> **Left Inverse** </u>
>Let $A = \{ a, b \}$ and $B = \{ 1,2,3 \}$, then $f: A \rightarrow B$ gives $f(a) = 1$ and $f(b) = 2$
>We can go in the reverse direction with $g: B \rightarrow A$, $g(1) = a$ and $g(2) = b$
>What we are looking for is $g \circ f (x) = x$ But $3$ doesn't map to anything so $g$ is not a function right now, lets let $g(3) = b$
>Does $g$ act as an inverse? 
>$g \circ f (a) = g(1) = a$
>$g \circ f(b) = g(2) = b$
>So we have that $g \circ f$ has the domain $A$ and co-domain $A$
>So $g \circ f : A \rightarrow A$, $g \circ f$ is the identity function on $A$
>So $g$ is a left inverse of $f$ as we can put it on the left to be an inverse
- We say an inverse because there can be more than one inverse
- Another left inverse of $f$, $h: B \rightarrow A$, $h(1) = a$, $h(2) = b$ and $h(3) = a$ so $h \neq g$ but they 
- are both left inverses of $f$
>[!Definition]
><u>**Right Inverse** </u>
>$S = \{ c, d, e \}$, $T = \{ 4, 5 \}$
>$f: S \rightarrow T$, $f(c) = 4, f(d) = 5, f(e) = 5$
>This $f$ does **not** have a left inverse! Because $f$ is not injective
>Let $g: T \rightarrow S, g(4) = c, g(5) = d$
>So we have $f \circ g (4) = 4$ and $f \circ g (5) = 5$
>So $g$ is a right inverse of $f$

- Once again there is another right inverse, $h: T \rightarrow S$ with $h(4) = c$ and $h(5) = e$
- $g \neq h$ but they are still both right inverses of $f$

- Formally we have $i_{A}$ be the identity function on $A$ and $i_{B}$ on $B$
- let $f: A \rightarrow B$ and $g: B \rightarrow A$
- if $g \circ f = i_{A}$ then $g$ is a left inverse of $f$
- if $f \circ g = i_{B}$ then $g$ is a right inverse of $f$
- if $g$ is both the right and left inverse of $f$ then $g$ is the inverse of f
- A function only has an if and only if it is bijective
- A function has a left inverse iff it is injective
- A function has a right inverse iff it is surjective
>[!Problem 5]
>Let $f: A \rightarrow B$ be a function. Prove:
>(a) If there is a function $g: B \rightarrow A$ that is a left inverse of $f$, $\forall x \in A$
>Then $f$ is injective
>(b) Prove that if $f$ is injective then there is a function $g:B \rightarrow A$ such that $g \circ f(x) = x, \forall x\in A$

 - (a)
	 - Assume $f(x_{1}) = f(x_{2})$ for some $x_{1},x_{2} \in A$. We want to show $x_{1} = x_{2}$
	- Apply $g: g(f(x_{1})) = g(f(x_{2}))$
	- Since $g \circ f (x) = x: x_{1} = x_{2}$
	- So $f$ is injective
- (b)
	- We can construct a function $g: B\rightarrow A$
	- Given $b \in B$
	- **Case 1**: $b \in$ range($f$)
		- Prove is in notes 20 on pages
	- **Case 2**: $b \in$ range(f)
		- Fix $z \in A$ independant of b
		- Define $g(b) = z$
	- This defines our function $g$
	- Consider $g \circ f (x) = g(f(x))$ for any $x \in A$ 
	- Since $f(x) \in$ range($f$), by definition of $g$, we have $g(f(x)) = x, \forall x \in A$.
	- So $g$ is a left inverse for $f$
### Practice
- Find a function has a right inverse but no left inverse
- Let $f(x) = x^2$, $f:\mathbb{R} \rightarrow [0, \infty)$ so $f$ is surjective on its domain
- Therefore It has a right inverse
- Let $g(x) = \sqrt{x }, g: [0, \infty) \rightarrow \mathbb{R}$
- Then $f \circ g(x) = f(g(x)) = f(\sqrt{x }) = x$. So $g$ is a right inverse of $f$ 
- $f$ does not have a left inverse : Let's claim that $h: [0, \infty) \rightarrow \mathbb{R}$ is a left inverse of $f$
- Then we must have $h \circ f(x) = x, \forall x\in \mathbb{R}$ 
- But we must have $h \circ f(-1) = h(1) = -1$ and $h \circ f(1) = h(1) = 1$ which doesn't make sense and is not possible
- So $h$ doesn't exist

