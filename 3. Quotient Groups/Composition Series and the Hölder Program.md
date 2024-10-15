---
aliases:
  - "[[Quotient Groups]]"
  - "[[Lagrange's Theorem and Products of Groups]]"
---
### Finite Abelian Groups and Simple Groups

We first prove an important proposition about Finite Abelian Groups that is a weakened version of [[Theorem of Cauchy|Cauchy's Theorem]]. The proof of the proposition illustrates the power of induction in finite group theory: 

>[!success] Cauchy's Theorem for Finite Abelian Groups
>If $G$ is a finite abelian group and $p$ is a prime dividing $|G|$, then $G$ contains an element of order $p$. 

**Proof**: We proceed by induction on the order of $G$. In the base case, the proposition is obviously true for the trivial group $\{e\}$. Suppose that for all positive integers $k < n$, any group with order $k$ satisfies the proposition, we want to prove that any group of order $n$ satisfies the proposition. If $G$ is cyclic, then we are done, as the subgroups of a cyclic group corresponds bijectively to the factors of $|G|$. If $G$ is not cyclic, then there exists an element $x \in G$ such that $o(x) < |G|$. Then, as $G$ is an abelian group, $\langle x \rangle \unlhd G$. Since $|\langle x \rangle| < |G|$, we can use the inductive hypothesis to deduce that for every prime dividing $o(x)$, there is a corresponding subgroup of the desired order in $\langle x \rangle$. If $p \nmid o(x)$, then we can consider the quotient group $G / \langle x \rangle$. As $|G / \langle x \rangle| = G / o(x)$, $p$ must divide $|G / \langle x \rangle|$. By the inductive hypothesis, we can again deduce that there exists a subgroup of order $p$ in $G/\langle x \rangle$. Hence, there exists $g\langle x\rangle \in G / \langle x \rangle$ such that $o(g\langle x \rangle) = p$.    

### Jordan-Hölder Theorem and the Hölder Program

### Solvable Groups