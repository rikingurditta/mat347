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
