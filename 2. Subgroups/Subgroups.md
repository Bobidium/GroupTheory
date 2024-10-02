---
aliases:
  - "[[Definition and Elementary Properties of Groups]]"
tags:
  - Theory
---
### Definition and Examples

In short, subgroups are groups within groups. 

>[!definition] Subgroups
>Let $G$ be a group and $H$ be a subset of $G$. We say that $H$ is a *subgroup* of $H$ if and only if $H$ is closed under multiplication and taking inverses. This is denoted as $H \leq G$.
>

>[!warning] Note
>It is redundant to say that a subgroup contains the identity in the definition as for $x \in H$, $e = xx^{-1} \in H$  follows from the two conditions immediately. 

Studying the subgroups of a group and their relationships allows us to understand the **structure** of the group better. Another approach we can take to study the structure of groups is via [[Quotient Groups]]. 

>[!example] Examples of Subgroups
>1. For any group $G$, $\{e\}$ and $G$ are both subgroups of $G$. These are the *trivial subgroups* of $G$. 
>2. The set of all rotations $\{r, r^2, ..., r^{n-1}\}$ in $D_{2n}$ ([[The Dihedral Group]]) forms a subgroup as it is closed under mutiplication (composition) and taking inverses (inverse of a rotation is still a rotation). 
>3. The set of all even numbers is a subgroup of $(\mathbb{Z}, +)$ as the sum of two even numbers is still even, and the negative of an even number is still even. In contrary, the set of all odd numbers is NOT a subgroup of $(\mathbb{Z}, +)$ as it does not contain $0$, the additive identity. 

>[!warning] Remark
>For $H$ to be a subgroup of $G$, $H$ must **inherit** the operation in $G$. If the operation in $H$ is different from the operation in $G$, even though $H$ may still be a group on its own, it is not regarded as a subgroup of $G$. 

For the above reason, we have the following non-examples of subgroups: 

>[!example] Non-Example of Subgroups
>$\mathbb{Q} - \{0\}$ under multiplication is not a subgroup of $(\mathbb{R}, +)$ despite the fact that it is indeed a subset of $\mathbb{R}$. 

### Properties of Subgroups

We shall be deriving some useful propositions about subgroups in this section. Let us begin with a criteria for subgroups which is simpler than the criteria as stated in the definition: 

>[!success] Criteria for Subgroups
>Let $G$ be a group and $H \subseteq G$ be non-empty. Then $H$ is a subgroup if and only if for all $x, y \in H$: 
>$$
>xy^{-1} \in H
>$$

**Proof**: The forward direction is trivial: if $H$ is a subgroup, then it is closed under inverses and multiplcation, so naturally $xy^{-1} \in H$. Now suppose we have that for all $x, y \in H$, $xy^{-1} \in H$. As $H$ is non-empty, there exists at least one element $x \in H$, from which we can deduce that $xx^{-1} = e \in H$. Then, for any $x \in H$, $ex^{-1} = x^{-1} \in H$, so $H$ is closed under inverses. To prove that $H$ is closed under multiplication in $G$, notice that for all $y \in H$, $(y^{-1})^{-1} = y$. We thus have that for all $x, y \in H$, 
$$
xy = x(y^{-1})^{-1} \in H
$$
which prove the closure under multiplication. As a result, $H \leq G$. 

Next, we investigate the ways in which two subgroups can produce another subgroup: 

>[!success] Intersection of Subgroups
>If $K$ and $H$ are subgroups of a group $G$, then $H \cap K$ is also a subgroup of $G$. 

**Proof**: For any $y \in H \cap K$, we must have that $y^{-1} \in H$ and $y^{-1} \in K$, so $y^{-1} \in H \cap K$.  Consequently, for any $x \in H \cap K$, $xy^{-1} \in H$ and $xy^{-1} \in K$, so $xy^{-1} \in H \cap K$. By the previous proposition, this shows that $H \cap K \leq G$. 

>[!success] Union of Subgroups
>Let $K, H$ be subgroups of a group $G$, then $K \cup H \leq G$ if and only if $H \subseteq K$ or $K \subseteq H$. 

**Proof**: The "if" direction is trivial so we only prove the "only if" direction. If $H \not \subseteq K$ and $K \not \subseteq H$, then there exists $h \in H$ such that $h \not \in K$ and likewise, there exists $k \in K$ such that $k \not \in H$. Now suppose FTSOC that $H \cup K \leq G$, then by the closure under multiplcaiton, $hk \in H \cup K$. Consequently, $hk\in H$ or $hk \in K$. If $hk = k' \in K$, then $h  = k'k^{-1} \in K$, which is a contradiction. Similarly, if $hk = h' \in H$, then $k = h^{-1}h' \in H$, which is also a contradiction. Thus, we must have that $H \subseteq K$ or $K \subseteq H$ if $K \cup H \leq G$, completing the proof for the proposition. 

To end this note, here is an interesting problem about subgroups: 

>[!example] A Subgroup of $\mathbb{Q}$
>Let $H$ be a subgroup of $(\mathbb{Q}, +)$ with the additional property that for all $x \in H$, $x^{-1} \in H$ ($x^{-1}$ is the multiplicative inverse of $x$). Then, $H  = \{0\}$ or $\mathbb{Q}$. 

**Proof**: First we introduce some notations. For any $p/q \in (\mathbb{Q}, +)$, let $n(p/q)$ denote the result when $p/q$ is added to itself $n$ times ($n \in \mathbb{N}$). Clearly, this is the same as the rational number $(np)/q$ so we shall not distinguish between the two throughout the proof. First, suppose that $H$ is non-trivial, then $H$ contains some non-zero element $p/q$. We shall prove that we can get all elements in $\mathbb{Q}$ by applying the conditions on $H$. Firstly,  notice that: 
$$
(nq)\frac{p}{q} = np \in H
$$
so all multiples of $p$ must be in the subgroup. As $(p/q)^{-1} = q/p \in H$, a similar argument shows that all multiples of $q$ are in $H$. Now, as we assumed $p$ and $q$ to be coprime, by Bezout's Lemma, there exists $x, y \in \mathbb{Z}$ such that:
$$
xp + yq = 1
$$
which implies that for all $k \in \mathbb{Z}$: 
$$
k = (kx)p + (ky)q
$$
Since $(kx)p$ is a multiple of $p$ and $(ky)q$ is a multiple of $q$, both of which are in $H$, we have that $k \in H$ by closure under addition. Thus, we have so far shown that $\mathbb{Z} \subseteq H$. Consequently, for all $k \in \mathbb{Z}$, $k^{-1} \in H$ by the definition of $H$ and hence for all $p/q \in \mathbb{Q}$: 
$$
\frac{p}{q} = p\frac{1}{q} = pq^{-1} \in H
$$
which shows that $\mathbb{Q} \subseteq H$. Since $H \subseteq \mathbb{Q}$ by definition, we have that $H = \mathbb{Q}$, which completes the proof. 