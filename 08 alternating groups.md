# Alternating Groups

$$
\newcommand{\ds}{\displaystyle}
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\angles}[1]{\left\langle #1 \right\rangle}
\newcommand{\inv}[1]{#1^{-1}}

\newcommand{\Sp}{\mathbb S}
$$

## Alternating groups

Recall that for a fixed $n$, we can define the Vandermonde determinant

$$
\phi(x_1, ..., x_n) = \prod_{j > i} (x_j - x_i)
$$

For a permutation $\sigma \in S_n$, we can define

$$
\sigma \cdot \phi(x_1, ..., x_n) = \phi(x_{\sigma(1)}, ..., x_{\sigma(n)}) = \epsilon(\sigma) \phi(x_1, ..., x_n)
$$

where $\epsilon(\sigma) = \pm 1$ is the parity of sigma, i.e. whether it is an even or odd permutation.

Suppose $\sigma, \tau \in S_n$, with decompositions into $m$ and $n$ transpositions, respectively. Then

$$
\epsilon(\sigma \tau) = (-1)^{m + n} = (-1)^m (-1)^n = \epsilon(\sigma) \epsilon(\tau)
$$

so $\epsilon$ is a homomorphism.

We define the alternating group $A_n = \ker(\epsilon)$.

