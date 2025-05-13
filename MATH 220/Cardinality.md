- How can you count to infinity?
- We are familiar with infinite sets. Should we think of them as being of different sizes?
- We need to come up with a different strategy
## Defining Cardinality
- Let $f:A \rightarrow B$ where there are more elements in set $B$ than $A$, $f$ can be injective but not surjective
- For injective $|A| \leq|B|$ and $|A|\geq|B|$ for surjective
- Therefore for a function to be bijective $|A| = |B|$
- We extend these ideas to infinite sets!
>[!Definition]
>Two sets have the same **cardinality** if there exists a bijection between them
>_Notation_: If two sets have the same cardinality, then we write $|A|=|B|$
- If two sets have the equal cardinality can be said to be equinumerous
- denumerable: same cardinality as $\mathbb{N}$
- countable: set is finite
- uncountable: set is not countable
- Do $(0,1)$ and $(0,1]$ have the same cardinality? yes, this is hard as fuck to prove though
>[!Definition]
>Let $A$ and $B$ be sets
> - We write $|A|\leq|B|$ if there is an injection from $A\rightarrow B$
> - We write $|A|<|B|$ if $|A|\leq|B|$ and $|A|\neq|B|$
> - We write $|A|\geq|B|$ if there is a surjection from $A \rightarrow B$
> - We write $|A|>|B|$ if $|A|\geq|B|$ and $|A|\neq|B|$

# Pigeon hole principle
>[!Theorem]
>If $n$ objects are placed in $k$ boxes
>If $n>k$ then there exists at least one box which has two objects in it
>If $n<k$ then there exists a box that is empty
# Infinity Tower
>[!Theorem]
>Let $S$ be a set. Then the power set of $S$, denoted by $\mathcal{P}(S)$ satisfies
>$|S|\leq|\mathcal{P}(S)|$
# Cantor-Schroder-Berstein (CSB)
>[!Theorem]
>Let $A$ and $B$ be sets. If $|A|\leq|B|$ and $|A|\geq|B|$ then $|A|=|B|$
## Examples
>[!Example]
>1. Lets show that $|(0,1)|=|0,2|$
>2. Show that $|[3,\infty)|=|5,\infty)$

- 1. Define $f:(0,1)\rightarrow(0,2)$
	- let $f(x)=2x$ 
	- Now lets prove that the function is bijective
	- Injective:$f(a)=f(b), a,b \in (0,1)$ $f(a)=2a,f(b)=2b \implies a=b$ so injective
	- Surjective: Given $c\in(0,2)$ then let $x=\frac{c}{2} \in (0,1)$ then $f\left( \frac{c}{2} \right) = \frac{2\cdot c}{2} =c$
	- Since $f$ is bijective then $|(0,1)|=|0,2|$
- 2. Define $g:[3,\infty)\rightarrow[5,\infty)$
	- Let $g(x) = x+2$
	- find the inverse
	- $h:[5,\infty)\rightarrow[3,\infty)$
	- $h(y) = y-2$
	- Then $g\circ h (x) = h(g(x)) = x$
	- And $h \circ g(y) = h(g(y)) = y$
	- So $h$ is a two sided inverse of $g$, so $g$ is bijective. So $|[3,\infty)| = |[5,\infty)|$
## Problems
>[!Problem 1]
>Show that $|(0,1)| = |(0,\infty)|$

- $\tan\left( \frac{\pi}{2}x \right)$ lmao
- Let $f:(0,1)\rightarrow(0,\infty)$
- let $f(x) = \frac{1}{x}$
- $g:(1,\infty) \rightarrow(0,\infty)$, $g(y) = y-1$
- Then other things posted in the notes online
>[!Problem 2]
>Prove or disprove: for every $n \in \mathbb{N}, \exists$ distinct $k,l \in \mathbb{N}$ s.t. $11 \mid (a^k-a^l)$

- send help lmao prof save me ;-;
- Scratch:
	- Boxes: number of of values in $\pmod {11}$, 11 of them
	- Birds, powers of $a$
	- So there must be a box with two powers in it
	- $a^{k}\equiv a^{l} \pmod{11}$
>[!Proof]
>Consider $a^{1},a^2,\dots{},a^{12}$.
>There are eleven equivalence classes in mod 11.
>By the PHP  least two of $a^{1},a^2,\dots{},a^{12}$ must be in the same equivalence class in mod 11.
>So $\exists k,l\in\mathbb{N}$ s.t. $k\neq l$ and $a^{k}\equiv a^{l}\pmod{11} \implies a^{k}-a^{l}\equiv{0}\pmod{11}$ so $11 \mid a^{k}-a^{l}$

>[!Problem 3]
>Given an example of two sets $A$ and $B$ that are both uncountable but $|A|\neq|B|$

- Lets take $|A| = \mathbb{R}$ and $|B| = \mathcal{P}(S)$ then $|A|<|B|$ due to a theorem from class
>[!Problem 4]
>Prove that $|(0,1)|=|(0,1]|$

- Lets use CSB
- for $(0,1)\rightarrow(0,1]$ we take $f(x) = x$ which is injective(gotta actually prove this) so $|(0,1)|\leq|(0,1]|$
- for $(0,1]\rightarrow(0,1)$ we take $g(x) = \frac{x}{2}$ which is injective so $|(0,1]| \leq |(0,1)|$
- Since $|(0,1)|\leq|(0,1]|$ and $|(0,1]| \leq |(0,1)|$ so by CSB theorem $|(0,1)|=|(0,1]|$
