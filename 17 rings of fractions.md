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

## Construction of the rational numbers

$\Q$ can be constructed from $\Z$ by taking equivalence classes of pairs of integers:

We can define $\Q$ as
$$
\Q = \curlies{\frac{a}{b} \in \Z^2 : b \neq 0} /\sim \text{ where } (a, b) \sim (c, d) \text{ if } ad = bc
$$

## [...]

### Examples

Clearly, if $R = \Z$ and $D = \Z \setminus \curlies{0}$, then $Q = \Q$.

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

In a commutative ring $R$ with $d \in R$ not a zero divisor, let $D = \curlies{d, d^2, d^3, ...}$. Then we can think of $Q = R[\frac{1}{d}]$, as we would end up with $Q = \curlies{a_n \frac{1}{d^n} + ... + a_1 \frac{1}{d} + a_0 : a_i \in R}$.

With $R = \Z$ and $p \in \N$ prime, let $D = \curlies{n \in \Z : p \ndivides n}$. Then if $m, n \in D$, then $p \ndivides mn$, so $D$ is closed under multiplication. Then $Q$ is a ring that contains $\Z$ where every prime number $q$ other than $p$ is invertible because $q \in D$. The only ideals in $Q$ are $(p), (p^2), (p^3), ...$ and the only prime one is $(p)$. This construction is useful in number theory, as some statements are easier to prove in $Q$ than in $\Z$.