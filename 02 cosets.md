# Cosets

$$
\newcommand{\ds}{\displaystyle}
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\angles}[1]{\left\langle #1 \right\rangle}

\newcommand{\inv}[1]{#1^{-1}}
$$

## Cosets

Suppose $H \leq G$. If $g \in G$, then $xH = \curlies{x \cdot h : h \in H}$ is a **left coset** and the similarly defined $Hx$ is a **right coset**. Cosets are not necessarily groups.

The set of left cosets of $G$ with respect to $H$ is denoted $G / H$, and the right cosets are denoted $H \backslash G$.

### Cosets are disjoint

The different cosets of $H$ in $G$ are disjoint, so if $xH \cap yH \neq \emptyset$ then $xH = yH$.

**Proof.** Suppose  $xH \cap yH \neq \emptyset$. Then there are $a, b \in H$ so that $xa = yb$. Then,

$$
\begin{align*}
x a &= y b \\
x a \inv{a} &= y b \inv{a} \\
x &= y b \inv{a} \\
\end{align*}
$$

and similarly $y = xa\inv{b}$

Suppose $z \in xH$, then $z = xd$ for some $d \in H$, so

$$
\begin{align*}
z &= xd \\
&= yb\inv{a}d \\
&= y(b\inv{a}d) \\
&\in yH \tag{since $b\inv{a}d \in H$}
\end{align*}
$$

Using a similar process, we can show that if $z \in yH$ then it is also in $xH$. Thus, $xH = yH$.

If we choose enough $x_\alpha$ so that every $x_\alpha H$ is disjoint (non-equal), then

$$
G = \bigsqcup_\alpha x_\alpha H
$$

(we can do all of this with right cosets too, though in general everything is different with right cosets, including this decomposition)

### Examples

- if our subgroup is $2\Z < \Z$, the even integers:
  - the cosets are $0 + 2\Z$ aka the even integers and $1 + 2\Z$ aka the odd integers
  - $(0 + 2\Z) \cup (1 + 2\Z) = \Z$.
- if our subgroup is $H = \curlies{e, \rho, \rho^2}$ aka the rotation group of the triangle, then $rH = \curlies{r, r\rho, r\rho^2}$ are the flipped rotations, and clearly $H \cup rH = D_3$

#### Index of a subgroup

If we know $\abs H$ and $\abs G$, then the number of cosets is called the **index** of $H$ in $G$. The index is denoted by $[G : H]$ and is computed by

$$
[G:H] = \frac{\abs G}{\abs H}
$$

The index can also be computed for infinite groups and infinite cosets, e.g. if $G = \Z$ and $H = n\Z$ then $[G:H] = n$.

## Normal subgroups

Left and right cosets of a subgroup $H \leq G$ are not necessarily the same (unless the group is commutative). However, sometimes they are, i.e. $gH = Hg$ for every $g \in G$ - in this case, the subgroup is called **normal**, and we write $H \trianglelefteq G$.

We can alternately write this condition as $gH\inv g = H$. Another sufficient condition for $H$ to be normal is for all $g \in G$, there is a $k \in G$ so that $gH = Hk$.

For example, consider the triangle group $D_3 = \curlies{e, \rho, \rho^2, r, r\rho, r\rho^2}$. Consider the subgroup $H = \angles{\rho} = \curlies{e, \rho, \rho^2}$, the rotations. $rH = Hr$, so $H$ is a normal subgroup.

Normal subgroups are useful because we can use our operation on their cosets nicely, i.e. if we define the operation

$$
xH \cdot yH = \curlies{xhyh': h, h' \in H}
$$

then as long as $H$ is a normal subgroup,

$$
xH \cdot yH = (xy)H
$$



### Quotient groups

If $H \trianglelefteq G$, then $G / H\ (= H \backslash G)$ with the product defined above is a group, called the **quotient group.**

For example, for any $n$, $n\Z \trianglelefteq \Z$, so the quotient $\curlies{n\Z, 1 + n\Z, ..., (n-1) + n\Z}$ is a group.

Recall that since $n\Z$ is normal, the operation on the cosets is the group operation on the elements defining the cosets, so

$$
(a + n\Z) + (b + n\Z) = (a+b) + n\Z
$$

Notice that $x + n\Z = (x+n) + n\Z$ - we recognize this group as the integers with addition mod $n$.

#### Rotations of $\R^3$

Consider the group of rotations of $\R^3$, $SO(3)$. Let $H$ be the rotations around the vertical axis, then any matrix in $H$ can be written as
$$
\begin{pmatrix}
\cos\theta & \sin\theta & 0 \\
-\sin\theta & \cos\theta & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$H$ can be identified with $SO(2)$, so clearly it is a group, so $H < SO(3)$. However, it is not a normal subgroup. We will still consider its set of coset $SO(3) / H$.

If $\mathbf n = (0, 0, 1) \in \R^3$ is the north pole, then for each $\mathbf p \in \mathbb S^2$, here is a matrix $\Omega \in SO(3)$ so that $\Omega \mathbf p = \mathbf n$. Furthermore, a matrix $M \in H$ keeps $\mathbf n$ fixed, so $\Omega M \mathbf p = n$. This holds for every $M \in H$. Thus, we can associate the coset $\Omega H$ with $\mathbf p$. Now we have found a bijection between the cosets of $H$ and $\mathbb S^2$.