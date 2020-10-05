# The First Isomorphism Theorem

$$
\newcommand{\ds}{\displaystyle}
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\angles}[1]{\left\langle #1 \right\rangle}
\newcommand{\inv}[1]{#1^{-1}}

\newcommand{\Sp}{\mathbb S}
$$

## Another weird product thingy of groups [pls rename this section later]

Suppose $H, K \leq G$ are subgroups but not necessarily normal. Define $HK = \curlies{hk : h \in H, k \in K}$.

### Lemma: $HK$ is a subgroup if and only if $HK = KH$

($\Rightarrow$) Suppose $HK \leq G$, we will prove that $HK = KH$.

If $h, h' \in H$ and $k, k' \in K$, then $hk \cdot h'k' \in HK$, so there exist $x \in H$, $y \in K$ so that $hkh'k' = xy$. Then
$$
\begin{align*}
hkh'k' &= x y \\
kh' &= \inv h x y \inv{(k')} \\
kh' &= (\inv h x) (y \inv{(k')})
\end{align*}
$$
so $kh'$ is a product of elements of $H$ and $K$, so $kh' \in HK$. since $k, h'$ were arbitrary, this is true for all $kh' \in KH$, so $KH \subseteq HK$. By symmetry, $HK \subseteq KH$.

($\Leftarrow$) Suppose $HK = KH$, we wll prove that $HK \leq G$.

Suppose $h, h' \in H$ and $k, k' \in K$. Since $HK = KH$, $kh' \in HK$, so let $x \in H$ and $y \in K$ be such that $kh' = xy$.
$$
\begin{align*}
hk \cdot h'k' &= h (kh') k' \\
&= hxyk' \\
&= (hx)(yk) \in HK
\end{align*}
$$
So $HK$ is closed under multiplication. $HK$ is closed under inverses by a similar argument.

### Quotients by $H \cap K$

Note that $\ds HK = \bigcup_{h \in H} hK$, however these cosets are not necessarily disjoint.

Suppose $hK = h'K$, so there exist $k, k' \in K$ so that $hk = h'k'$. Then $\inv h h' = k\inv{(k')} \in K$, so $\inv h h' \in H \cap K$. Then we can conclude that $h, h'$ are in the same coset of $H \cap K$ in $H$.

Thus, the number of cosets of $K$ in $HK$ the same as the number of cosets of $H \cap K$ in $H$, so 
$$
[HK : K] = [H : H \cap K] = \frac{\abs H}{\abs{H \cap L}}
$$
Each coset of $K$ in $HK$ has $\abs K$ elements, so the number of elements in $HK$ is
$$
\abs{HK} = [HK : K] \cdot \abs K = \frac{\abs H \abs K}{\abs{H \cap L}}
$$


// Since $H, K$ are subgroups, so $H \cap K$. We also know that $H \cap K \subseteq HK$, so we can consider the quotient $HK / (H \cap K)$.

## The First Isomorphism Theorem

Suppose $\phi : G \to H$ is a homomorphism, and let $K = \ker(\phi) = \curlies{g \in G : \phi(g) = e}$. Then $K \trianglelefteq G$, and $\phi(G) \cong H/K$ (we know $H/K$ is a group because $K$ is normal).

**Proof.**

Suppose $k \in K$ and $g \in G$. Then,
$$
\phi(gk\inv g) = \phi(g) \phi(k) \phi(\inv g) = \phi(g) e \phi(g)^{-1} = \phi(g) \phi(g)^{-1} = e
$$
so $gK\inv g = K$, so $K$ is normal.

Let $\Phi : G/K \to H$ be defined by $\Phi(gK) = \phi(g)$.

This is not well defined unless $\phi(g) = \phi(g')$ whenever $gK = g'K$, so we will prove that this is the case. If $gK = g'K$, then there exist $k, k' \in K$ so that $gk = g'k'$. Then $g = g'k'\inv k$, so

$$
\begin{align*}
\phi(g) &= \phi(g' k' \inv k) \\
&= \phi(g')\phi(k')\phi(\inv k) \\
&= \phi(g') \tag{since $k, k' \in K = \ker(\phi)$}
\end{align*}
$$
Thus, $\Phi$ is well-defined.

Now we will show that $\Phi$ is a homomorphism.
$$
\begin{align*}
\Phi(gK \cdot g'K) &= \Phi(gg' K) \\
&= \phi(gg') \\
&= \phi(g) \phi(g') \\
&= \phi(gK) \phi(g'K)
\end{align*}
$$
Clearly,  our two function have the same image, i.e. $\Phi(G/K) = \phi(G)$. Showing that $\Phi$ is injective will prove that it is an isomorphism.

Suppose $\Phi(gK) = \Phi(g'K)$, then
$$
\begin{align*}
\Phi(gK) (\Phi(g'K))^{-1} &= e \\
\Phi(gK \cdot (g'K)^{-1}) &= e \\
\Phi(g\inv{(g')} K) &= e \\
\phi(g \inv{(g')}) &= e \\
g\inv{(g')} &\in K \\
g &\in Kg' = g'K \\
gK &= g'K
\end{align*}
$$
