# Unique Factorization Domains

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

## Irreducible, prime, associate elements

### Irreducible elements

Let $R$ be an integral domain. An element $r \in R$ is **irreducible** if it is not a unit, and if $r = ab$ then either $a$ or $b$ is a unit.

### Prime elements

An element $r \in R$ is **prime** if $(r)$ is a prime ideal.

Translating this into the language of divisibility, this means that if $r \divides ab$ then either $r \divides a$ or $r \divides b$.

Note that irreducible and prime are equivalent in $\Z$ and $F[x]$ for any field $F$, but prime is more natural language for numbers and irreducible is more natural language for polynomials.

#### Primes are irreducible in integral domains

Let $R$ be an integral domain. Suppose $p \in R$ is a prime and $p = ab$. Then $ab \in (p)$, which is a prime ideal, so either $a \in (p)$ or $b \in (p)$. Without loss of generality, assume $a \in (p)$, so $a = tp$ for some $t \in R$. Then

$$
\begin{align*}
p &= ab \\
p &= tpb \\
p - tbp &= 0 \\
p(1 - tb) &= 0
\end{align*}
$$


Since $R$ is an integral domain, there are no zero divisors, so we have $1 - tb = 0$ i.e. $1 = tb$, so $b$ is a unit.

#### Irreducible elements are not always prime

Consider $3 \in \Z[\sqrt{-5}]$, this is an irreducible element. However, $2 + \sqrt{-5}, 2 - \sqrt{-5} \notin (3)$, but $(2 + \sqrt{-5})(2 - \sqrt{-5}) = 9 \in (3)$. This means that $(3)$ is not a prime ideal, so $3$ is not prime in $\Z[\sqrt{-5}]$.

#### Prime is equivalent to reducible in a PID

Let $R$ be a PID.

($\Rightarrow$) Suppose $p$ is prime, then since $R$ is a PID, it is also an integral domain, so $p$ is irreducible.

($\Leftarrow$) Suppose $q$ is irreducible and $M$ is an ideal containing $(q)$. Since we are in a principal ideal domain, $M = (m)$ for some $m \in R$. $(q) \subseteq (m)$, so $q = tm$ for some $t$. Since $q$ is irreducible, either $m$ is a unit or $t$ is a unit. If $m$ is a unit, then $(m) = R$. If $t$ is a unit, then $(m) = (tp) = (p)$. Thus, there are no proper ideals containing $(p)$, so $(p)$ is maximal, which means that it is prime.

### Associate elements

$a, b \in R$ are **associate** if there exists a unit $u \in R$ so that $a = ub$.

## Unique Factorization Domains

A **unique factorization domain** is an integral domain $R$ where every nonzero $r \in R$ which is not a unit can be factored uniquely as

$$
r = u p_1^{\alpha_1} \cdot ... \cdot p_n^{\alpha_n}
$$

where $u$ is a unit and each $p_i$ is irreducible. Note that the uniqueness is up to multiplication of each $p_i$ by a unit, i.e. up to associate $p_i$'s.

For example, consider $R = \Z[2i]$. This is an integral domain but not a UFD. This is because both $2$ and $2i$ are irreducible but not associate, so $4 = 2^2 = -(2i)^2$ has two distinct decompositions.

### Prime is equivalent to irreducible in a UFD

Let $R$ be a UFD.

($\Rightarrow$) Suppose $p$ is prime, then since $R$ is a PID, it is also an integral domain, so $p$ is irreducible.

($\Leftarrow$) Suppose $q$ is irreducible and suppose $p \divides ab$. Then $ab = pc$ for some $c$. Suppose $a = u p_1^{\alpha_1} \cdot ... \cdot p_m^{\alpha_n}$ and $b = v q_1^{\beta} \cdot ... \cdot q_n^{\beta_n}$, then $p \divides ab$, so $p$ must be associate to one of the factors of either $a$ or $b$, i.e. $p = p_i$ or $p = q_i$. So either $p \divides a$ or $p \divides b$, so $p$ is prime.

### Greatest common divisors are obvious in a UFD

Suppose $a = u p_1^{e_1} \cdot ... \cdot p_n^{e_n}$ and $b = v p_1^{f_1} \cdot ... \cdot p_n^{f_n}$, where $e_i, f_i \geq 0$ (so $e_i$ or $f_i$ is $0$ if $p_i$ isn't a factor). Then

$$
\gcd(a, b) = \prod_{i=1}^n p_i^{\min(e_i, f_i)}
$$

### PIDs are UFDs

Suppose $R$ is a principal ideal domain and $r \in R$ is neither zero nor a unit.

Suppose $r$ is reducible, then $r = r_1 \cdot r_2$. If both are irreducible, then we are done.

Suppose they are not both reducible, then $(r) \subsetneq (r_1)$ (since $r_2 \notin (r))$. If we continue factoring this way, we get a strictly growing chain of ideals $I_1 \subsetneq I_2 \subsetneq I_3 \subsetneq ...$. Taking their union,

$$
I = \bigcup_{i=1}^\infty I_i
$$

It is not hard to show that $I$ is an ideal, and since $R$ is a PID $I$ must be a principal ideal $(a)$.

However, if $a \in I$, then there exists some $i$ so that $a \in I_i$. But then $(a) \subseteq I_i$, so $I \subseteq I_i$. However, this contradicts our earlier statement that the chain of ideals $I_1 \subsetneq I_2 \subsetneq ...$ is strictly growing, as it must stop growing at $I_i$. Therefore, we can eventually factor $r$ into irreducible elements.

To show uniqueness, we use induction:

Let $n$ be the number of irreducible elements that $r$ factors into, i.e. $r = u p_1, ..., p_n$.

If $n = 1$ then $r = up_1$, so if $r = vq$ then $p$ and $q$ must be associate.

Suppose the statement holds for $n$ factors, and suppose $r$ decomposes into $n+1$ factors in two ways, $r = up_1 \cdot ... \cdot p_{n+1}$ and $r = vq_1 \cdot ... \cdot q_{n+1}$. Then $q_1$ divides $r$, so it must divide $up_1 \cdot ... \cdot p_{n+1}$, so $q_1$ must be associate to one of the $p_i$'s. Assume without loss of generality that $q_1 = w p_1$ where $w$ is a unit, then

$$
(u/w) q_1 p_2 \cdot ... \cdot p_{n+1} = v q_1 \cdot ... \cdot q_{n+1}
$$

so cancelling $q_1$ on both sides,

$$
(u/w) p_2 \cdot ... \cdot p_{n+1} = v q_2 ... \cdot q_{n+1}
$$

By the inductive hypothesis, these irreducibles must all be associate, so $r$ can be uniquely factored.

## Primes in $\Z[i]$

Recall that $\Z[i]$ is a Euclidean domain with its usual norm

$$
N(a + bi) = (a + bi)(a - bi) = a^2 + b^2
$$

so it is a PID and a UFD.

Also recall that this norm is multiplicative, i.e. if $x, y \in \Z[i]$, then $N(xy) = N(x)N(y)$.

### Lemma: $N(\gamma) = 1$ if and only if $\gamma$ is a unit

($\Rightarrow$) Suppose $\gamma \in \Z[i]$ and $N(\gamma) = 1$, then $\gamma \overline \gamma = 1$, so $\gamma$ is a unit.

($\Leftarrow$) Suppose $\gamma$ is a unit, then there is some $\delta$ so that $\gamma \delta = 1$. Then $N(\gamma \delta) = N(\gamma) N(\delta) = 1$, and $N(\gamma) \in \Z^{\geq 0}$, so $N(\gamma) = 1$.

### Elements with prime norms

Suppose $\alpha \in \Z[i]$ is such that $p = N(\alpha)$ is prime.

If $\alpha = \beta \gamma$, then $p = N(\alpha) = N(\beta) N(\gamma)$. Since $p$ is prime, this means that either $N(\beta) = p$ or $N(\gamma) = p$ and the other norm is $1$. Suppose without loss of generality that $N(\beta) = p$, then $N(\gamma) = 1$, so by the lemma, $\gamma$ is a unit. Thus, whenever we factorize $\alpha$ one of the factors is a unit, so $\alpha$ is irreducible and therefore prime.

### Prime ideals in $\Z[i]$ and in $\Z$

Suppose $\pi \in \Z[i]$ is prime, i.e. $(\pi)$ is a prime ideal. Then $(\pi) \cap \Z$ is an ideal in $\Z$. Suppose $a, b \in \Z$ and $ab \in (\pi) \cap \Z \subseteq (\pi)$. Then either $a$ or $b$ is in $(\pi)$. Without loss of generality assume $a \in (\pi)$, then $a \in (\pi) \cap \Z$. Thus, $(\pi) \cap \Z$ is a prime ideal.

Recall that $\Z$ is a PID, so there is some prime $p \in \Z$ so that $(\pi) \cap \Z = (p)$.

### Factorizations of integer primes in $\Z[i]$

Suppose an integer prime $p$ is in $(\pi)$ ($\pi$ is a prime in $\Z[i]$), we know that there is some $x \in \Z[i]$ so that $p = \pi x$. Then $N(\pi) N(x) = N(p) = p^2$.

This means that either $N(\pi) = 1$, $N(\pi) = p$, or $N(\pi) = p^2$. However, $\pi$ is a prime so it is not a unit, so $N(\pi) \neq 1$.

Considering the other two cases,

- If $N(\pi) = p^2$ then $N(x) = 1$ so $x$ is a unit. The only units in $\Z[i]$ are $\pm 1, \pm i$, so $\pi = \pm p$ or $\pi = \pm ip$.
- If $N(\pi) = p$, then we also have $N(x) = p$. By the previous theorem, this means that $\pi$ and $x$ are both irreducible, so $p$ has exactly two irreducible divisors in $\Z[i]$. This further implies that $p$ is a sum of two squares, since if $\pi = a + bi$ then $N(\pi) = a^2 + b^2 = p$.

## Primes that are the sum of two squares

For which primes $p$ can we find integers $a, b$ so that $p = a^2 + b^2$?

We know a few examples:

- $2 = 1^2 + 1^2$
- $3 \neq a^2 + b^2$ for any $a, b$
- $5 = 2^2 + 1^2$
- $7 \neq a^2 + b^2$ for any $a, b$
- $11 \neq a^2 + b^2$ for any $a, b$
- $13 = 3^2 + 2^2$

Notice that in the Gaussian integers, if $p = a^2 + b^2$, then $p = (a + bi)(a - bi)$. Then

$$
\begin{align*}
p^2 &= N(p) \\
&= N(a + bi) N(a - bi) \\
&= N(a + bi)^2 \tag{since $N(x) = N(\overline x)$}
\end{align*}
$$

so $p = N(a + bi) = N(a - bi)$, so by a previous theorem, both of these are irreducible.

### Squares in $\Z/4\Z$

Consider the squares of numbers mod $4$:

- if $x \equiv 0 \bmod 4$ then $x^2 \equiv 0 \bmod 4$
- if $x \equiv 1 \bmod 4$ then $x^2 \equiv 1^2 \equiv 1 \bmod 4$
- if $x \equiv 2 \bmod 4$ then $x^2 \equiv 2^2 \equiv 0 \bmod 4$
- if $x \equiv 3 \bmod 4$ then $x^2 \equiv 3^2 \equiv 1 \bmod 4$

So for any $x \in \Z$, $x \equiv 0 \text{ or } 1 \bmod 4$. This means that for any sum of squares $x^2 + y^2 \equiv 0 \text{ or } 1 \text{ or } 2 \bmod 4$. This helps us rule out some primes. For example, $11 \equiv 3 \bmod 4$, so there are no $x, y$ so that $x^2 + y^2 \equiv 11 \bmod 4$, so $x^2 + y^2 \neq 11$.

### Lemma: If $m$ has order 2 in $(\Z/p\Z)^\times$ then $m \equiv -1 \bmod p$

Suppose $m$ has order 2 in $(\Z/p\Z)^\times$, then $m^2 = 1 \bmod p$.

Then $p \divides m^2 - 1 = (m - 1)(m + 1)$. Since $\Z/p\Z$ has no zero divisors, this means that either $m - 1 \equiv 0 \bmod p$ or $m + 1 \equiv 0 \bmod p$, so either $m \equiv 1 \bmod p$ or $m \equiv -1 \bmod p$. However, 1 does not have order 2, so $m \equiv -1 \bmod p$.

As a corollary, suppose there is a subgroup of order 4 in $(\Z/p\Z)^\times$. This subgroup cannot be isomorphic to the Klein 4-group ($a^2 = b^2 = c^2 = 1$, $ab = c$, $bc = a$, $ca = b$) because then there would be three distinct elements with order 2, which is impossible since the only element of order 2 is $-1$.

### A prime $p$ divides $n^2 + 1$ for some $n$ if and only if $p = 2$ or $p \equiv 1 \bmod 4$

Suppose $p = 2$, then $p \divides 1^2 + 1$.

Suppose $p \divides n^2 + 1$. This is equivalent to $n^2 \equiv -1 \bmod p$. If this is the case then $n$ has order 4 in $(\Z/p\Z)^\times$, which means that there is a subgroup of order 4 of $(\Z/p\Z)^\times$. This in turn means that $4 \divides \abs{(\Z/p\Z)^\times} = p - 1$, so $p \equiv 1 \bmod 4$.

Suppose instead that $p \equiv 1 \bmod 4$, so $4 \divides p - 1 = \abs{(\Z/p\Z)^\times}$. Then, $H = \curlies{1, -1} \leq (\Z/p\Z)^\times$, and it is normal because this is an abelian group. So we can consider the quotient group $(\Z/p\Z)^\times / H$. This quotient group has order $\abs{(\Z/p\Z)^\times} / 2 = (p - 1) / 2$, so we know that 2 divides the order of the quotient group.

We know that $(\Z/p\Z)^\times / H$ has a subgroup of order 2 because

[...]

This means that $(\Z/p\Z)^\times$ has a subgroup $S$ of order 4. Using the corollary to the lemma above, we know that $S$ is not the Klein 4-group, so $S$ must be cyclic, aka $S = \angles{n}$ for some $n \in (\Z/p\Z)^\times$. Then $n$ has order 4, so $n^2$ has order 2, so $n^2 \equiv -1 \bmod p$, so $p \divides n^2 + 1$.

### Primes $p$ that are $p \equiv 1 \bmod 4$ are sums of squares

Suppose $p \equiv 1 \bmod 4$, then by the previous theorem there is some $n$ so that $p \divides n^2 + 1 = (n - i)(n + i)$.

If $x \in \Z[i]$ and $p \divides x$, then $p \divides \overline x$. Suppose $p$ is irreducible, then either $p \divides (n - i)$ or $p \divides (n + i)$. However, in either case, $p$ also divides the conjugate, so $p$ must divide both. Thus, $p$ divides their difference, so $p \divides ((n + i) - (n - i))$, so $p \divides 2i$. Since $p$ is real, this means that either $p = 1$ or $p = 2$. However, 1 is not a prime and $2 \not \equiv 1 \bmod 4$, so neither of these work. Thus, $p$ cannot be irreducible. Using our previous work on factorizing integer primes in $\Z[i]$, we know that there must be a factor $\pi \in \Z[i]$ of $p$ so that $N(\pi) = p$, i.e. if $\pi = a + bi$ then $p = N(\pi) = a^2 + b^2$.

Also note that if $p$ is a prime other than 2, then $p$ is odd so $p \equiv 1 \text{ or } 3 \bmod 4$. Every sum of squares is $a^2 + b^2 \equiv 0 \text{ or } 1 \text{ or } 2 \bmod 4$, so if $p$ is a sum of squares then $p \equiv 1 \bmod 4$.

### Classification of primes in $\Z[i]$

The work above shows us that the prime ideals of $\Z[i]$ are

- $(1 + i)$ and $(1 - i)$, since both of them have a norm of 2
- $(p)$ for some prime $p \in \Z$ where $p \equiv 3 \bmod 4$, so $p$ cannot be written as a sum of squares
- $(a + bi)$ and $(a - bi)$ where $a^2 + b^2 = p$ for some prime in $\Z$ (and $p \equiv 1 \bmod 4$)

