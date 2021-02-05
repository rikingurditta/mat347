# Euclidean Domains and Principal Ideal Domains

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

## Norms

Let $R$ be an integral domain, i.e. a commutative ring with $1$ that has no zero divisors.

A **norm** is a function $N: R \to \N_0 (= \N \cup \curlies{0})$ where $N(0) = 0$. A **positive norm** is one where $N(a) > 0$ whenever $a \neq 0$.

## Euclidean domains

An integral domain $R$ is a **Euclidean domain** if there exists a norm $N: R \to \N_0$ so that for all $a, b \in R$ where $b \neq 0$, there exist $q, r \in R$ (*quotient*, *remainder*) so that

$$
a = qb + r
$$

where either $r = 0$ or $N(r) < N(b)$.

There may be multiple norms that make $R$ a Euclidean domain!

### Euclidean algorithm

The existence of such a norm allows for Thea *Euclidean algorithm*: for any $a, b$, we can do successive "divisions" until the remainder is 0.

$$
\begin{align*}
a &= q_0 b + r_0 \\
b &= q_1 r_0 + r_1 \\
r_0 &= q_2 r_1 + r_2 \\
&... \\
r_{n-2} &= q_n r_{n-1} + r_n \\
r_{n-1} &= q_{n+1} r_n + 0
\end{align*}
$$

This is possible because the norms of the remainders $N(r_0), N(r_1), ...$ are strictly decreasing natural numbers, so eventually they must reach $N(r_n) = 0$. At this point, there is no $r_{n+1}$ so that $N(r_{n+1}) < 0$, so the last remainder is 0.

### Examples

The classic example is the Euclidean algorithm on the integers.

Another simple example is fields - since every element $b \neq 0$ has an inverse, we can always write

$$
a = (a\inv b)b + 0
$$

so the Euclidean algorithm ends on the first step.

For any field $F$, $F[x]$ is a Euclidean domain with the norm $N(f(x)) = \deg(f(x))$. Then the division algorithm relies on polynomial long division.

### Gaussian integers are a Euclidean domain

Recall that the Gaussian integers $\Z[i]$ are the analog to the the integers in $\C$:

$$
\Z[i] = \curlies{a + bi : a, b \in \Z}
$$

With the norm $N(a + bi) = a^2 + b^2$, they are a Euclidean domain:

Given $a, b \in \Z[i]$ with $b \neq 0$, we can divide $\ds \frac{a}{b} = s + ti \in \C$ but we do not know if the result is in $\Z[i]$, but we do know that $s, t \in \Q$:

$$
\begin{align*}
\inv b &= \frac{1}{b} \\
&= \frac{1 \overline b}{b \overline b} \\
&= \frac{u - vi}{u^2 + v^2} \\
&= \frac{u}{u^2 + v^2} - \frac{v}{u^2 + v^2}i \\
&\in \Q[i] \\
\text{so } a\inv b &\in \Q
\end{align*}
$$

Then, we can *round* $s$ and $t$ to the nearest integers, i.e. we can find $p, q$ so that $\abs{p - s} \leq 1/2$ and $\abs{q - t} \leq 1/2$.

Then

$$
\frac{a}{b} = s + it = p + iq + ((s - p) + (t - q)i)
$$

and $p + iq \in \Z[i]$.

Then, multiplying both sides by $b$, we find

$$
a = (p + iq)b + b((s - p) + (t - q)i)
$$

$a$ is a Gaussian integer and so is $(p + iq)b$, so $r = b((s - p) + (t - q)i)$ must also be a Gaussian integer.

Recall that for complex numbers, $f(x) = x\overline x$ is a multiplicative function (i.e. $f(xy) = f(x)f(y)$) and it has the same formula $N(x)$. Then, manipulating complex numbers and recalling that $\abs{p - s} \leq 1/2$ and $\abs{q - t} \leq 1/2$, we see:

$$
\begin{align*}
N(r) &= f(b((s - p) + (t - q)i)) \\
&= f(b) f((s - p) + (t - q)i) \\
&= N(b) f((s - p) + (t - q)i) \\
&= N(b) ((s - p)^2 + (t - q)^2) \\
&= N(b) (\abs{s - p}^2 + \abs{t - q}^2) \\
&\leq N(b) \left(\frac{1}{4} + \frac{1}{4}\right) \\
&= \frac{N(b)}{2} \\
&< N(b)
\end{align*}
$$

> "Is everybody stunned by the sheer beauty of this, or is everybody confused as hell?"
> 
> \- Joe

Thus, we have proved that $\Z[i]$ is a Euclidean domain, as we have shown that

$$
a = (p + iq)b + r
$$

with either $r = 0$ or $N(r) < N(b)$.

## Principal Ideal Domains

A **principal ideal domain** (PID) is an integral domain where every ideal is principal.

A familiar example is $\Z$, where every ideal is in the form $n\Z$. (The simple proof of this uses the fact that every ideal is an additive subgroup, and every subgroup of $\Z$ is some $n\Z$.)

### Every Euclidean domain is a PID

Let $R$ be a Euclidean domain and let $I \neq \curlies{0}$ be an ideal of $R$. By the well-ordering theorem for $\Z$, there must be an element $d \in I$ with minimum norm, then $(d) \subseteq I$. If $a \in I$, then with the Euclidean algorithm we can find $r$ such that $a = qd + r$ with either $r = 0$ or $N(r) < N(d)$, so $r = a - qd$. Since $I$ is closed under subtraction and $a, qd \in I$, $r$ must be in $I$. However, $d$ has minimum norm, so $r$ cannot have norm less than $d$, so $r$ must be $0$. Thus, $0 = a - qd$, so $a = qd$ i.e. $a \in (d)$. This holds for every $a \in I$, so $I \subseteq (d)$, so $I = (d)$.

Note that not every PID is a Euclidean domain! For example,

$$
\Z\left[\frac{1 + \sqrt{-19}}{2}\right]
$$

is a PID but is not Euclidean.

#### $\Z[\sqrt{-5}]$ is not a Euclidean domain

The contrapositive of the statement above says that if a ring is not a PID, then it is not a Euclidean domain. This is the strategy we will use in our proof.

Suppose the ideal $(3, 2 + \sqrt{-5}) \subseteq \Z[\sqrt{-5}]$ were a principal ideal, i.e. $(3, 2 + \sqrt{-5}) = (a + b\sqrt{-5})$. Then

$$
3 = \alpha \cdot (a + b\sqrt{-5}) \text{ and } 2 + \sqrt{-5} = \beta \cdot (a + b\sqrt{-5})
$$

Define the function

$$
\begin{align*}
N(u + v\sqrt{-5}) &= (u + v\sqrt{-5})(u - v\sqrt{-5}) \\
&= u^2 + 5b^2
\end{align*}
$$

Then $N$ is multiplicative, i.e. $N(xy) = N(x)N(y)$.

Applying this to our first equation,

$$
\begin{align*}
N(3) &= N(\alpha) N(a + b\sqrt{-5}) \\
9 &= N(\alpha) (a^2 + 5b^2) \\
\end{align*}
$$

both $N(\alpha)$ and $a^2 + 5b^2$ are positive integers, so either one of them is $1$ and the other is $9$, or both are $3$.

Suppose both are $3$, then $a^2 + 5b^2 = 3$. $5b^2 > 3$ for any nonzero $b$, so $b = 0$. But $3$ is not a perfect square, so $a^2 \neq 3$, so we've reached a contradiction.

Suppose $N(\alpha) = 9$, then $a^2 + 5b^2 = 1$, so by similar logic to above, $a = 1 \in (3, 2 + \sqrt{-5})$, so

$$
\begin{align*}
a = 1 &= 3x + (2 + \sqrt{-5})y \\
2 - \sqrt{-5} &= 3x(2 - \sqrt{-5}) + 4y + 5y \\
2 - \sqrt{-5} &= 3x(2 - \sqrt{-5} + 3y) \\
\end{align*}
$$

So $2 - \sqrt{-5}$ is a multiple of $3$ in $\Z[i]$. However, this is clearly not the case, so we've reached another contradiction.

Suppose $N(\alpha) = 1$, then $\alpha = \pm 1$, so $3 = \pm (a + b\sqrt{-5})$, so $2 + \sqrt{-5} = \pm 3\beta$. However, this is again clearly not the case, so we have reached another contradiction.

All paths lead to contradiction, so $\Z[\sqrt{-5}]$ cannot be a PID, and therefore cannot be a Euclidean domain.

### In a PID, a prime ideal must be maximal

Let $R$ be a PID. Suppose $(p)$ is a prime ideal but it is not maximal, i.e. there exists $m$ so that $(p) \subsetneq (m) \neq R$.

$p \in (m)$, so $p = xm$ for some $x \in R$. Thus $xm \in (p)$, which is a prime ideal, so one of $m$ and $x$ must be in $(p)$.

If $m \in (p)$ then $(m) \subseteq (p)$, which goes against our assumption.

If $x \in (p)$, then $x = yp$ for some $y$. Then $p = xm = xyp$, so $p(1 - xy) = 0$, so $xy = 1$. Thus $x$ is a unit within $(p)$, and any ideal containing a unit is the whole ring, so $(p) = R$. This is another contradiction.

Thus, $(p)$ must be maximal.

#### Corollary: If $R$ is an integral domain and $R[x]$ is a PID, then $R$ is a field

Consider the evaluation map $\phi: R[x] \to R$ which sets $x$ to $0$. Then $\ker(\phi) = (x)$, which is a prime ideal. Since $R[x]$ is a PID, it is also a maximal ideal, so $R[x]/(x) \cong R$ is a field.