# Group Actions

$$
\newcommand{\ds}{\displaystyle}
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\angles}[1]{\left\langle #1 \right\rangle}
\newcommand{\inv}[1]{#1^{-1}}

\newcommand{\Sp}{\mathbb S}
$$

## Group Actions

A group **acts** on a set $S$ if there exists a map

$$
\begin{align*}
G \times S &\to S \\
(g, s) &\mapsto g \cdot s = gs
\end{align*}
$$

where $(gh)\cdot s = g \cdot(h \cdot s)$ and $e \cdot s = s$.

This is a *left action* because we multiply things on the left, i.e. $g \cdot s$. We can also have a *right action*, which is $(g, s) \mapsto s \cdot \inv g$ (we need to invert $g$ so that the associativity property holds)

### Examples

For example, if $G = SO(3)$ and $S$ is $\Sp^2$, then the action of a rotation $\Omega \in G$ is rotating each point $s \in S$.

If $S$ is some other 3-dimensional object, then we could take some specific subgroup of $SO(3)$ for the rotations of that object.

### Orbits

If $G$ acts on $S$ and $s \in S$, the set 

$$
G \cdot s = \curlies{g \cdot s : g \in G}
$$

is the **orbit** of $s$.

We can also consider $SO(2)$ acting on $\Sp^2$. For example, suppose $\mathbf p \in \Sp^2$ is on the equator, then the set $SO(2) \cdot \mathbf p$ is the orbit of $\mathbf p$, and it is the equator.

### Stability group

If $s \in S$, the stability group of $s$ is $\curlies{g \in G : g \cdot s = s}$.

For example, if $\mathbf n \in \Sp^2$ is the north pole, then $SO(2) \cdot \mathbf n = \curlies{\mathbf n}$ (and this does not hold outside $SO(2)$) so the stability group of $\mathbf n$ is $SO(2)$.

#### Stability group and orbits

If $H$ is the stability group of $S$, then each coset of $H$ corresponds uniquely to an element of the orbit $G \cdot s$ (so $G \cdot s$ "is" the cosets of $H$)

### Groups acting on themselves

If $G$ is a group, we can consider it acting on itself. It can do this the obvious way:

$$
L: (g, h) \mapsto gh
$$

But there are more ways! For example,

$$
R: (g, h) \mapsto h\inv g
$$

We can define $L_g : G \to G$ by $L_g(x) = L(g, x) = gx$ and similarly define $R_g: G \to G$. Notice that these commute!

$$
L_g \cdot R_g = R_g \cdot L_g : x \mapsto g x \inv g
$$

These commute for different fixed actions too, i.e.

$$
L_g \cdot R_h = R_h \cdot L_g : x \mapsto g x \inv h
$$

Then we can come up with conjugation as a group action:

$$
C_g = L_g \cdot R_g = R_g \cdot L_g : x \mapsto g x \inv g
$$

And the set of conjugations $C = \curlies{C_g : g \in G}$.

### Conjugacy classes

Then for each $x \in G$, the orbit of $C$ is

$$
C \cdot x = \curlies{C_g(x) = g x \inv g}
$$

The set of all orbits $\curlies{C \cdot x : x \in G}$ is the set of **conjugacy classes** of $G$.

### Cyclic group parity

Suppose $\sigma \in S_n$, then it can be written as a composition of transpositions (2-cycles). If $\sigma$ is written as a composition of $k$ transpositions, then the **parity** of $\sigma$ is whether $k$ is even or odd.