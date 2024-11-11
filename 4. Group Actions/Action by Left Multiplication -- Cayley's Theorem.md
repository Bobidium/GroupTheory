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

In this section, we derive the absolutely crucial result that summarizes the key properties of the actions defined in the previous section. The important theorem due to Cayley that describes the relationship between groups and symmetries will then follow as an immediate consequence to the theorem. 

>[!success] Properties of Action by Left Multiplication with Cosets
>Let $G$ be a group and $H \leq G$. Let $A$  denote





### Cayley's Theorem and Groups of Minimal Prime Index


