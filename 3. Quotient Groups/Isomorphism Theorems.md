---
aliases:
  - "[[Homomorphisms and Isomorphisms]]"
  - "[[Quotient Groups]]"
  - "[[Lagrange's Theorem and Products of Groups]]"
---
### First Isomorphism Theorem

On the basis of our previous discussions about fibers and kernels in [[Quotient Groups]], we have the following natural but highly useful result: 

>[!success] First Isomorphism Theorem
>Let $\varphi:  G \to H$ be a group homomorphism, then: 
>$$
>G / \text{Ker}(\varphi) \simeq \text{Im}(\varphi)
>$$

**Proof**: Define the function $f: G / \text{Ker}(\varphi) \to \text{Im}(\varphi)$ by $f(gK) = \varphi(g)$ for any $h \in \text{Im}(\varphi)$ and $K = \text{Ker}(\varphi)$. This map is well defined as suppose $gK = g'K$, we have $g^{-1}g' \in K$, so naturally $\varphi(g^{-1}g') = e \iff \varphi(g)  = \varphi(g')$, and conseuqently:
$$
f(gK) = \varphi(g) = \varphi(g') = f(g'K)
$$
$f$ is clearly surjective and to prove injectivity, simply notice that $\varphi(g) = \varphi(g')$ if and only if $g^{-1}g' \in K$ if and only if $gK = g'K$. Finally, $f$ is a homomorphism since:
$$
f(gKg'K) = f(gg'K) = gg' = f(gK)f(g'K)
$$
which completes the proof for the First Isomorphism Theorem. 

Notice that since the Kernel is a normal subgroup, the quotient group on the LHS is defined. Intuitively speaking, the First Isomorphism Theorem is simply saying that the fibers of the Homomorphism is essentially the same as the image of the homomorphism. This is trivial once we considered the definition of fibers. 

We have the following easy corollary:

>[!success] Index of the Kernel
>Let $\varphi: G \to H$ be a group homomorphism, then:
>$$
>[G : \text{Ker}(\varphi)] = |\text{Im}(\varphi)|
>$$

**Proof**: Trivial. 

>[!warning] Note
>$G$ does not have to be finite for the above propositions to hold. 

We can derive some seemingly non-trivial isomorphism relationship easily using the First Isomorphism Theorem:

>[!example] Special Linear Group
>The *Special Linear Group*, denoted by $SL_n(\mathbb{F})$, is a subgroup of the **General Linear Group** $GL_n(\mathbb{F})$ satisfying the condition that for all $A \in SL_n(\mathbb{F})$, $\det(A) = 1$. In other words, the special linear group of order $n$ contains all elements with determinant $1$ in the general linear group. We want to find $GL_n(\mathbb{F}) / SL_n(\mathbb{F})$ by using the First Isomorphism Theorem. We need to find an isomorphism that has the special linear group as its Kernel. It is easy to deduce that the **determinant map** which maps every element in $GL_n(\mathbb{F})$ to its determinant is a group homommorphism between the general linear group and the multiplicative group $F$. The Kernel of this homomorphism is $SL_n(\mathbb{F})$ because these are precisely the elements that will be mapped to $1$. Also observe that image of the determinant map is every non-zero element in $\mathbb{F}$. Hence by the 1st Isomorphism Theorem: 
>$$
>GL_n(\mathbb{F}) / SL_n(\mathbb{F}) \simeq \mathbb{F} - \{0\}
>$$
>If $\mathbb{F}$ is a finite field of order $p$, then we further have that $[GL_n(\mathbb{F}) : SL_n(\mathbb{F})] = p-1$. 





### Second Isomorphism Theorem


### Third Isomorphism Theorem


### Fourth Isomorphism Theorem

