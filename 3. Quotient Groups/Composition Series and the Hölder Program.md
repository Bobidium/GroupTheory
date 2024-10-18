---
aliases:
  - "[[Quotient Groups]]"
  - "[[Lagrange's Theorem and Products of Groups]]"
---
### Finite Abelian Groups and Simple Groups

We first prove an important proposition about Finite Abelian Groups that is a weakened version of [[Theorem of Cauchy|Cauchy's Theorem]]. The proof of the proposition illustrates the power of induction in finite group theory: 

>[!success] Cauchy's Theorem for Finite Abelian Groups
>If $G$ is a finite abelian group and $p$ is a prime dividing $|G|$, then $G$ contains an element of order $p$. 

**Proof**: We proceed by induction on the order of $G$. In the base case, the proposition is obviously true for the trivial group $\{e\}$. Suppose that for all positive integers $k < n$, any group with order $k$ satisfies the proposition, we want to prove that any group of order $n$ satisfies the proposition. If $G$ is cyclic, then we are done, as the subgroups of a cyclic group corresponds bijectively to the factors of $|G|$. If $G$ is not cyclic, then there exists an element $x \in G$ such that $o(x) < |G|$. Then, as $G$ is an abelian group, $\langle x \rangle \unlhd G$. Since $|\langle x \rangle| < |G|$, we can use the inductive hypothesis to deduce that for every prime dividing $o(x)$, there is a corresponding subgroup of the desired order in $\langle x \rangle$. If $p \nmid o(x)$, then we can consider the quotient group $G / \langle x \rangle$. As $|G / \langle x \rangle| = G / o(x)$, $p$ must divide $|G / \langle x \rangle|$. By the inductive hypothesis, we can again deduce that there exists a subgroup of order $p$ in $G/\langle x \rangle$. Hence, there exists $g\langle x\rangle \in G / \langle x \rangle$ such that $o(g\langle x \rangle) = p$. This implies that $g^p \in \langle x \rangle$, and that $p \mid o(g)$ which again implies the existence of a cyclic group of order $p$ in $G$. This completes the proof. 

This is an elegant proof and illustrates some important ideas in finite group theory. 

>[!abstract] Key Ideas
>1. we can see the idea of **piecing together information about a normal subgroup and its quotient group to obtain information about our original group**. Since both the subgroup and the quotient group has order less than the original group. we can use the inductive hypothesis to obtain their information. We will see this idea again in the second part of the *Hölder Program*. 
>2. The reason why this argument works so well is based on the fact that $G$ is **finite and abelian**, so every subgroup of $G$ is normal and we can utilise the quotient group nicely in our proof. However, in most groups, we don't have such strong properties, which makes things more difficult when we want to prove statement about any aribtrary group. 

On the other end of the spectrum, opposing finite abelian groups, we have the *simple groups*: 

>[!d] Simple Groups
>A group $G$ is *simple* if $|G| > 1$ and the only normal subgroups of $G$ are $\{e\}$ and $G$. 

In other words, a simple group has no proper normal subgroups other than the trivial group. In the contrary to Abelian Groups, we have 

### Jordan-Hölder Theorem and the Hölder Program

### Solvable Groups