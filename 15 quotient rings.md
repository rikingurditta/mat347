# Quotient Rings

$$
\newcommand{\ds}{\displaystyle}
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\angles}[1]{\left\langle #1 \right\rangle}
\newcommand{\inv}[1]{#1^{-1}}
\newcommand{\divides}{ {\large\mid} }
\newcommand{\ndivides}{ {\large\not\mid} }

\newcommand{\Sp}{\mathbb S}
\newcommand{\F}{\mathbb F}
$$

## Quotient Rings

If $I \subseteq R$ is a two-sided ideal, then we can define the **quotient ring** $R/I$.

We start by defining the underlying additive group, which is just the quotient group $(R, +)/(I, +)$ (since $(I, +) \trianglelefteq (R, +)$).

Multiplication is defined as $(r + I)(s + I) = rs + I$. For this to work, we need $rI = I$ for every $r \in R$, which is why we defined ideals the way we did.

Note that if $R$ has an identity, then so does $R/I$, and similarly $R/I$ is commutative if $R$ is.

### Examples

A simple example is $Z/m\Z$.

A more complicated one is a subring of $\Q[x]$, the polynomials over $\Q$. Consider $(x)$, i.e. all multiples of $x$, then

$$
(x) = \curlies{a_n x^n + ...  a_1 x : a_i \in \Q}
$$

Then $\Q{x}/(x) \cong Q$.

Consider the projection $proj : \Q[x] \to \Q[x]/(x)$. This takes a polynomial $f(x) = a_n x^n + ... + a_1 x + a_0$ to $a_0 + I$, i.e. $f(0) + (x)$. Thus, $\ker(proj) = (x)$. Using the first isomorphism theorem, we can conclude that $\Q[x]/(x) \cong \Q$.

Consider $F[x, y]$ where $F$ is a field. Then $F[x, y]/(x) \cong F[y]$.

Consider the evaluation map $E_a : p(x) \to p(a)$ (where $p(x) \in F[x]$ and $a \in F$) which evaluates the polynomial $p$ at $a$. Then $\ker(E_a) = (x - a)$.