---
aliases:
  - "[[Homomorphisms and Isomorphisms]]"
  - "[[Definition and Elementary Properties of Groups]]"
---
### Kernel and Fibers

The study of Quotient Groups originates in the study of [[Homomorphisms and Isomorphisms|Homomorphisms]], so we begin by defining the *Kernel* and *Image* of a Homomorphism. 

>[!d] Kernel of a Homomorphism
>Let $G$ and $H$ be groups and let $\varphi: G \to H$ be a group homomorphism. The *Kernel* of $\varphi$, denoted by $\text{Ker}(\varphi)$ is the set: 
>$$
>\text{Ker}(\varphi) = \{ g \in G : \varphi(g) = e_{H} \}
>$$
>where $e_H$ denotes the identity element of $H$. 

>[!d] Image of a Homomorphism
>Let $G$ and $H$ be groups and let $\varphi: G \to H$ be a group homomorphism. The *Image* of $\varphi$, denoted by $\text{Im}(\varphi)$ is the set: 
>$$
>\text{Im}(\varphi) = \{ h \in H : \exists \; g \in G \text{ such that } \varphi(g) = h \}
>$$

Diagramically, Kernels and Images can be represented as follows: 

![[Image_Kernel.jpg | center| 500]]

It is easy to see that both the kernel and Image of a homomorphism are [[Subgroups|subgroups]]:

>[!success] Images and Kernels are Subgroups
>For any homomorphism $\varphi: G \to H$, $\text{Ker}(\varphi) \leq G$ and $\text{Im}(\varphi) \leq H$. 
>

**Proof**: Trivial. 

We shall start by investigating the elements that gets mapped to the same element $h \in H$ in a homomorphism. If we fix $h \in H$, then all such elements form a set called the *fiber* above $h$. 

>[!d] Fiber
>Let $\varphi : G \to H$ be a homomorphism. For any $h \in H$, the *fiber above $h$*, denoted by $\varphi^{-1}(h)$ is the set: 
>$$
>\varphi^{-1}(h) = \{ g \in G : \varphi(g) = h \}
>$$

Two elements of $G$ belong to the same fiber if and only if they get mapped to the same element in $H$. Notice that if we define an equivalence relation $g_1 \sim g_2$ in $G$ to be $g_1 \sim g_2 \iff \varphi(g_1) = \varphi(g_2)$, then the equivalence classes are exactly the distinct fibers of $\varphi$, so naturally, the fibers form a natural **partition** of our group $G$. The rest of this subsection is the investigate the structure of this set of distinct fibers that partition $G$. Diagramically, fibers can be represented as: 

![[Pasted image 20241001141911.png|center|400]]

(Diagram from Dummit & Foote, *Abstract Algebra*)

The most classical example to illustrate fibers is the follows: 

>[!example] $\mathbb{Z} / n\mathbb{Z}$ as Fibers
>Consider the homomorphism $f: \mathbb{Z} \to Z_n = \langle x \rangle$ defined by $f(k) = x^k$ (Recall that $Z_n$ is the [[Cyclic Groups|Cyclic Group]] of order $n$). This is a homomorphism as:
>$$
>f(k_1+k_2) = x^{k_1+k_2} = x^{k_1}x^{k_2} = f(k_1)f(k_2) 
>$$
>As $x^k = e$ if and only if $n \mid k$, the kernel of $f$ consists exactly of the multiples of $n$, this is simply the set $n\mathbb{Z}$. For any $x^a \in Z_n$, the fiber above $x^a$ is 
>$$
>\varphi^{-1}(x^a) = \{k \in \mathbb{Z}: x^k = x^a\} = \{ k \in \mathbb{Z} : n \mid k-a \} = \{ a+ dn : d \in \mathbb{Z}\} = a+ n\mathbb{Z}
>$$
>Hence, the fiber above $x^a$ is simply a **translation** of the set $n\mathbb{Z}$ by $a$, as indicated above. If we use $\mathbb{Z} / n\mathbb{Z}$ to denote the set of all fibers under this homomorphism, we have:
>$$
>\mathbb{Z} / n\mathbb{Z} = \{a+ n\mathbb{Z} : a \in \mathbb{Z}, \; 0 \leq a \leq n-1 \}
>$$
>which is precisely the modulo group of order $n$ in number theory. 

We can adopt the same notation as in the above example and give "the set of fibers" a new notation: 

>[!d] Quotient "Set"
>Let $\varphi:G \to H$ be a group homomorphism with Kernel $K$. We use the symbol $G / K$ to denote the set of all distinct fibers induced by $\varphi$. 

With this example as a motivation, we can ask whether the ideas above can be extended to all group homomorphisms? i.e. Can the fibers of a homomorphism always be treated as "translations" of the Kernel of the homomorphism? The answer is yes, as shown in the following proposition: 

>[!success] Fibers as "Translations" of the Kernel
>Let $\varphi: G \to H$ be a group homomorphism with kernel $K$, and let $X \in G / K$ be the fiber above $a \in H$. Then: 
>1. For any $u \in X$, $X = \{uk : k \in K\}$. 
>2. For any $u \in X$, $X = \{ ku : k \in K\}$. 

**Proof**: We shall only prove the case where $u$ is multiplied on the left. Let $uK = \{uk : k \in K\}$. Notice that for all $uk \in uK$, we have:
$$
\varphi(uk) = \varphi(u)\varphi(k) = \varphi(u)e = \varphi(u)
$$
As $u \in K = \varphi^{-1}(a)$, we have $\varphi(uk) = a$, so naturally $uk \in X$, which prove the inclusion $uK \subseteq X$. for the opposite inclusion, observe that for all $x \in X$, $x = u(u^{-1}x)$ and furthermore, we have that:
$$
\begin{align}
\varphi(u^{-1}x) &= \varphi(u^{-1})\varphi(x)\\
&= \varphi(u)^{-1}\varphi(x) \\
&= a^{-1}a \\
&= e
\end{align}
$$
Hence, $u^{-1}x \in K$, which implies that $x = uk$ for some $k \in K$, which completes the proof for the inclusion $X \subseteq uK$. 

We can establish the following notation to represent fibers: 

>[!d] Coset Notation for Fibers
>For a group homomorphism $\varphi: G \to H$, if $X = \varphi^{-1}(h)$ for $h \in H$, we use the symbol $uK$ for $X$, where $u$ is any element in $X$. 

---
Knowing that the set $G/\text{Ker}(\varphi)$ consists exactly of the "translations" of the Kernel, we may now consider the problem of turning this set into a group by assigning an **algebraic structure** on the set. To do this, we need to define a kind of "multiplication" between the fibers. A natural way to define such as operation is as follows, we define: 
$$
(uK)(vK) = uvK 
$$
As illustrated in the following proposition, this operation is **well-defined** and it does make $G / \text{Ker}(\varphi)$ into a Group: 

>[!success] Quotient Group
>Let $G$ be a group and let $K$ be the kernel of some homomorphism from $G$ to another group. Then the operation defined as:
>$$
>(uK)(vK) = uvK
>$$
>in the set $G / K$ is well-defined in the sense that if $u_1 \in uK$ and $v_1 \in vK$, then $u_1v_1K = uvK$. (The multiplication does not depend on the choice of representatives) Furthermore, $G/K$ under this operation is a group. 

**Proof**: To show that the operation is well-defined, it suffices to show that $u_1v_1 \in uvK$. By definition, the elements in $uvK$ consists of all elements $g \in G$ such that:
$$
\varphi(g) = \varphi(uv) = \varphi(u)\varphi(v)
$$
Notice also that as $u_1 \in uK$, $v_1 \in vK$, 
$$
\varphi(u_1v_1) = \varphi(u_1)\varphi(v_1) = \varphi(u)\varphi(v)
$$
Hence, $u_1v_1 \in uvK$, which prove that the operation is well-defined. Next, we verify that $G/K$ under this oepration is a group. Associativity is naturally inheritted from associativity in $G$. The identity element of $G/ K$ is $K$ since for all $g \in G$, :
$$
(gK)(K) = (K)gK = gK 
$$
The inverse of $gK$ is naturally $g^{-1}K$ since:
$$
(gK)(g^{-1}K) = (gg^{-1})K = K
$$
$$
(g^{-1}K)(gK) = (g^{-1}g)K = K
$$
Hence, $G/K$ is a group under the "multiplication" defined above. 

Intuitively speaking, this new operation defined on $G/K$ tells us that to multiply two fibers, we can take **any** representative from each fiber, multiply the two representatives, then find the fiber that contains the product. This fiber is then the product of our two fibers. Graphically, this can be represented as: 

![[Pasted image 20241002144417.png | center | 400]]

(Diagram from Dummit & Foote, *Abstract Algebra*)

The Group $G/K$ we have constructed above is called the *quotient group* (or *factor group*) of $G$ under the homomorphism $\varphi$. The fact that the result of multiplication is independent of the choice of representatives will be come crucial when we try to extend this idea of a quotient group to more general subgroups. 

### Cosets

The notion of "Translating" the kernel shown in the previous section can in fact be generalized to any subgroup of a group $G$, this lead naturally to th concept of *cosets*: 

>[!d] Cosets
>Let $G$ be a group and for any $H \leq G$, $g \in G$, the set $gH = \{gh : h \in H\}$ is called a *left coset* of $H$ (since the element is being multiplies on the left), and symmetrically, the set $Hg = \{hg : h \in H\}$ is called a *right coset* of $H$. 

>[!warning] Remark
>Using the language of cosets, we can then say that the quotient group $G / K$ consists of **all the disinct cosets of $K$.** 

The following proposition gives an important criteria to determin whether two cosets are equal: 

>[!success] Equivalence of Cosets
>Let $G$ be a group and $H \leq G$, then $uH = vH$ if and only if $u \in vH$, which is also equivalent to $v^{-1}u \in H$. 

**Proof**: If $u \in vH$, let $u = vh$, then for all $uh_1 \in uH$,  
$$
uh_1=  vhh_1 = v(hh_1) \in vH 
$$
so $uH \subseteq vH$. For the opposite inclusion, notice that for all $vh_1 \in vH$: 
$$
vh_2 = vh(h^{-1}h_2) = u(h^{-1}h_2) \in uH
$$
so $vH \subseteq vH$. Thus, if $u \in vH$, $uH = vH$. Conversely, if $uH = vH$, then for any $uh \in uH$, there exists $h' \in H$ such that $uh = vh'$. This implies that $u = vh'h^{-1} \in vH$, which completes the first part of the proposition. 

It is trivial to show that $u \in vH$ is equivalent to $v^{-1}u \in H$. If $u = vh$ for some $h \in H$, then $v^{-1}u = h \in H$. Conversely, if $v^{-1}u=h \in H$, $u = vh \in vH$, which completes the proof. 

As we've seen previously with the cosets of the kernel $K$, cosets form a natural **partition** of our group $G$: 

>[!success] Cosets form a Partition
>Let $G$ be a group and $H \leq G$, then all the left cosets of $H$ in $G$ partition $G$. (The same conclusion holds for right cosets.)

**Proof**: First, we show that:
$$
G = \bigcup_{g \in G} gH
$$
Since $gH \subset G$ for all $g \in G$, we naturally have that $\bigcup_{g \in G} gH \subseteq G$. For any $g \in G$, notice that $g = ge$ where $e \in H$, hence $g \in gH$, which implies that $G \subseteq \bigcup_{g \in G} gH$, completing the proof for the set equivalence. Next, we prove that distinct left cosets are disjoint. Suppose $uH$ and $vH$ are distinct cosets and $uH \cap vH \neq \emptyset$, then there exists $x \in   uH \cap vH$ such that:
$$
uh_1 = x = vh_2 \implies v^{-1}u  \ = h_1h_1^{-1} \in H
$$
By the previous proposition, this implies that $uH = vH$, which constradicts the assumption that they are distinct. Thus, all distinct left cosets of a subgroup $H$ forms a partition of $G$. 

![[8a3effcc6cf8682780a20bc84f6d439.jpg | center | 300]]

(Diagram from Artin, *Algebra*)

### Normal Subgroups and Quotient Groups

In the first subsection, we have constructed the quotient group $G/K$ from the kernel of a homomorphism, and using the language of cosets, we can say that the quotient group consists of all the distinct cosets of the kernel, which itself form a partition of the group $G$. In this subsection, we want to answer the following crucial question: 

<center> Can we construct a quotient group from any subgroup, instead of solely the kernel of some homomorphism? </center>

In general, **not all** subgroups can be used to form a quotient group due to the fact that the multiplication of cosets would not be well-defined in these subgroups. The following proposition reveals exactly which subgroups are suitable candidates ro form the quotient group: 

>[!success] Criteria to form a Quotient Group
>Let $G$ be a group and let $N \leq G$, then the operation defined on the set of left cosets of $N$ in $G$ as described by:
>$$
>(uN)(vN) = uvN
>$$
>is well-defined if and only if for all $n \in N$, for every $g \in G$, we have $gng^{-1} \in N$. In other words, for all $g \in G$, $gNg^{-1} = N$. Moreover, the set of left cosets, denoted by $G/N$, under this operation forms a group. 

**Proof**: Suppose that the coset multiplciation is well-defined, then specifically, we have:
$$
(N)(g^{-1}N) = (nN)(g^{-1}N) \iff g^{-1}N = ng^{-1}N
$$
for all $g \in G$ and any $n \in N$. Thus, we have that $ng^{-1} \in g^{-1}N$, which implies that there exists $n' \in N$ such that: 
$$
ng^{-1}= g^{-1}n' \iff gng^{-1} = n' \in N
$$
Hence, the subgroup $N$ must be closed under [[Group Actions#Examples of Group Actions|conjugation]]. Conversely, suppose that for all $n \in N$ and all $g \in G$, $gng^{-1} \in N$, we want to show that for any $u, v \in G$, and any $u_1 \in uN$ and $v_1 \in vN$, we have:
$$
uvN = u_1v_1N
$$
It suffices to show that $u_1v_1 \in uvN$. Suppose $u_1 = un_1$ and $v_1 = vn_2$, then:
$$
\begin{align}
u_1v_1 &= un_1vn_2\\
&= u(vv^{-1})n_1vn_2 \\
&= uv (v^{-1}n_1v)n_2 
\end{align}
$$
Since $N$ is closed under conjugation, we may deduce that $v^{-1}n_1v = v^{-1}n_1(v^{-1})^{-1} = n' \in N$. Thus:
$$
u_1v_1 = uv(n'n_2) \in uvN
$$
which prove that $u_1v_1 N = uvN$ for any $u, v \in G$. Consequently, the coset multiplication is well-defined. The rest of the work to verify that $G/N$ is a group is trivial: observe that $N$ is the identity element and $g^{-1}N$ is the inverse of $gN$ for any $g \in G$. 

With the above proposition in hand, we can see that $G/N$ is a group under coset multiplication if and only if $N$ is closed under conjugation. Such subgroups are given a special name:

>[!d] Normal Subgroups
>Let $G$ be a group. A subgroup $N$ of $G$ is called a *normal subgroup* if and only if for all $n \in N$ and all $g \in G$, $gNg^{-1} = N$. In particular, an element $g$ that satisfies $gNg^{-1} = N$ is said to *normalize* $N$. If $N$ is a normal subgroup of $G$, we shall write $N \unlhd G$. 

>[!warning] Note
>It is trivial to see that $N \unlhd G$ if and only if the normalizer of $N$ is $G$, i.e. $N_G(N) = G$. 

We may summarize our findings in the previous proposition concisely as follows: 

>[!success] Quotient Groups of Normal Subgroups
>The set of all left cosets $G/N$ under coset multiplication is a group if and only if $N \unlhd G$. 

When $G/N$ is a group, we once again call it a *quotient group*, or more specifically, *G mod N*. 

---

It is easy to see that the Kernel of any homomorphism is normal, so naturally, $G / \text{Ker}(\varphi)$ is a group; but the more surprising fact is that the converse also true: **a subgroup is normal** **if and only if it is the kernel of some homomorphism**. (How amazing!)

>[!success] Normality is Equivalent to being a Kernel 
>Let $G$ be a group and $N \leq G$, then $N \unlhd G$ if and only if $N$ is the kernel of some homomorphism. 

**Proof**: We first show that for any homomorphism $\varphi: G \to H$, $K = \text{Ker}(\varphi)$ is a normal subgroup of $G$. For any $n \in K$ and for any $g \in G$, notice that: 
$$
\begin{align}
\varphi(gng^{-1}) &= \varphi(g)\varphi(n)\varphi(g^{-1})\\
&= \varphi(g)e_H\varphi(g^{-1}) \\
&= \varphi(gg^{-1}) \\
&= \varphi(e_G)\\
&= e_H
\end{align}
$$
Thus, $gng^{-1} \in K$, so by definition, $K \unlhd G$. Conversely, suppose $N \unlhd G$, we consider the map $\varphi: G \to G/N$ defined by: 
$$
\varphi(g) = gN
$$
This is called the *natural projection* of $G$ onto $G/N$. We shall now prove that $\text{Ker}(\varphi) = N$. This is again trivial as we previously derived that $gN = N$ if and only if $g \in N$, so indeed $N$ is exactly the kernel of this homomorphism. 

As we can see in the section of [[Isomorphism Theorems]], introducing the quotient group $G/\text{Ker}(\varphi)$ allows us to **decompose the homomorphism into a surjective and an injective homomorphism**. The surjective map is precisely the natural projection as described in the proof above. This relation is illustrated in the following *commutative diagram*: 

```tikz
\usepackage{tikz-cd}
\usepackage{amsmath}
\tikzcdset{scale cd/.style={every label/.append style={scale=#1},
    cells={nodes={scale=#1}}}}
\begin{document}
\begin{tikzcd}[scale cd=1.3] G \arrow[rd, "\pi"] \arrow[r, "\varphi"] & H \\ & G/K \arrow[u, "\Phi"] \end{tikzcd}
\end{document}
```

where $K = \text{Ker}(\varphi)$, $\pi$ is the natural projection (which is surjective), and $\Phi$ is the isomorphism between $G/K$ and $\text{Im}(\varphi)$ (which is injective even when the codomain is $H$).  