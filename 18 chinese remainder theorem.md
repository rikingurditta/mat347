# Chinese Remainder Theorem

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

## Chinese Remainder Theorem

Suppose $gcd(m, n) = 1$, $0 \leq a < m$, and $0 \leq b < n$. Then there is a unique $k$ where $0 \leq k < nm$ so that $k \equiv a \bmod m$ and $k \equiv b \bmod n$.

For example, if $m = 6, n = 5, a = 4, b = 2$, then we want to find a number $k < 30$ so that $k \equiv 4 \bmod 6$ and $k \equiv 2 \bmod 5$. The only one that works is 22.

The theorem can be generalized as, for any set of $m_1, ..., m_r$ which are pairwise relatively prime, and with $a_1, ..., a_r$ with $0 \leq a_i < m_i$, then there is exactly one $\ds k < \prod_{i=1}^r m_i$ so that $k \equiv a_i \bmod m_i$ for each $i$.

### Product rings

Let $R, S$ be commutative rings with identity, then we can define the **product ring** as $R \times S = \curlies{(r, s) : r \in R, s \in S}$.

### Comaximal ideals

Suppose $I, J$ are ideals in $R$. They are **comaximal ideals** if $I + J = R$.

### Proof of Chinese Remainder Theorem

First, we generalize the theorem to any commutative ring with identity:

Suppose $A_1, ..., A_k$ are ideals in $R$.

Define a map

$$
\begin{align*}
\phi :R &\to R/A_1 \times ... \times R/A_k \\
r &\mapsto (r + A_1, ..., r + A_k)
\end{align*}
$$

This is a ring homomorphism whose kernel is $A_1 \cap ... \cap A_k$.

If each $A_i, A_j$ are comaximal, then

$$
A_1 \cap ... \cap A_k = A_1 \cdot ... \cdot A_k
$$

and $\phi$ is surjective.

Then we have

$$
R/(A_1 \cdot ... \cdot A_k) \cong R/A_1 \times ... \times R/A_k
$$

**Proof:**

Consider the kernel of $\phi$. Suppose $r \in \ker(\phi)$, then $r + A_i = A_i$ for every $i$, so $\ds r \in \bigcap_{i=1}^n A_i$. Conversely, if $\ds r \in \bigcap_{i=1}^n A_i$, then $r + A_i = A_i$ for every $i$, so $\phi(r) = (0, ..., 0)$, so $r \in \ker(\phi)$.

We will prove the next part by induction.

*Base case:*

Suppose $A_1, A_2$ are comaximal, so $A_1 + A_2 = R$. Then there exist $x \in A_1$ and $y \in A_2$ so that $x + y = 1$. If $z \in A_1 \cap A_2$, then $z = z \cdot 1 = z(x + y) = zx + zy$. $zx \in A_2 A_1$ and $zy \in A_1 A_2$, so $z = zx + zy \in A_1 A_2$. Thus $A_1 \cap A_2 \subseteq A_1 A_2$. It is clear that $A_1 A_2 \subseteq A_1 \cap A_2$, so $A_1 \cap A_2 = A_1 A_2$.

*Inductive step:*

> "The induction is easy" or something like that
>
> \- Joe

By induction, this holds for all $k$ pairwise comaximal ideals.

Now we will show that $\phi$ is surjective, again by induction.

*Base case:*

Suppose $A_1, A_2$ are comaximal ideals. We want to show that $\phi : R \to R/A_1 \times R/A_2$ is surjective. Suppose $x \in A_1$ and $b \in B_2$ so that $x + y = 1$. Then $1 + A_2 = x + y + A_2 = x + A_2$, and $1 + A_1 = x + y + A_1 = y + A_1$. Thus, $\phi(x) = (A_1, 1 + A_2)$ and $\phi(y) = (1 + A_1, A_2)$.

Now let $(a_1 + A_1, a_2 + A_2) \in R/A_1 \times R/A_2$. Using the work above, we know that

$$
\begin{align*}
\phi(a_2 x + a_1 y) &= \phi(a_2)\phi(x) + \phi(a_1)\phi(y) \\
&= \phi(a_2)(0 + A_1, 1 + A_2) + \phi(a_1)(1 + A_1, 0 + A_2) \\
&= (0 + A_1, a_2 + A_2) + (a_1 + A_1, 0 + A_2) \\
&= (a_1 + A_1, a_2 + A_2)
\end{align*}
$$

Thus, $\phi(R) = R/A_1 \times R/A_2$.

*Inductive step:*

> "The induction is easy" or something like that
>
> \- Joe

By induction, $\phi$ is always surjective when $A_1, ..., A_k$ are pairwise comaximal.

Using the first isomorphism theorem, we see that $R/\ker(\phi) = R/(A_1 \cdot ... \cdot A_k) \cong R/A_1 \times ... \times R/A_k$ 

This completes the proof. We can recover the classical form for integers if $R = \Z$.

## Rings of integers

Suppose $n = p_1^{\alpha_1} \cdot ... \cdot p_k^{\alpha_k}$. Then we have the ring isomorphism

$$
\Z/n\Z \cong \Z/p_1^{\alpha_1}\Z \times ... \times \Z/p_k^{\alpha_k}\Z
$$

Looking at just the units of this ring, we see that

$$
(\Z/n\Z)^\times \cong (\Z/p_1^{\alpha_1}\Z)^\times \times ... \times (\Z/p_k^{\alpha_k}\Z)^\times
$$

Suppose $\varphi : \N \to \N$ is Euler's totient function, then $\varphi(n) = \abs{(\Z/n\Z)^\times}$ is the number of units in $\Z/n\Z$, so

$$
\begin{align*}
\varphi(n) &= \abs{(\Z/n\Z)^\times} \\
&= \abs{(\Z/p_1^{\alpha_1}\Z)^\times} \cdot ... \cdot \abs{(\Z/p_k^{\alpha_k}\Z)^\times} \\
&= \prod_{i=1}^k \varphi(p_i^{\alpha_i})
\end{align*}
$$

In each ring $p_i^{\alpha_i}\Z$, the non-units are the multiples of $p_i$, since if $x = a p_i^m$, then $p^{\alpha_i - m}x = ap^{\alpha_i} \equiv 0 \bmod p^{\alpha_i}$. Thus every multiple of $p_i$ is a zero divisor, so it is not a unit. There are $p_i^{\alpha_i - 1}$ multiples of $p_i$, so

$$
\varphi(p_i^{\alpha_i}) = p_i^{\alpha_i} \left(1 - \frac{1}{p_i}\right)
$$

So computing it for $n$, we find

$$
\begin{align*}
\varphi(p_i^{\alpha_i}) &= \prod_{i=1}^k \varphi(p_i^{\alpha_i}) \\
&= \prod_{i=1}^k p_i^{\alpha_i} \left(1 - \frac{1}{p_i}\right) \\
&= n \prod_{i=1}^k \left(1 - \frac{1}{p_i}\right)
\end{align*}
$$
