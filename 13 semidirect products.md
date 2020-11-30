# Semidirect products

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

## Semidirect products

Recall that if $H, K \triangleleft G$ and $H \cap K = \curlies e$, then $G \cong H \times K$. This characterizes the direct product.

Suppose $H \triangleleft G$, $K < G$, and $H \cap K = \curlies{e}$. Then by the second isomorphism theorem, $HK \leq G$. In this situation, we say $K$ is a complement to $H$, and that $HK$ is the **semidirect product** of $H$ and $K$, written as $G = H \rtimes K$ (with the pointy part of the normal subgroup triangle pointing toward the normal subgroup).

Suppose we have $a, b \in H$ and $x, y \in K$. Then,

$$
\begin{align*}
axby &= axb \inv x x y \\
&= a(xb\inv x)xy \\
&= h \cdot \phi(x)(b) \cdot xy
\end{align*}
$$

Where $\phi : K \to Aut(H)$ so that $\phi(k) = C_k$. If $\phi(k) = id$ for every $x \in K$, then this is a direct product.

We can use this behaviour to define a semidirect product similarly to the direct product for arbitrary groups, as ordered pairs: Suppose $H, K$ are groups and we have a homomorphism $\phi : K \to Aut(H)$. Then we can formally define $H \rtimes K$ to be the set $H \times K$ with the operation $(a, x) \cdot (b, y) = (a \cdot \phi(x)(b), x \cdot y)$. We call this an **outer semidirect product**.

### Example: Rigid motions of $\R^2$

Let $R$ be the set of rigid motions of $\R^2$.

The rotations of $\R^2$ are $SO(2)$, and the rotations correspond to elements of $\R^2$. $\R^2 \triangleleft R$. $R = SO(2) \cdot \R^2$.

Suppose $\omega, \omega' \in SO(2)$ and $x, x' \in \R^2$. Then 

$$
\omega x \omega' x' =  \omega x (\text{rotate by } \omega' \cdot \text{translate by } x') \omega \omega'
$$

