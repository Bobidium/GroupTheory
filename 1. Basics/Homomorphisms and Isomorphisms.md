---
aliases:
  - "[[Definition and Elementary Properties of Groups]]"
tags:
  - Theory
---
### Definitions

Homomorphisms and Isomorphism are special **mappings** between groups. Studying these maps allows mathematicians to understand the relationship between groups and how "similar" they are to each other. 

>[!definition] Homomorphism
>Let $G, H$ be two groups. A *Homomorphism* betwen $G$ and $H$ is a map $\varphi: G \to H$ such that for all $x, y \in G$:
>$$
>\varphi(xy) = \varphi(x)\varphi(y)
>$$

>[!warning] Note
>In the above definition, the "multiplication" $xy$ happens in $G$ while the multiplication $\varphi(x)\varphi(y)$ takes place in $H$. 

In its essense, homomorphisms are maps that **preserves the algebraic structure** between two groups. A special type of Homomorphism is called an *Isomorphism*: 

>[!definition] Isomorphism
>An *Isomorphism* between groups $G$ and $H$ is a **bijective** homomorphism between the two groups. If there exists an isomorphism between $G$ and $H$, we say that the two groups are *Isomorphic* and this is denoted as: 
>$$
>G \simeq H
>$$

If two groups are isomorphic, they they are essentially the same group but with **different** labellings for its elements (i.e. which symbols we use for the elements). The following are some examples of Homomorphisms and Isomorphisms:

>[!example] Examples of Homomorphisms and Isomorphisms
>* Consider the set of all rotations for an $n$-gon under the operation of function composition. We can verify that this is indeed a group. In fact, it is a [[Subgroups|subgroup]] of the [[The Dihedral Group|Dihedral Group]] of order $2n$. Consider the map $f: \mathbb{Z}/n\mathbb{Z} \to D_{2n}$ defined by $f([k]) = r^k$. This constitutes a homomorphism because for all $[x], [y] \in \mathbb{Z}/n\mathbb{Z}$:
> $$\begin{align}f([x + y]) &= r^{x+y}\\ &= r^x r^y \\ &= f([x])f([y])\end{align}$$
> * The map $g: (\mathbb{R}, +) \to (\mathbb{R} ^{+}, \times)$ defined by $g(x) = e^x$ is a homomorphism because: $$ \begin{align} g(x+y) &= e^{x+y} \\ &= e^x e^y \\ &= g(x)g(y)\end{align}$$Furthermore, $g$ is an isomorphism as we can find its inverse to be $\ln(x)$. Thus we can say that: $(\mathbb{R}, +) \simeq (\mathbb{R} ^{+}, \times)$. 

As some elementary properties to isomorphisms, we shall prove that a homomorphism (not necessarily an isomorphism) maps an identity to an identity and an inverse to an inverse. 

>[!success] Homomorphisms, Identity and Inverses
>Let $G, H$ be groups and let $f: G \to H$ be a homorphism, then:
>1. $f(e_G) = e_H$, where $e_G, e_h$ denote the identities in $G$ and $H$ respectively.
>2. For all $g \in G$, $f(g^{-1}) = f(g)^{-1}$. 

**Proof**: 
1. As $e_G \cdot e_G = e_g$, we have: $$ \begin{align} f(e_G) &= f(e_G \cdot e_G)\\ &= f(e_G) \cdot f(e_G) \end{align}$$
	Then multiplying both sides by $f(e_G)^{-1}$ will show that $f(e_G) = e_H$. 
2. Since: $$ \begin{align} f(g^{-1}) f(g) &= f(g^{-1}g) \\ &= f(e_G) \\&= e_H  \end{align}$$
	Multiplying $f(g)^{-1}$ on both sides shows that $f(g^{-1}) = f(g)^{-1}$. 

### Application to the Symmetric Group

Using the tools of homomorphisms and isomorphisms, we can prove the following interesting theorem, which shows that the structure of a [[The Symmetric Group#Definitions|Symmetric Group]] $S_{\Omega}$ is only dependend on its **cardinality**:  

>[!success] Classification of the Symmetric Group
>Let $\Omega, \Delta$ be finite sets such that $|\Omega| = |\Delta|$. Then: 
>$$
>S_{\Omega} \simeq S_{\Delta}
>$$

**Proof**: As $|\Omega| = |\Delta|$, there exists a bijection $\theta: \Omega \to \Delta$. Now, we define the map $f: S_{\Omega} \to S_{\Delta}$ as follows: For all $\sigma \in S_{\Omega}$:
$$
f(\sigma) = \theta \circ\sigma \circ \theta^{-1}
$$
Notice that this map is well-defined since $f(\sigma)$ is indeed a permutation of the set $S_{\Delta}$. This can be verified by observing that $\theta \circ\sigma \circ \theta^{-1}$ has the inverse of $\theta \circ \sigma^{-1} \circ \theta^{-1}$. Additionally, $f$ is a bijection as we can defined the inverse map $f^{-1}: S_{\Delta} \to S_{\Omega}$ as:
$$
f^{-1}(\pi) = \theta^{-1} \circ \pi \circ \theta
$$
for all $\pi \in S_{\Delta}$. We can easily verify that this is the two-sided inverse of $f(\sigma)$. Finally, we shall verify that $f(\sigma)$ is indeed a homomorphism. It suffices to show that for any $\sigma_1, \sigma_2 \in S_{\Omega}$ and any $x \in \Omega$: 
$$
f(\sigma_1\sigma_2)(x) = f(\sigma_1)(f(\sigma_2)(x))
$$
This is relatively straightforwards since: 
$$
\begin{align}
f(\sigma_1)(f(\sigma_2)(x)) &= f(\sigma_1)(\theta \sigma_2\theta^{-1}(x)) \\
&= \theta \sigma_1\theta^{-1}((\theta \sigma_2\theta^{-1})(x)) \\
&= (\theta \sigma_1(\theta^{-1}\theta) \sigma_2\theta^{-1})(x) \\
&= (\theta(\sigma_1\sigma_2)\theta^{-1})(x) \\
&= f(\sigma_1\sigma_2)(x)
\end{align}
$$
As a result, we have that $f$ is an isomorphism between $S_{\Omega}$ and $S_{\Delta}$, showing that the two groups are isomorphic. 

>[!important] Corollary
>For a finite set $\Omega$, if $|\Omega| = n$, then $S_{\Omega} \simeq S_n$. 

### Properties of Isomorphic Groups

In this section, we list some properties that are preserved by isomorphisms. These properties allow us to quickly check when two groups are **not** isomorphic. 

>[!success] Isomorphisms preserve Commutativity
>Let $G, H$ be two groups. If $G \simeq H$, then $H$ is abelian if and only if $G$ is abelian. 
>

**Proof**: Let $f: G \to H$ be an isomorphism, then by definition, $f^{-1}: H \to G$ is also an isomorphism. Suppose that $G$ is an abelian group, then for any elements $x, y \in H$, we have:
$$
\begin{align}
f^{-1}(xy) &= f^{-1}(x) f^{-1} (y) \\
&= f^{-1}(y) f^{-1} (x) \\
&= f^{-1}(yx)
\end{align}
$$
As $f^{-1}$ is a bijection, this implies that $xy = yx$, showing that $H$ is an abelian group. The proof in the other direction works analogously. 

>[!success] Isomorphisms preserve Order of Elements
>Let $G, H$ be two groups and let $f$ be an isomorphism between them. For any $g \in G$: 
>$$
>o(g) = o(f(g))
>$$

**Proof**: Let $o(g) = n$, then naturally $g^n = e$ and for any $k < n$, $g^k \neq e$. As $f$ is an isomorphism, we have:
$$
\begin{align}
f(g)^n &= f(g^n) \\
&- f(e) \\
&= e
\end{align}
$$
Now, suppose FTSOC that there exists $k < n$ such that $f(g)^k = e$, then:
$$
\begin{align}
g^k &= f^{-1} (f(g^k)) \\
&= f^{-1} (f(g)^k) \\
&= f^{-1} (e) \\
&= e
\end{align}
$$
which contradicts the minimality of order. Hence, $f(g)^n = e$ and $n$ is the smallest such integer, implying that $o(f(g)) = n$. 

>[!important] Corollary
>If $G$ and $H$ are two isomorphic groups, then they have the same number of elements of order $n$ for all $n \in \mathbb{Z}$. 

**Proof**: Let the set of all elements of order $n$ in $G$ be $S_G$ and let the set of all elements of order $n$ in $H$ be $S_H$. Then by the previous Proposition, the map $f : S_G \to S_H$ defined by $f(g) = \varphi(g)$ where $\varphi$ is an isomorphism between $G$ and $H$ is a bijection. As a result, $|S_G| = |S_H|$.  

We have the following examples that illustrates the use of the above propositions:

>[!example] Proving that Two Groups are Not Isomorphic
>1. $S_3$ and $\mathbb{Z} / 6\mathbb{Z}$ are not isomorphic as $S_3$ is non-abelian but $\mathbb{Z} / 6\mathbb{Z}$ is abelian. 
>2. $(\mathbb{R}, +)$ and $(\mathbb{R} - \{0\},  \times)$ are not isomorphic since the latter has an element of order $2$ (i.e. $-1$), but the former has no element of order $2$. 


