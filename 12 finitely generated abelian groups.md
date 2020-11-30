# Finitely generated abelian groups

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

## Simple groups

### Simplicity of $A_n$ for $n \geq 5$

For now, assume that it is known that the alternating groups $A_n$ where $n \geq 5$ are all simple. This will be proved later.

## Fundamental theorem of finitely generated abelian groups

A finitely generated group $G$ is isomorphic to
$$
\Z^r \times \Z_{n_1} \times ... \times \Z_{n_k} \text{ where } r \in \N \text{ and } n_{i+1} \divides n_i, 1 \leq i \leq k-1
$$
$r$ is called the **rank** (or Betti number) of $G$, and each $\Z_{n_i}$ is called an **invariant factor**.

If $G$ is finite, then $\abs G = p_1^{a_1} \cdot ... \cdot p_k^{a_k}$, where each $p_i$ is a prime. 

It is also true that $G \cong P_1 \times ... \times P_k$, where $\abs{P_i} = p_i^{a_i}$. Clearly, $P_i$ is a Sylow $p_i$-subgroup of $G$, and $P_i \cong \Z_{p_i}^{d_1} \times ... \times Z_{p_i}^{d_\ell}$ where $d_1 + ... + d_\ell = a_i$. This is called the **primary decomposition** of $G$, unique up to order.