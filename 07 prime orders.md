# Prime Orders

## Prime-ordered elements

Suppose $G$ is abelian, $n = \abs G$, and $p$ is a prime where $p \mid n$. Then $G$ contains an element of order $p$.

**Proof.**

*Base case:*

Suppose $|G| = p$, then $G \cong \Z/p\Z$, so every element has order $p$.

*Inductive step:*

Suppose the theorem holds for all abelian groups $H$ where $\abs H < \abs G$.

Suppose $x \in G$.

Suppose $p$ divides $\abs x$. Then $\abs x = kp$ for some $k \in \N$. This means that $(x^k)^p = x^{kp} = e$. $x^k \neq e$ since $k \leq kp$ and $\abs x = kp$, so this means that $x^k$ has order $p$.

Suppose $p$ does not divide $\abs x = \abs{\angles x}$. Let $N = \angles x$, then $N \triangleleft G$:

- $N \trianglelefteq G$ since $G$ is abelian
- $N \neq G$, since $p \mid \abs G$ but $p \nmid \abs N$

Then since $\abs G$ = $\abs {G/N} \cdot \abs N$, we know that $p \mid \abs{G/N}$. By the induction hypothesis, $G/N$ has an element $c = yN$ of order $p$, so $c^p = e \in G/N$, i.e. $(yN)^p = y^pN = N$. This means that $y^p \in N$. However, $c$ has order $p$, so $c = yN \neq e$, so $y \notin N$. Then $\angles y \neq \angles{y^p} \leq N$. Furthermore, $\angles{y^p} \leq \angles y$, so $\abs y^p < \abs y$.

It is easy to show that for any $g \in G$ and $m \in \N$,
$$
\abs{g^m} = \frac{\abs g}{(\abs g, m)}
$$
We can apply this to find that
$$
\abs{y^p} = \frac{\abs y}{(\abs y, p)} < \abs y
$$
This means that $(\abs y, p) > 1$, so $\abs y = mp$ for some $m$, so $\abs{y^m} = p$.

## Simple groups

A group $G \neq \curlies{e}$ is **simple** if its only normal subgroups are $\curlies e$ and $G$ itself.

### Composition series (Jordan-Hölder series)

Suppose we have a sequence of nested normal subgroups:
$$
\curlies e = G_0 \, \triangleleft \, G_1 \, \triangleleft \, ... \, \triangleleft \, G_{n-1} \, \triangleleft \, G_n = G
$$
and furthermore, each $G_{i+1}/G_i$ is simple.

This sequence is called a **composition series** (or Jordan-Hölder series) for $G$.

Every group has a composition series, and furthermore it can have more than one. For example, considering $\Z_p \times \Z_q$ where $p, q$ are primes,
$$
\curlies{0} \triangleleft \Z_p \times \curlies 0 \triangleleft \Z_p \times \Z_q \\
\curlies{0} \triangleleft \curlies 0 \times \Z_q \triangleleft \Z_p \times \Z_q
$$

### The Hölder Program

1. Classify all simple groups
2. Figure out how to combine them in composition series to make all groups

#### Classification of finite simple groups

If $\mathbb F \neq \mathbb F_2$ is a finite field and
$$
Z = Z(SL_n(\mathbb F)) = \curlies{\lambda I : \lambda \in \mathbb F}
$$
then $SL_n(\mathbb F)/Z$ is simple. This is a family of finite fields.

For a permutation group $S_n$, $A_n < S_n$ is the subgroup of even permutations. For $n \geq 5$, $A_n$ is simple.

The classification was completed in 1980, after 18 infinite families of simple groups and and 26 spare *sporadic* simple groups were classified.

### The Feit-Thompson Theorem

If $G$ is simple and $\abs G$ is odd, then $G = \Z/p\Z$ for a prime $p$.

### Solvable groups

Given a composition series

$$
\curlies e = G_0 \, \triangleleft \, G_1 \, \triangleleft \, ... \, \triangleleft \, G_{n-1} \, \triangleleft \, G_n = G
$$

the quotients $G_{i+1}/G_i$ are called the **composition factors**. A finite group is called **solvable** if all of its composition factors are abelian. (This is independent of the composition series used.) These are useful for Galois theory, where solvable groups correspond solvable polynomials.

#### If $N \triangleleft G$ and both $N$ and $G/N$ are solvable, then $G$ is solvable

If $N$ is solvable, then each quotient $N_{i+1}/N_i$ in its composition series is abelian. Similarly, if $\overline G = G/N$ is solvable, then each quotient $\overline{G_{i+1}}/\overline{G_i}$ in its composition series is abelian. Then we can find a composition series for $G$:
$$
\curlies e = N_0 \, \triangleleft \, ... \, \triangleleft \, N_n = N = G_0 \, \triangleleft \, G_1 \, \triangleleft \, ... \, \triangleleft \, G_{n-1} \, \triangleleft \, G_n = G
$$
By the fourth isomorphism theorem, we know that each $G_i$ corresponds to a subgroup of $\overline{G}$, so we can choose $G_1 \cong \overline{G_1}, ..., G_{n-1} \cong \overline{G_{n-1}}$. Thus the composition series we have found has every quotient abelian, so $G$ is solvable.