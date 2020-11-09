# Even More on Group Actions

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

## Groups acting on their normal subgroups

If $H \leq G$, then $N_G(H)$ acts on $H$ by conjugation. Thus there is a homomorphism

$$
\begin{align*}
\psi : N_G(H) &\to Aut(H) \\
g &\mapsto \text{conjugation by } g
\end{align*}
$$

Then by the first isomorphism theorem, there exists an isomorphism from $N_G(H) / C_G(H)$ to a subgroup of $Aut(H)$.

### Examples of automorphisms

Suppose $G = \Z/p\Z$ where $p$ is prime, then any automorphism of $G$ is determined by what it does to a generator of $G$. Suppose $\phi : G \to G$ is an automorphism, then $\phi(k) = \underset{k \text{ times}}{\phi(1) + ... + \phi(1)}$. $\phi(1)$ can be any other generator, so $Aut(G) \cong (\Z/p\Z)^\times$.

For another example, consider a finite dimensional vector space over a finite field $\F_p = \Z/p\Z$. We can think of the space as $V = \F_p^n$, aka $n$-tuples of elements of $\F_p$. Then $Aut(V)$ are the maps from $V \to V$ that preserve addition, aka $Aut(V) = GL(n, \F_p)$. 

## $p$-groups

Suppose $p$ is a prime. A group $P$ whose order is $p^m$ for some $m$ is called a **$p$-group**.

For example, $\abs{\F_p^n} = p^n$ so it is a $p$-group.

### $p$-Sylow subgroups

Suppose $G$ has order $p^a m$ where $(m, p) = 1$. Then the largest possible $p$-subgroup of $G$, the one with order $p^a$, is called the **$p$-Sylow subgroup**.

For example, $S_3$ has a single 3-Sylow subgroup, $\angles{(1\ 2\ 3)} = \curlies{e, (1\ 2\ 3), (1\ 3\ 2)}$, and three 2-Sylow subgroups, $\angles{(1\ 2)}, \angles{(2\ 3)}, \angles{(3\ 1)}$.

### Sylow's Theorem

Suppose $G$ has order $\abs G = p^a m$ where $p \ndivides m$. Then,

1. There exists a $p$-Sylow subgroup $P$.
2. For a fixed $p$, all $p$-Sylow subgroups are conjugate
3. For a fixed $p$, let $n_p(H)$ be the number of $p$-Sylow subgroups in a group $H$. Then $n_p(G)$ satisfies $n_p \equiv 1 \mod p$. Furthermore, $n_p(P) \divides \abs{N_G(P)}$.

> This is very powerful for classifying groups of a given order.
> \- Joe

