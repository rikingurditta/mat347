# Sylow's Theorem

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

## $p$-groups

Suppose $p$ is a prime. A group $P$ whose order is $p^m$ for some $m$ is called a **$p$-group**.

For example, $\abs{\F_p^n} = p^n$ so it is a $p$-group.

### $p$-Sylow subgroups

Suppose $G$ has order $p^a m$ where $(m, p) = 1$. Then the largest possible $p$-subgroup of $G$, the one with order $p^a$, is called the **$p$-Sylow subgroup**.

For example, $S_3$ has a single 3-Sylow subgroup, $\angles{(1\ 2\ 3)} = \curlies{e, (1\ 2\ 3), (1\ 3\ 2)}$, and three 2-Sylow subgroups, $\angles{(1\ 2)}, \angles{(2\ 3)}, \angles{(3\ 1)}$.

## Sylow's Theorem

Suppose $G$ has order $\abs G = p^a m$ where $p \ndivides m$. Then,

1. There exists a $p$-Sylow subgroup $P$.
2. For a fixed $p$, all $p$-Sylow subgroups are conjugate
3. For a fixed $p$, let $n_p(H)$ be the number of $p$-Sylow subgroups in a group $H$. Then $n_p(G)$ satisfies $n_p \equiv 1 \mod p$. Furthermore, $n_p(P) \divides \abs{G/N_G(P)}$.

> This is very powerful for classifying groups of a given order.
> \- Joe

### Lemma: If $P$ is a Sylow $p$-subgroup of $G$ and $Q$ is a $p$-subgroup, then $Q \cap N_G(P) = Q \cap P$

$P$ is in its own normalizer $N_G(P)$, so we know $Q \cap N_G(P) \supseteq Q \cap P$.

Let $H = Q \cap N_G(P) \subseteq N_G(P)$ . We know from the second isomorphism theorem that $HP$ is a subgroup, and that

$$
\abs{HP} = \frac{\abs P \abs H}{\abs{P \cap H}}
$$

This means that $\abs{HP}$ is a power of $p$. But $P \leq HP$, and we know by assumption that $P$ is the largest $p$-subgroup, so $P = HP$.

### Part 1: For any $G$ where $\abs G = p^a m$, there is a $p$-Sylow subgroup $P$

We will prove this by induction. Suppose the result is true for all groups smaller than $G$.

Suppose $p \divides \abs{Z(G)}$. Then $Z(G)$ is abelian. Then there exists a subgroup $N \leq Z(G)$ with $\abs N = p$. Since $N \leq Z(G)$, we know that $N \trianglelefteq G$.

Consider $\overline G = G/N$. If $\abs  G = p^a m$ and $(p, m) = 1$, then $\abs{\overline G} = p^{a-1}m$, so by the induction hypothesis, there is a subgroup $\overline P \leq \overline G$, with $\abs{\overline P} = p^{a-1}$. Then by the fourth isomorphism theorem, we know that $\overline P \leq \overline G$ corresponds to a subgroup $P \leq G$ which has order $p^a$.

Now we will take care of the other case. Suppose $p \ndivides \abs{Z(G)}$. Recall the class equation:

$$
\abs G = \abs{Z(G)} + \sum_i [G : C_G(g_i)]
$$

Since $p$ does not divide $\abs{Z(G)}$, it also cannot divide every index of conjugacy classes. Without loss of generality, assume that $p \ndivides [G : C_G(g_1)]$. Since $\abs G = p^a m$, and $[G : C_G(g_1)] \divides \abs G$, we know that $[G : C_G(g_1)] \divides m$. Let $H = C_G(g_1)$, then we know that $\abs H [G : H] = \abs G = p^a m$, and that $[G : H] \divides m$, so we can conclude that $p^a \divides \abs H$.

We know that $g_1 \notin Z(G)$, so $H = C_G(g_1) \lneq G$, i.e. $H$ is a proper subgroup of $G$. This means that $H$ is a strictly smaller group than $G$, so we can apply the induction hypothesis to conclude that it has a Sylow $p$-subgroup $P$ of order $\abs P = p^a$. Since $P \leq H$, we know that $P \leq G$, so we have found a Sylow $p$-subgroup of $G$.

### Part 2: All $p$-Sylow subgroups are conjugate

Let $P$ be a Sylow $p$-subgroup of $G$ where $\abs G = p^a m$. Let $\mathcal S = \curlies{P = P_1, P_2, ..., P_s}$ be the set of all Sylow $p$-subgroups of $G$. $G$ acts on $\mathcal S$ by conjugation - this is a valid action, since the conjugate of any $p$-Sylow subgroup is also a $p$-Sylow subgroup. [confirm this pls]

We write $\mathcal S = O_1 \cup ... \cup O_r$ where each $O_j$ is an orbit for this action. Assume that $P_1 \in O_i$. Using the orbit-stabilizer theorem, $Stab_G(P_i) = N_G(P_i)$, so $\abs{O_j} = [G : N_G(P_i)]$ where $P_i \in O_j$.

Suppose $Q$ is a $p$-subgroup of $G$, then $Q$ can also act on $S$. Each orbit $O_i$ can be broken up into orbits that $Q$ induces. If we write $\mathcal S = R_1 \cup ... \cup R_q$ where each $R_j$ is an orbit caused by $Q$. Then,

$$
\abs{R_j} = [Q : N_Q(P_i)] = [Q : P_i \cap Q] \tag{by the lemma}
$$

If $Q$ is not contianed in any $P_i$, then $P_i \cap Q \lneq Q$, so $[Q : P_i \cap Q] > 1$. Since $\abs Q$ is a power of $p$, any subgroup's order is also a power of $p$, so $p \divides [Q : P_i \cap Q]$. This means that every $\abs{R_j}$ is divisible by $p$, so $p \divides \abs{\mathcal S}$.

Apply what was just considered with $P_i$ in place of $Q$. i.e., consider $P_1$ acting on $\mathcal S$

$$
\abs{O_1} = [P_1 : N_{P_1}(P_1)] = [P_1 : P_1] = 1
$$

Now consider this for $P_i \neq P_1$.

$$
\abs{O_j} = [P_1 : N_{P_1}(P_i)]
$$

Suppose $[P_1 : N_{P_1}(P_i)] = 1$, then $P_1 = N_{P_1}(P_i)$. However this means that $N_{P_1}(P_i) \cap P_1 = P_1$, so $P_i \cap P_1 = P_1$. But $P_1$ and $P_i$ have the same order, so this would imply that $P_1 = P_i$, which is a contradiction. Thus, $\abs{O_j} > 1$. From the work above, recall that this implies that $p \divides \abs{O_j}$. Thus, the order of every $O_j$ is a multiple of $p$, except for $O_1$ which has order 1. This implies that

$$
\abs{\mathcal S} = \sum_j \abs{O_j} \equiv 1 \mod p
$$

[...]