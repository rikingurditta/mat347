# Tensor Products

$$
\newcommand{\ds}{\displaystyle}
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\angles}[1]{\left\langle #1 \right\rangle}
\newcommand{\inv}[1]{#1^{-1}}
\newcommand{\divides}{ {\large\mid} }
\newcommand{\ndivides}{ {\large\not\mid} }
\newcommand{\th}{^{\text{th}}}

\newcommand{\Sp}{\mathbb S}
\newcommand{\F}{\mathbb F}
$$

## Tensor Products

Suppose $M$ is an $R$-module and $R$ is a subring of $S$. Can we extend $M$ to be an $S$-module?

In general, the answer is no. For example, suppose $M$ is a finite abelian group, then it is a module over $\Z$. Then since it is finite, we cannot extend it to be a module over $\Q$, as every vector space over $\Q$ is infinite.

Instead, we could ask "To what extent can we extend our $R$-module?"

Consider the free abelian group made from the set $S \times M$, i.e. all formal sums of elements $(s, m)$. We want to think of pairs of $(s, m)$ as multiplying $s \cdot m$, and we want these pairs to end up satisfying the module axioms. To do this, we will take a quotient on this free group.

Let $N$ be the subgroup containing all elements of the form:

- $(s_1 + s_2, m) - (s_1, m) - (s_2, m)$
- $(s, m_1 + m_2) - (s, m_1) - (s, m_2)$
- $(sr, m) - (s, rm)$

Then if we take the quotient $(S \times M) / N$, we get an object where each type of element listed above represents $0$, which imposes distributivity and associativity.

We call $(S \times M) / N$ the **tensor product of $S$ and $M$ over $R$** and denote it by $S \otimes_R M$ (or just $S \otimes M$ if the underlying ring is clear). If $(s, m) \in S \times M$, we denote the coset they belong to in $S \otimes M$ by $s \otimes m$, because we are thinking of each coset as a "product". Because of the equivalences we defined with our quotient, we have:

- $(s_1 + s_2) \otimes m = s_1 \otimes m + s_2 \otimes m$
- $s \otimes (m_1 + m_2) = s \otimes m_1 + s \otimes m_2$
- $sr \otimes m = s \otimes rm$

Elements of the form $s \otimes m$ are called **simple tensors** and elements of $S \otimes M$ in general are called **tensors**.

### Example: $\Q \otimes_\Z \Z/p\Z$

Suppose $\overline{m} \in \Z/p\Z$, then

$$
\begin{align*}
1 \otimes_\Z \overline m &= \frac{1}{p} \cdot p \otimes_\Z \overline m \\
&= \frac{1}{p} \otimes_\Z p \cdot \overline m \tag{$sr \otimes m = s \otimes rm$} \\
&= \frac{1}{p} \otimes_\Z 0 \tag{$\overline m \in \Z/p\Z$} \\
&= \frac{1}{p} \otimes_\Z 0 \cdot 0 \\
&= \frac{1}{p} \cdot 0 \otimes_\Z 0 \\
&= 0 \otimes_\Z 0
\end{align*}
$$

so $\Q \otimes_\Z \Z/p\Z = \curlies 0$.

### Universal property of tensor products

Let $M$ be an $R$-module, let $S$ be a ring so that $R \subseteq S$, and consider the $S$-module $S \otimes_R M$. Consider the inclusion function

$$
\begin{align*}
\iota : M &\to S \otimes_R M \\
m &\mapsto 1 \otimes m
\end{align*}
$$

Suppose $L$ is a (left) $S$-module, then $L$ is also an $R$-module.

Let $\phi : M \to L$ be an $R$-module homomorphism. Then there is a unique $S$-module homomorphism $\Phi : S \otimes_R M \to L$ so that $\Phi \circ \iota = \phi$.

![universal property of tensor products.png](universal property of tensor products.png)