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

## Unique Factorization Domains

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

#### In a PID, prime is equivalent to reducible

Let $R$ be a PID.

($\Rightarrow$) Suppose $p$ is prime, then since $R$ is a PID, it is also an integral domain, so $p$ is irreducible.

($\Leftarrow$) Suppose $q$ is irreducible and $M$ is an ideal containing $(q)$. Since we are in a principal ideal domain, $M = (m)$ for some $m \in R$. $(q) \subseteq (m)$, so $q = tm$ for some $t$. Since $q$ is irreducible, either $m$ is a unit or $t$ is a unit. If $m$ is a unit, then $(m) = R$. If $t$ is a unit, then $(m) = (tp) = (p)$. Thus, there are no proper ideals containing $(p)$, so $(p)$ is maximal, which means that it is prime.

### Associate elements

$a, b \in R$ are **associate** if there exists a unit $u \in R$ so that $a = ub$.