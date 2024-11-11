---
aliases:
  - "[[Group Actions]]"
  - "[[Quotient Groups]]"
  - "[[Homomorphisms and Isomorphisms]]"
---
### Definition and Examples

In this note, we shall be studying a partiular example of [[Group Actions]], i.e. action by left multiplication. 

>[!d] Action by Left Multiplication
>Let $G$ be a group. We call the action of $G$ on **itself** defined by:
>$$
>g \cdot a = ga
>$$
>for any $g, a \in G$ the *action by left multiplication* of $G$ on itself. 

It is easy to verify that this is indeed a group action:

>[!success] Action by Left Multiplication is a Group Action
>The operation $\cdot : G \times G \to G$ defined by $g \cdot a = ga$ for any $g, a \in G$ is a group action. 

**Proof**: Trivial. 

In the following example, we list some elementary properties of this group action: 

>[!example] Elementary Properties of the Action by Left Multiplication
>1. The Action by Left Multiplication is [[Orbits and the Orbit-Stabilizer Theorem|Transitive]]. This is shown where for any $a, b \in G$, we pick $g = ba^{-1} \in G$ such that: $$ g \cdot a = (ba^{-1}) \cdot a = b(a^{-1}a) = b $$
>2. The Action by Left Multiplication is [[Group Actions#Definition|faithful]]. We can consider the Kernel of the action and notice that if $g \neq e$, then $g \cdot a = ga \neq a$ as otherwise, $g = a^{-1}a = e$ which is a contradiction. Hence, the action has a trivial kernel and is hence faithful. From the same argument, we can also see that the [[Group Actions#Definition|stabilizer]] of each element in $G$ is $\{e\}$. 

It will be beneficial to us to generalize this action a bit -- instead of considering multiplication with the group elements only, we can instead consider multiplication with **cosets** of a subgroup. 

>[!d] Action by Left Multiplication with Cosets
>Let $G$ be a group and let $H \leq G$. Let $A$ be the set of left cosets of $H$ in $G$. Then, $G$ can act on $A$ via left multiplication as defined by:
>$$
>g\cdot aH = gaH
>$$
>for all $g \in G, aH \in A$. 

Again, it is trivial to verify that this is indeed a group action. 

>[!warning] Note
>Notice how action by multiplication with elements is simply a special case of the above action where $H$ is chosen to be $\{e\}$.
>

### The Main Theorem

In this section, we derive the absolutely crucial result that summarizes the key properties of the actions defined in the previous section. The important theorem due to Cayley that describes the relationship between groups and symmetries will then follow as an immediate consequence to the theorem. j

>[!success] Properties of Action by Left Multiplication with Cosets
>Let $G$ be a group and $H \leq G$. Let $A$  denote the set of left coset if $H$ in $G$ and let $G$ act on $A$ via left multiplcation. Denote the permutation representation of this group action as $\pi_H$. Then, the folllowing properties hold:
>1. $G$ acts transitively on $A$. 
>2. The stabilizer of $eH \in A$ is the subgroup $H$. 
>3. The Kernel of the action is the subgroup $$ \text{Ker}(\pi_H) = \bigcap_{x \in G} x^{-1}Hx$$ and any normal subgroup of $G$ that is contained in $H$ is contained in the kernel. (i.e. it is the largest normal subgroup of $G$ in $H$)

**Proof**: The proof is relatively easy. We verify the properties one by one: 
1. To show that $G$ acts transitively on $A$, it suffices to prove that for any $aH, bH \in A$, there exists $g \in G$ such that $g \cdot aH = g \cdot bH$. This can be done by choosing $g = ba^{-1}$ (reference to the previous example on the multiplicatoin of group elements) so that: $$ g \cdot aH = (ga)H = b(a^{-1}a)H = bH$$thus proving that the action is transitive. 
2. The Stabilizer of $eH$ consists of all the elements $g$ such that $g \cdot eH = eH$. This is equivalent to: $$ gH = eH \iff g \in H $$which completes the proof. 
3. The Kernel of an action is simply the **intersection** of all stabilizers of the group action. Generalizing the previous property, we can see that for any $aH \in A$, the stabilizer of $aH$ consists of all elements $g \in G$ such that $g \cdot aH = aH$. This is equivalent to: $$ (ga)H = aH \iff a^{-1}ga \in H \iff $$Thus, for the stabilizer of $aH$ consists of exactly the elements of the form $aha^{-1}$ for some $h \in H$. In other words, $\text{stab}_G(aH) = aHa^{-1}$. Resultingly, taking the intersection of all such sets gives the Kernel of the Homomorphism: $$ \text{Ker}(\pi_H) = \bigcap_{x \in G} xHx^{-1} $$To show that this kernel is the largest normal subgroup in $H$, first notice that $\text{Ker}(\pi_H) \leq eHe^{-1} = H$, and for any $xhx^{-1} \in \text{Ker}(\pi_H)$ and $g\in G$, we have $$ gxhx^{-1}g^{-1} = (gx)h(gx ^{-1}) \in\text{Ker}(\pi_H)$$so indeed, $\text{Ker}(\pi_H) \unlhd H$. Now, for any $K \unlhd G$ such that $K \leq H$, we have that for all $x \in G$, $xKx^{-1} = K$,  so: $$ K = \bigcap_{x \in G} xKx^{-1} \leq \bigcap_{x \in G} xHx^{-1} = \text{Ker}(\pi_H)$$which completes the proof. 
 



### Cayley's Theorem and Groups of Minimal Prime Index


