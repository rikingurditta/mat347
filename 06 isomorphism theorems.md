# The Isomorphism Theorems

$$
\newcommand{\ds}{\displaystyle}
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\angles}[1]{\left\langle #1 \right\rangle}
\newcommand{\inv}[1]{#1^{-1}}

\newcommand{\Sp}{\mathbb S}
$$

## $AB$ for groups $A$ and $B$

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
So $HK$ is closed under multiplication.

Suppose $h \in H$ and $k \in K$, then $hk \in HK$. Then, taking its inverse, $(hk)^{-1} = \inv k \inv h \in KH = HK$, so $HK$ is closed under inverses.

Thus, $HK$ is a subgroup.

### Quotients by $H \cap K$

Note that $\ds HK = \bigcup_{h \in H} hK$, however these cosets are not necessarily disjoint.

Suppose $hK = h'K$, so there exist $k, k' \in K$ so that $hk = h'k'$. Then $\inv h h' = k\inv{(k')} \in K$, so $\inv h h' \in H \cap K$. Then we can conclude that $h, h'$ are in the same coset of $H \cap K$ in $H$.

Thus, the number of cosets of $K$ in $HK$ the same as the number of cosets of $H \cap K$ in $H$, so 
$$
[HK : K] = [H : H \cap K] = \frac{\abs H}{\abs{H \cap K}}
$$
Each coset of $K$ in $HK$ has $\abs K$ elements, so the number of elements in $HK$ is
$$
\abs{HK} = [HK : K] \cdot \abs K = \frac{\abs H \abs K}{\abs{H \cap K}}
$$


// Since $H, K$ are subgroups, so $H \cap K$. We also know that $H \cap K \subseteq HK$, so we can consider the quotient $HK / (H \cap K)$.

## The First Isomorphism Theorem

Suppose $\phi : G \to H$ is a homomorphism, and let $K = \ker(\phi) = \curlies{g \in G : \phi(g) = e}$. Then $K \trianglelefteq G$, and $\phi(G) \cong G/K$ (we know $G/K$ is a group because $K$ is normal).

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

Thus, $\Phi$ is injective, so it is a bijection on its image which is $\phi(G)$. As a result, it is an isomorphism.

### Applications

Let $N$ be a normal subgroup of $G$, then the homomorphism $\phi : G \to G/N$ defined by $\phi(g) = gN$ is called the **natural projection map** for $N$.

Similarly, in a direct product $G_1 \times G_2$, then the homomorphism $\phi(g_1, g_2) = g_2$ is also called a **projection**, and $(G_1 \times G_2)/(G_1 \times \curlies{e})$ is normal.

If we consider the map
$$
\begin{align*}
\phi : \R &\to \Sp^1 \\
t &\mapsto e^{2\pi i t}
\end{align*}
$$
then its kernel is $\ker(\phi) = \Z$, so $\R/\Z \cong \Sp^1$.

## The Second Isomorphism Theorem

### Normalizers

We define the **normalizer** of a subgroup $H$ as $N_G(H) = \curlies{g \in G : gH\inv g = H}$. Notice that $H$ is normal if and only if $N_G(H) = G$.

### The theorem

Suppose $A, B \leq G$ and $A \leq N_G(B)$. Then,

- $AB \leq G$
- $B \trianglelefteq AB$
- $A \cap B \trianglelefteq A$
- $AB/B \cong A/(A \cap B)$

This is expressed in the following lattice diagram:

![image-20201005163327895](/Users/rikin/Documents/School Stuff/2020-2021/mat347/mat347-notes/second isomorphism theorem lattice diagram.png)

This theorem is often referred to as the *diamond theorem* because of the shape of this lattice diagram.

**Proof.**

To show that $AB \leq G$, it suffices to show that $AB = BA$. Suppose $a \in A$, $b \in B$, then since $A \leq N_G(B)$, $ab\inv a = b' \in B$.
$$
\begin{align*}
ab &= (ab\inv a) a \\
&= b' a \in BA
\end{align*}
$$
so $AB \subseteq BA$. We can similarly show that $BA \subseteq AB$, so $AB = BA$, so $AB \leq G$.

Now we will prove that $A \cap B \trianglelefteq A$. Suppose $x \in A \cap B$ and $a \in A$. Since $x \in A$, $ax\inv a \in A$. Since $x \in B$ and $A \leq N_G(B)$, $ax\inv a \in B$. Thus, $ax\inv a \in A \cap B$, so $A \cap B \trianglelefteq A$.

Now we will prove that $AB / B \cong A / (A \cap B)$. We define
$$
\begin{align*}
\phi : AB &\to A/(A \cap B) \\
ab &\mapsto a(A \cap B)
\end{align*}
$$
Suppose $ab = a'b'$, then $\inv{(a')} a = b' \inv b$. The left is in $A$ and the right is in $B$ but they are equal, so both sides are in $A \cap B$. $a = a'b'\inv b$, so $a(A \cap B) = a'b'\inv b = a'(A \cap B)$. Thus, $\phi$ is well-defined. Now we will show that it is a homomorphism:
$$
\begin{align*}
\phi(aba'b') &= \phi(aa'\inv{(a')} b a' b') \\
&= \phi(aa'(\inv{(a')} b a') b') \\
&= \phi(aa'\beta b') \tag{since $A \leq N_G(B)$} \\
&= aa'(A \cap B) \tag{since $\phi(ab) = a(A \cap B)$} \\
&= (a(A \cap B))(a' (A \cap B)) \\
&= \phi(ab) \phi(a'b')
\end{align*}
$$
Thus, $\phi$ is a homomorphism.

Its kernel is

## The Third Isomorphism Theorem

Suppose $N \trianglelefteq G$, $K \trianglelefteq G$, and $N \trianglelefteq K$. Then $K/N \trianglelefteq G/N$ and
$$
(G/N)/(K/N) \cong G/K
$$
We will prove this using the first isomorphism theorem, by creating a map $\phi : G/K \to (G/N)/(N/K)$.

We define $\phi$ by
$$
\phi(gK) = gN(K/N)
$$
To show that $\phi$ is well-defined, suppose $gK = g'K$. Then $g = g'k$ for some $k \in K$. Then
$$
\begin{align*}
gN(K/N) &= g'k N(K/N) \\
&= g'Nk(K/N) \tag{$N \trianglelefteq K$ so $kN = Nk$} \\
&= g'N(k(K/N)) \\
&= g'N(K/N)
\end{align*}
$$
So $\phi(gK) = \phi(g'K)$ whenever $gK = g'K$.

Now we want to find $\ker(\phi)$, so we want to find when $\phi(gK) = e = K/N$.

So $\phi(gK) = gN(K/N) = K/N$, so we want $gN \subseteq K/N$, so $gN \subseteq \curlies{kN : k \in K}$, so $g \in K$. Thus, $\phi(gK) = e$ if $g \in K$, so
$$
\ker(\phi) = \curlies{kK : k \in K} = K/K = \curlies e
$$
Thus, $\phi$ is an isomorphism, so we have found an isomorphism between $G/K$ and $(G/N)/(K/N)$.

