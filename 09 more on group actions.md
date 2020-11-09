# More on Group Actions

$$
\newcommand{\ds}{\displaystyle}
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\angles}[1]{\left\langle #1 \right\rangle}
\newcommand{\inv}[1]{#1^{-1}}
\newcommand{\divides}{ {\large\mid} }

\newcommand{\Sp}{\mathbb S}
$$

## Groups acting on their quotients

If $H \leq G$, then $G$ acts on $G/H$ by **left translation**:

$$
g \cdot xH = gxH
$$

If $H = \curlies e$ then trivially, $G/H \cong G$. In this case, the stabilizer, aka the set of elements with trivial action $\curlies{g \in G : g\cdot x = x}$ is $\curlies e$.

For $H \leq G$ in general, the stabilizer $G_H$ of $H$ is $H$ itself: since $hH = H$ for all (and only) $h \in H$,

$$
G_H = \curlies{g \in G : gH = H} = H
$$


## Actions as permutations

Suppose $G$ acts on a finite set $X$. Then there exists a homomorphism $\phi$ between $G$ and $S_X$, the symmetric group of $X$, aka the group of permutations (bijections) on $X$. Note that if $n = \abs X$, then $S_X \cong S_n$.

Suppose $G$ is finite and it is acting on $H$ by left translation, so $\phi : G \to S_{G/H}$. Then

$$
\begin{align*}
\ker(\phi) &= \curlies{g \in G : \phi(g) = id_{G/H}} \\
&= \curlies{g \in G : g \cdot xH = gxH = xH \text{ for all } x \in G} \\
&= \curlies{g : g \in xH\inv x \text{ for all } x \in G} \\
&= \bigcap_{x \in G} xH\inv x
\end{align*}
$$

Consider a normal subgroup of $G$ which is contained in $H$, so $N \trianglelefteq G$ and $N \leq H$. Tthen $xN\inv x = N \leq H$ for all $x \in G$, so $N = xN\inv x \leq xH\inv x$ for every $x$, so

$$
N \subseteq \bigcap_{x \in G} xH\inv x = \ker(\phi)
$$

Thus $\ker(\phi)$ is the largest normal subgroup of $G$ that is contained in $H$.

## Cayley's Theorem

Consider the group action of left translation on a subgroup $H$ as described above. If $H = \curlies e$, then $G/H \cong G$, so we can conflate the action of $G$ on $G/H$ as an action of $G$ on itself.

In this case, if $\phi: G \to S_G$ is a homomorphism from $G$ to its set of permutations, then its kernel $\ker(\phi) \leq H = \curlies e$, so $\ker(\phi) = \curlies e$, so $\phi$ is injective. Thus $\phi$ is an isomorphism from $G$ to a subgroup of $S_G \cong S_n$ where $n = \abs G$.

Thus, every finite group is isomorphic to a subgroup of some $S_n$. This relates the modern axiomatic understanding of groups to the classical study of groups as subgroups of $S_n$.

However, Cayley's theorem does not help us with computations, as its results are generall impractical. For example, $\abs{A_5} = 60$, so Cayley's thoerem tells us that $A_5$ can be embedded in $S_{60}$, which is a ridiculously large and computationally infeasible group.

## Smallest prime subgroups

Suppose $H \leq G$ and $[G : H] = p$ where $p$ is the smallest prime dividing $\abs G$. Then $H \trianglelefteq G$. Note that there may not be such a subgroup!

**Proof.**

Consider the action of $G$ on $G/H$. These actions are equivalent to $S_p$, so consider the homomorphism $\phi: G \to S_p$. Let $K = \ker(\phi)$, then $K \leq H < G$.

Suppose $[H : K] = k$, then $[G : K] = pk$. $\text{im}(\phi) \leq S_p$, and by the first isomorphism theorem $\abs{\text{im}(\phi)} = \abs{G/K}$, so we know $pk = \abs{G/K} \divides \abs{S_p} = p!$. Thus, $k \divides (p - 1)!$.

Either $k = 1$ or $k$ is a product of primes. Consider the latter case. Since $k \divides \abs G$, every prime in the factorization of $k$ divides $G$. However, $p$ is the smallest prime dividing $G$, so $k$ is a product of numbers that are greater or equal to $p$, so $k \geq p$. But if that is the case, then $k$ cannot divide $(p - 1)!$. So $k = 1$.

$k = [H : K] = 1$, so we know that $\abs H = \abs K$, so $H = K$. [...]

## Conjugacy classes

Recall that a group $G$ acts on itself by conjugation, i.e. $g \cdot x = gx\inv g$ is a group action.

The orbit of $x$ under conjugation, $\curlies{gx\inv g : g \in G}$ is called the **conjugacy class** of $x$. The set of conjugacy classes of $x$ partitions $G$.

The stabilizer of $x$ is the set $\curlies{g \in G : gx\inv g = x}$, so in this case the stabilizer is equal to the centralizer $C_G(x)$.

Thus the size of the conjugacy class of $x$ is $\ds \frac{\abs G}{\abs{C_G(x)}}$. [...]

### Example: $(1\ 2\ 3) \in S_3$

Consider $\rho = (1\ 2\ 3) \in S_3$. $e, \rho, \rho^2$ all commute with $\rho$, so they are in the centralizer of $\rho$. However, transpositions do not commute with $\rho$, so they are not in the centralizer. Thus the centralizer has size 3, so the conjugacy class of $\rho$ has size
$$
\frac{\abs G}{\abs{C_G(\rho)}} = \frac{6}{3} = 2
$$

### Example: 5-cycles in $S_5$

For another example, we will work out the size of a centralizer. Consider $s = (1\ 2\ 3\ 4\ 5) \in S_5$. Then since conjugation is the same as relabelling, we know that the conjugacy class of $p$ is the set of all 5-cycles, which has size $4! = 24$. Then we can work out the size of the centralizer:
$$
\begin{align*}
24 &= \frac{\abs G}{\abs{C_G(s)}} \\
&= \frac{120}{\abs{C_G(s)}} \\
\abs{C_G(s)} &= \frac{120}{24} \\
&= 5
\end{align*}
$$
We know that $e, s, s^2, s^3, s^4$ are all in $C_G(s)$, so they must be the entirety of $C_G(s)$.

### The Class Equation

Recall that $G$ is partitioned into conjugacy classes. We can take a representative $g_0 = e, g_1, ..., g_k$ for each one, and we can consider the size of $G$:
$$
\begin{align*}
\abs G &= \sum \abs{\text{conjugacy classes}} \\
&= \sum_i \frac{\abs G}{\abs{C_G(g_i)}}
\end{align*}
$$
Note that $\ds \frac{\abs G}{\abs{C_G(g_i)}} = 1$ when $g_i \in Z_G$. We can use this fact to simplify our equation, by first rewriting our representatives. Suppose $r_1, ..., r_m$ are the representatives that are not in the centre, then
$$
\abs G = \abs{Z_G} + \sum_i \frac{\abs G}{\abs{C_G(r_i)}}
$$
This is the **class equation**.

### If $p$ is a prime and $\abs G = p^n$ where $n \geq 1$, then $G$ has a non-trivial centre

By the class equation,
$$
\begin{align*}
\abs G = \abs{Z_G} + \sum_{i=1}^m \frac{\abs G}{\abs{C_G(g_i)}}
\end{align*}
$$
Since each centralizer $C_G(g_i)$ is a proper subgroup of $G$, its size divides the size of $G$, so $\abs{C_G(g_i)} = p^\ell$ for some $\ell < m$. Thus, $p$ divides the summation. Since $p$ divides $\abs G$, $p$ must divide $\abs{Z_G}$ as well, so $\abs{Z_G} \neq 1$.

### $A_5$ is simple

If $N$ is normal, then it must be a union of conjugacy classes, since for each $x \in N \trianglelefteq G$, we have $gx\inv g \in gN\inv g = N$.

Consider the conjugacy classes of $S_5$, aka the cycle types:

| Cycle type    | Representative    | Even? |
| ------------- | ----------------- | ----- |
| 5             | $(1\ 2\ 3\ 4\ 5)$ | Yes   |
| 4, 1          | $(1\ 2\ 3\ 4)$    | No    |
| 3, 2          | $(1\ 2\ 3)(4\ 5)$ | No    |
| 3, 1, 1       | $(1\ 2\ 3)$       | Yes   |
| 2, 2, 1       | $(1\ 2)(3\ 4)$    | Yes   |
| 2, 1, 1, 1    | $(1\ 2)$          | No    |
| 1, 1, 1, 1, 1 | $e$               | Yes   |

Since $A_5$ is all the even permutations of $S_5$, $A_5$ is made up of permutations of cycle types (5), (3, 1, 1), (2, 1, 1, 1), and (1, 1, 1, 1, 1). However, these are conjugacy classes of $S_5$, but they are not necessarily conjugacy classes in $A_5$.

The conjugacy classes of $A_5$ are:

| Representative    | Size |
| ----------------- | ---- |
| $(1\ 2\ 3\ 4\ 5)$ | 12   |
| $(1\ 3\ 5\ 2\ 4)$ | 12   |
| $(1\ 2\ 3)$       | 20   |
| $(1\ 2)(3\ 4)$    | 15   |
| $e$               | 1    |

Any normal subgroup of $A_5$ would be a union of these conjugacy classes, specifically including $\curlies e$. Then its order would be a sum of the sizes of the conjugacy classes, including 1. Any sum like this would not divide $\abs{A_5} = 60$, so the union could not be a subgroup.