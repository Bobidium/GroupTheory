---
aliases:
  - "[[Definition and Elementary Properties of Groups]]"
  - "[[The Symmetric Group]]"
---
### Definition

The concept of Group Action is important in depicting the relationship between Groups and Symmetries. Intuitively, the idea of a group action on a set is a sort of transformation on the set that preserves the group structure itself (similar to a homomorphism): 

>[!definition] Group Action
>A *group action* of a group $G$ on a set $A$ is a map from $G \times A \to A$ written as $g\cdot a$ that satisfies: 
>1. $e \cdot a = a$ for all $a \in A$. 
>2. $g_1 \cdot (g_2 \cdot a) = (g_1g_2) \cdot a$ for any $g_1, g_2 \in G$ and all $a \in A$. 

>[!warning] Note
>The first condition means that acting $g_1$ on $a$ first, then acting $g_2$ is the same as acting the product $g_1g_2$ on $a$. This is essentially saying that the action **respects** the group structure. 

### Essence of Group Actions

To understand Group Actions at a deeper level, we need a more detailed investigation of how an arbitrary group action changes the elements in the set it acts on. The following two propositions reveals the essence of group actions: 

>[!success] Group Actions as Permutations
>Suppose Group $G$ acts on Set $A$. Fix an element $g\in G$. Define $\sigma_g: A \to A$ by $\sigma_g(a) = g \cdot a$ (i.e. the result when $g$ acts on $a$) Then $\sigma_g$ is a permutation of set $A$. 
>

**Proof**: We prove that $\sigma_g$ is a permutation by finding its inverse. consider $\sigma_{g^{-1}}(a) = g^{-1} \cdot a$, then obviously this is the inverse of $\sigma_g$ since for all $a \in A$:
$$
\begin{align}
\sigma_{g^{-1}} (\sigma_g(a)) &= \sigma_{g^{-1}} (g \cdot a) \\
&= g^{-1}\cdot (g \cdot a ) \\
&= (g^{-1}g) \cdot a \\
&= e \cdot a \\
&= a
\end{align}
$$
and the same result holds if we commute $\sigma_g$ and $\sigma_{g^{-1}}$. Thus, $\sigma_g$ is invertible and is hence a permutation of set $A$. 

>[!success] Group Actions Define a Homomorphism
>Let $\sigma_g$ be defined as in the previous proposition, then the map $f: G \to S_{A}$ defined by $f(g) = \sigma_g$ is a [[Homomorphisms and Isomorphisms|homomorphism]]. 

**Proof**: To prove that $f$ is a homomorphism, we need to show that for any $g_2, g_2 \in G$, $f(g_1g_2) = f(g_1)f(g_2)$ and equivalently that for all $a \in A$, $f(g_1g_2)(a) = f(g_1)f(g_2)(a)$. This is relatively easy to see as: 
$$
\begin{align}
f(g_1g_2)(a) &= \sigma_{g_1g_2}(a) \\
&= (g_1g_2) \cdot (a)\\
&= g_1 \cdot (g_2 \cdot a) \\
&= g_1 \cdot (\sigma_{g_1}(a)) \\
&= \sigma_{g_2} (\sigma_{g_1}(a)) \\
&= f(g_1)f(g_2) (a)
\end{align}
$$
Hence, $f$ is a homomorphism and we are done. 

In particular, we call this homomorphism a *permutation representation* of the Group Action and we have the following definition: 

>[!definition] Faithful Group Actions
>A Group Action is called *faithful* if and only if its permutation representation is injective. 

The two propositions above provide us with a better picture of a group action: If a group $G$ acts on a set $A$, then each element of $g$ acts on $A$ by permuting all elements of $A$ in a way that respects the group operation. Not only can Group actions induce homomorphisms from $G$ to $S_A$, the converse is also true: any homomorphism from $G$ to $S_A$, call it $f(g)$ can in fact induce a group action defined by: 
$$
g\cdot a = f(g)(a)
$$
Therefore, it can be said that **the set of all group actions is in bijective correspondence with the set of all homomorphisms from $G$ to $S_A$**.

More strcuture that are associated with Group Actions is introduced in the Note "[[Centralizers, Normalizers, Stabilizers and Kernels]]". 

### Examples of Group Actions

In this section, we introduce some important examples of Group Actions. We start with the simplest one: 

>[!example] The Trivial Action
>Given a group $G$ and a set $A$, the group action defined by $g \cdot a  = a$ for all $a \in A$ is a group action since:
>1. $1 \cdot a = a$
>2. $g_1\cdot (g_2 \cdot a) = g_1 \cdot a = a = (g_1g_2) \cdot a$ for any $g_1, g_2 \in G$.
>
>This action is called the *trivial action* and it is clearly faithful. 

To see why group actions depict the relationship between symmetries and groups, look at the following geometric example of group actions: 

>[!example] The [[The Dihedral Group|Dihedral Group]] Acting on an $n$-gon
>By definition, the each element $\alpha \in D_{2n}$ represents a permutation $\sigma_{\alpha}$ of the vertices of an $n$-gon, numbered from $\{1, 2, ..., n\}$. Define a group action of $D_{2n}$ on $\{1, 2, ..., n\}$ by $\alpha \cdot i = \sigma_{\alpha} (i)$ for all $i \in \{1, 2, ..., n\}$. Then this constitues a group action using the trivial properties of function composition. This group action is also faithful, as distinct elements in $D_{2n}$ represents distinct permutations of the vertices. Notice that when $n = 3$, the permutation representation of this group action (being injective already) is an isomorphism between $D_{2n}$ and $S_3$ as $|D_{2n}| = 6 = |S_3|$ (so it is necessarily surjective). This is a simple proof of the fact:
>$$
>D_{6} \simeq S_3
>$$

>[!warning] Note
>When $n > 3$, $D_{2n}$ cannot be isomorphic to $S_n$ because their orders don't match. 

Next, we introduce yet another important group action called *Conjugation*

>[!example] Conjugation
>Let a group $G$ **act on itself** by the action defined by $g \cdot a = gag^{-1}$ for all $a \in G$. This is a group action because: 
>1. $e \cdot a = e a e^{-1} = a$ for all $a \in G$. 
>2. For any $g_1, g_2, a \in G$, we have: $$ \begin{align} g_1\cdot (g_2\cdot a) &= g_1 \cdot (g_2ag_2^{-1}) \\ &= (g_1g_2) a (g_2^{-1} g_1^{-1}) \\ &= (g_1g_2) a (g_1 g_2)^{-1} \\ &= (g_1g_2) \cdot a  \end{align}  $$
>Moreover, the conjugation map that maps $x \in G$ to $gxg^{-1}$ for some fixed $g \in G$ is an isomorphism from $G$ onto itself. Let this map be $f$. then $f$ is clearly a homomorphism since for any $x_1, x_2 \in G$:
>$$
>f(x_1x_2) = gx_1x_2g^{-1} = gx_1(g^{-1}g)x_2g^{-1} = (gx_1g^{-1})(gx_2g^{-1}) = f(x_1)f(x_2)
>$$
>$f$ is also a bijection as the map that takes $x$ to $g^{-1}xg$ is a two-sided inverse of $f$. As a result, $f$ is an isomorphism from $G$ to itself, which also means that it is an *Automorphism*. 

It is also useful to look at a counterexample of a group action: 

>[!example] NOT a Group Action
>Let $G$ be a non-abelian Group and let $G$ act on itself by an action defined by $g \cdot a = ag$ for all $g, a \in G$ is NOT a Group Action. This is because:
>$$
>\begin{align}
>g_1\cdot (g_2 \cdot a) &= g_1 \cdot (ag_2)\\
>&= a(g_2g_1) \\
>&\neq a(g_1g_2) \\
>&= (g_1g_2) \cdot a
>\end{align}
>$$
>which violates the second condition in the definition for a Group Action. 










