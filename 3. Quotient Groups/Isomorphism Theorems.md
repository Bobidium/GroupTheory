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
>The *Special Linear Group*, denoted by $SL_n(\mathbb{F})$, is a subgroup of the **[[The Matrix Group and Quaternions|General Linear Group]]** $GL_n(\mathbb{F})$ satisfying the condition that for all $A \in SL_n(\mathbb{F})$, $\det(A) = 1$. In other words, the special linear group of order $n$ contains all elements with determinant $1$ in the general linear group. We want to find $GL_n(\mathbb{F}) / SL_n(\mathbb{F})$ by using the First Isomorphism Theorem. We need to find an isomorphism that has the special linear group as its Kernel. It is easy to deduce that the **determinant map** which maps every element in $GL_n(\mathbb{F})$ to its determinant is a group homommorphism between the general linear group and the multiplicative group $F$. The Kernel of this homomorphism is $SL_n(\mathbb{F})$ because these are precisely the elements that will be mapped to $1$. Also observe that image of the determinant map is every non-zero element in $\mathbb{F}$. Hence by the 1st Isomorphism Theorem: 
>$$
>GL_n(\mathbb{F}) / SL_n(\mathbb{F}) \simeq \mathbb{F} - \{0\}
>$$
>If $\mathbb{F}$ is a finite field of order $p$, then we further have that $[GL_n(\mathbb{F}) : SL_n(\mathbb{F})] = p-1$. 

In general, if we want to prove that for $N \unlhd G$, $G/N$ is isomorphic to some group using the 1st ISomorphism Theorem, we can adapt the following method: 

>[!abstract] Key Idea: Using 1st Isorphism Theorem
>1. Find a homomorphism such that the kernel is $N$. 
>2. Verify that the homomorphism is **well-defined**. 
>3. Find the image of the homomorphism. 
>4. Use the First Isomorphism Theorem to complete the proof. 

We shall be adopting this method to prove all of the Isomorphism Theorems that follow. 

### Second Isomorphism Theorem

The Second Isomorphism, or the *Diamond Isomorphism Theorem*, clarifies the relationship between a product of subgroups, the subgroups themselves, and the intersection of the subgroups. 

>[!success] Second Isomorphism Theorem
>Let $G$ be a group, $H, K \leq G$. If we have $H \leq N_G(K)$, i.e. $H$ normalizes $K$, then $HK \leq G$, $K \unlhd HK$, $H \cap K \unlhd H$, and:
>$$
>HK/K \simeq H/(H \cap K)
>$$

**Proof**: In [[Lagrange's Theorem and Products of Groups]], we have already prove that $H$ normalizes $K$ implies that $HK \leq G$. It is also trivial to prove that $K$ is normal in $HK$ since for any $hk \in HK$, and any $k' \in K$, we have $hkk'(hk)^{-1} = hkk'k^{-1}h^{-1}$, and the fact that $H$ normalizes $K$ can imply that $K \unlhd HK$. To prove the actual Isomorphism, we can utilize the first Isomorphism Theorem by constructing an homomorphism from $H$ to $HK/K$ with kernel $H \cap K$. The natural homomorphism to consider is $\varphi: h \mapsto hK$ for all $h \in H$. This map is obviously well-defined since there are no ambiguity in the repreentation of elements of $H$. This map is also surjective as for all $hkK = hK \in HK/K$, the element $h$ is mapped to it, so $\text{Im} (\varphi) = HK/K$. Next, $\varphi$ is a homomorphism because for any $h, h' \in H$:
$$
\varphi(h)\varphi(h') = (hK)(h'K) = hh'K = \varphi(hh')
$$
Lastly, notice that $\varphi(h) = e$ if and only if $h \in K$, so $K = \text{Ker}(\varphi)$. By the First Isomorphism Theorem, we have:
$$
HK/K \simeq H/(H \cap K)
$$
which completes the proof. 

>[!warning] Note
>Using this Theorem, we can have another proof for the order equation shown in [[Lagrange's Theorem and Products of Groups#Products of Subgroups]] **when $HK$ is a group**. The order equation more generalized as it does not require $HK$ to be a group. 

In a lattice, the subgroups $HK, H, K$ and $H \cap K$ are represented as below: 

![[Pasted image 20241010182658.png| center | 150]]

This explains why the 2nd Isomorphism is called the Diamond Isomorphism Theorem. It is worth noticing that $HK$ is the **first** subgroup that appears above $H$ and $K$ in the lattice, meaning that it is the **smallest** subgroup that contains both $H$ and $K$. (The proof of this is trivial.) Likewise, the intersection of $A$ and $B$ is the **largest** subgroup that is contained in both $A$ and $B$. So in a sense, the Second Isomorphism tells us that the way $H$ and $K$ are embedded into $HK$ is similar to the way $H\cap K$ is embedded into $H$ and $K$.   

### Third Isomorphism Theorem




### Fourth Isomorphism Theorem

