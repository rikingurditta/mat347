# Rings

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

## Rings

A **ring** is a set $R$ with two operations, $+$ and $\times$, which has the following properties:

- $(R, +)$ is an abelian group
  - we denote the identity of $(R, +)$ as $0$
- $\times$ is associative
- $R$ follows the two distributive laws:
  - $a (b + c) = ab + ac$
  - $(a + b) c = ac + ab$

A ring is **commutative** if $\times$ commutes. (We use the word commutative when we describe multiplication commuting and abelian when we discuss addition commuting.) $R$ is a ring **with unit** or **with identity** if there is an element $1 \in R$ so that $x \times 1 = 1 \times x = x$. Some books define a ring to be a ring with identity, some books have even weirder definitions.

### Examples

Some examples of rings are:

- $\Z$ is a commutative ring with unit

- fields are commutative rings with unit where every element element other than $0$ is invertible

- skew-fields are just like fields, except they are not commutative
  
  - the quaternions (real quaternions) are a skew-field - this is the set of 4-tuples $a + bi + cj + dk$ where $a, b, c, d \in \R$ and $1, i, j, k$ multiply just like they do in the quaternion group
  
- many classes of functions on $\R$ are rings with pointwise addition and multiplication:
  - all functions on $\R$
  - $C^k(\R)$, the set of $k$-times differentiable functions
  - $C^\infty(\R)$, the set of smooth functions
  - $C_C(\R)$, the set of continuous functions on $\R$ with compact support (does not have identity)
    - this is also a ring with the multiplication being convolution
  - the similar classes of functions on other spaces are also rings
  
- if $G$ is a finite group and $F$ is a field, we write $F[G]$ for the **group ring** of $G$: the set of all formal linear combinations $\ds \sum_{g_i \in G} c_i g_i$ where $c_i \in F$, $g_i \in G$ where
  $$
  \left(\sum_{g_i \in G} c_i g_i\right)\left(\sum_{g_j \in G} d_j g_j\right) = \sum_{g_i \in G} \sum_{g_j \in G} (c_i d_j) (g_i g_j)
  $$
  - in this case, $F[G]$ is commutative if and only if $G$ is abelian
  - (this is a generalization of the quaternions)
  
- polynomials form rings

  - if $F$ is a field, then $F[x] = \curlies{a_0 + a_1 x + ... + a_k x^k : a_i \in F, k \in \N_0}$, the polynomials over $F$, is a ring
  - if $R$ is a ring, the similarly defined $R[x]$ is a ring
  - note that $F \subseteq F[x]$, $R \subseteq R[x]$
  - $F[x_1, ..., x_n]$ is the set of polynomials over $F$ in $n$ variables
    - usually we assume that the variables commute with each other, i.e. $x_i x_j = x_j x_i$
    - we can have non-commuting polynomials too though

- the set of $n \times n$ matrices over a field $F$ or a ring $R$ form a ring

  - this ring is non-commutative unless $n = 1$
  - note that we cannot guarantee invertibility since invertible matrices are not closed under addition

- if $(A, +)$ is any abelian group, then we can create a ring $R$ by giving $A$ "the stupidest multiplication", so that $x \times y = 0$ for all $x, y \in R$

  > "This multiplication is so stupid that it doesn't tell us anything."
  >
  > \- Joe
  >
  > "We can have groups with pretty pathetic multiplications and they can become rings."
  >
  > \- Joe
  
- the Gaussian integers $Z[i] = \curlies{a + bi : a, b \in \Z} \subseteq \C$, are inside the complex numbers analogously to how the normal integers are inside the real numbers

- the set $\curlies{a + b\sqrt 2 : a, b \in Z} \subseteq \R$, the ring of integers of $\Q(\sqrt 2)$, is analogous to the normal integers inside $\R$

- $\Z/n\Z$ is a commutative ring with identity

  - it is also a field if and only if $n$ is prime
    - one reason is because if $n = jk$, then there are nonzero elements $x$ and $y$ where $xy = 0$, which cannot happen in a field
    - elements of a ring that can multiply to $0$ are called $0$-divisors - for example, every element of $C_C(\R)$ is a zero divisor