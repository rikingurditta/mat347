# Rings of Fractions

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

## Construction of the rationals

$\Q$ can be constructed from $\Z$ by taking equivalence classes of pairs of integers:

We can define $\Q$ as
$$
\Q = \curlies{\frac{a}{b} \in \Z^2 : b \neq 0} /\sim \text{ where } (a, b) \sim (c, d) \text{ if } ad = bc
$$

We would like to perform the same construction with any commutative ring $R$ (which doesn't necessarily have $1$).

We do this by choosing a set $D \subseteq R$ to be our denominators - notice that this cannot be all of $R$ because we cannot divide by $0$.

We also want our new ring of fractions to add and multiply like $\Q$. So what we want is:
$$
\frac{a}{b} \cdot \frac{c}{d} = \frac{ac}{bd}
$$
Thus, $D$ must be closed under multiplication, so that if $b, d$ are denominators then so is $bd$. Furthermore, there can be no $0$ divisors in $D$, so that $bd \neq 0$.

With $D$ chosen, we can construct our ring of fractions $Q$ as
$$
Q = R \times D/\sim \text{ where } (a, b) \sim (c, d) \text{ if } ad = bc
$$
Though elements of $R \times D$ are in the form $(r, d)$, we will write them as fractions $r/d$.

We define addition and multiplication as
$$
\begin{align*}
\frac{a}{b} + \frac{c}{d} &= \frac{ad + bc}{bd} \\
\frac{a}{b} \cdot \frac{c}{d} &= \frac{ac}{bd}
\end{align*}
$$
This construction is possible for any commutative ring $R$, not necessarily with $1$. Note that even if $1 \notin R$, there will be a $1 \in Q$, as if $d \in D \subseteq R$ then $1 = d/d \in Q$.

### Existence of a ring of fractions

To summarize the development above in to a single theorem:

If $R$ is a commutative ring (with or without $1$) and $D \subseteq R$ is closed under multiplication and contains no zero divisors, then there exists a ring $Q$ containing $R$ (as a subring) where every element of $D$ is a unit (i.e. for all $d \in D$, $1/d \in Q$.

Moreover,

- $Q = \curlies{a\inv d = a/d : a \in R, d \in D}$
  - if $D = R \setminus \curlies 0$ then $Q$ is a field
- $Q$ is the smallest ring containing $R$ where every element of $D$ is a unit

The proof is long but straightforward.

### Examples

This construction is motivated by the special case where if $R = \Z$ and $D = \Z \setminus \curlies{0}$, then $Q = \Q$.

Note that the same thing happens if $R = 2\Z$ - we can construct

$$
\begin{align*}
Q &= \curlies{\frac{2m}{2n} : m, n \in \Z, n \neq 0} \\
&= \curlies{\frac{m}{n} : m, n \in \Z, n \neq 0} \\
&= \Q
\end{align*}
$$

If $F$ is a field, $R = F[x]$, and $D = R \setminus \curlies{0}$, then $Q = F(x)$, field of rational functions.

Note that we can apply this to create the field of rational functions with integer coefficients starting from $R = \Z[x]$, however this set is the same as the field of rational functions with rational coefficients, i.e. constructing $Q$ starting from $\Q[x]$.

In a commutative ring $R$ with $d \in R$ not a zero divisor, let $D = \curlies{d, d^2, d^3, ...}$. Then we can think of $Q = R[\frac{1}{d}]$, as we would end up with
$$
\ds Q = \curlies{a_n \frac{1}{d^n} + ... + a_1 \frac{1}{d} + a_0 : a_i \in R}
$$
With $R = \Z$ and $p \in \N$ prime, let $D = \curlies{n \in \Z : p \ndivides n}$. Then if $m, n \in D$, then $p \ndivides mn$, so $D$ is closed under multiplication. Then $Q$ is a ring that contains $\Z$ where every prime number $q$ other than $p$ is invertible because $q \in D$. The only ideals in $Q$ are $(p), (p^2), (p^3), ...$ and the only prime one is $(p)$. This construction is useful in number theory, as some statements are easier to prove in $Q$ than in $\Z$.