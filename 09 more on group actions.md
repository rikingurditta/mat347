# More on Group Actions

$$
\newcommand{\ds}{\displaystyle}
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\angles}[1]{\left\langle #1 \right\rangle}
\newcommand{\inv}[1]{#1^{-1}}

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
N \subseteq \bigcup_{x \in G} xH\inv x = \ker(\phi)
$$

Thus $\ker(\phi)$ is the largest normal subgroup of $G$ that is contained in $H$.