# More on groups

$$
\newcommand{\ds}{\displaystyle}
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\angles}[1]{\left\langle #1 \right\rangle}

\newcommand{\inv}[1]{#1^{-1}}
$$

## Maps between groups

### Homomorphisms

A map $\phi : G \to K$ is a **homomorphism** if $\phi(gg') = \phi(g) \phi(g')$.

Note that on the left, $gg'$ is a product in $G$ and $\phi(g)\phi(g')$ is a product in $K$.

Also note that every homomorphism maps $e$ to $e$. Suppose $g \in G$, then $\phi(e) \phi(g) = \phi(eg) = \phi(g) = \phi(ge) = \phi(g) \phi(e)$. So $\phi(e)$ is a left and right identity, so it is the identity of $K$.

If $\phi$ is also a bijection, then $\phi$ is an **isomorphism**.

If there exists an isomorphism between two groups $G$ and $K$, then we say $G$ and $K$ are **isomorphic**.

### Kernel of a homomorphism

The **kernel** of a homomorphism $\phi$ is the set $\ker(\phi) = \curlies{g \in G : \phi(g) = e}$.

#### $ker(\phi)$ is a subgroup

Suppose $g, g' \in \ker(\phi)$. Then $\phi(g) = e = \phi(g')$, so $\phi(gg') = \phi(g)\phi(g') = ee = e$, so $gg' \in \ker(\phi)$. 

Suppose $g \in \ker(\phi)$, then
$$
\begin{align*}
\phi(\inv g) &= e\phi(\inv g) \\
&= \phi(g)\phi(\inv g) \\
&= \phi(g\inv g) \\
&= \phi(e) \\
&= e
\end{align*}
$$
so $\inv g \in \ker(\phi)$.

#### $\ker(\phi)$ is a normal subgroup

[TODO]

## Direct product of two groups

If $G, K$ are groups, their **(direct) product** is
$$
G \times K = \curlies{(g, k) : g \in G, k \in K}
$$
with the group operation
$$
(g_1, k_1) * (g_2, k_2) = (g_1g_2, k_1k_2)
$$
This is a group! Its identity is $e_{G \times K} = (e_G, e_K)$

### $\overline G$ and $\overline K$

In $G \times K$, there are two obvious subgroups:
$$
\begin{align*}
\overline G &= \curlies{(g, e_K) : g \in G} \\
\overline K &= \curlies{(e_G, k) : k \in G}
\end{align*}
$$
Both of these are normal: suppose $(g, k) \in G \times K$, then
$$
\begin{align*}
(g, k) \overline G (g, k)^{-1} &= (g, k) \overline G (\inv g, \inv k) \\
&= \curlies{(g, k) (g', e_K) (\inv g, \inv k) : g' \in G} \\
&= \curlies{(gg'\inv g, k e_K \inv k) : g' \in G} \\
&= \curlies{(gg'\inv g, e): g' \in G} = \overline G
\end{align*}
$$

We can use the same process to show that $\overline K \trianglelefteq G \times K$ as well.

Furthermore, $G \times K / \overline G$ is isomorphic to $\overline K$.

### Projections

The maps $p_G : (g, k) \mapsto g$ and the similarly defined $p_K$ are the **projections** from $G \times K$ to $G$ and $K$ respectively.

These maps are isomorphisms. The kernel of $p_G$ is clearly $\ker(p_G) = \curlies{(e, k): k \in K} = \overline K$. Since kernels are normal subgroups, this is another way to show that $\overline K \trianglelefteq G \times K$.

## Symmetric groups

Suppose $n \in \N$, then the **symmetric group** $S_n$ is the set of permutations of $n$ symbols, usually $\curlies{1, ..., n}$. We know that $\abs{S_n} = n!$

Notice that $D_3$, the symmetry group of the triangle, is equal to $S_3$, the set of permutations of 3 symbols!

### Notation for permutations

We can write **cycles** as $(1\ 2\ 3)$, denoting the permutation taking 1 to 2, 2 to 3, and 3 to 1. A cycle with 2 symbols is called a **transposition**, and in general a cycle with $k$ symbols is called a **$k$-cycle**. A $k$-cycle in $S_n$ has order $k$. Note that $(1\ 2\ 3) = (2\ 3\ 1)$.

We can take products of cycles by applying them sequentially from right to left. For example, if $[1\ 2\ 3\ 4]$ is our list, then
$$
\begin{align*}
(1\ 2\ 3) (3\ 4)[1\ 2\ 3\ 4] &= (1\ 2\ 3)[1\ 2\ 4\ 3] \\
&= [2\ 3\ 4\ 1] \\
&= (1\ 2\ 3\ 4)[1\ 2\ 3\ 4]
\end{align*}
$$
So $(1\ 2\ 3)(3\ 4) = (1\ 2\ 3\ 4)$

Any permutation can be written as a product of disjoint cycles. This product is unique up to rotations (i.e. $(1\ 2\ 3) = (2\ 3\ 1)$) and reorderings (since disjoint cycles commute).
