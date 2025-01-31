---
aliases:
  - "[[Group Actions]]"
  - "[[Homomorphisms and Isomorphisms]]"
  - "[[The Symmetric Group]]"
---
### Further Examples of Group Action

Recall from [[Group Actions]] the various definitions associated with Group Actions, especially *Permutation Representations* and the *Kernel* of a Group Action. In this section, we shall be extending the examples in [[Group Actions]] to see some more examples of the group structure acting on a variety of objects. 

>[!example] $S_n$ acting on a set of $n$ objects
>Let the group $S_n$ act on the set $A = \{1, 2, ..., n\}$ by the action defined by $\sigma \cdot i = \sigma (i)$, i.e. the "natural" action where the elements in $A$ are premuted according to $\sigma$. Then, the permutation representation of this action, which is the homomorphism $\varphi : S_n \to S_n$ that associates the action of one particular group element on all elements in $A$ with a bijection on $A$, is the **identity homomorphism**. This also shows that the group action is *faithful* (have an injective permutation representation). Furthremore, it is easy to see that the [[Centralizers, Normalizers, Stabilizers and Kernels|stabilizer]] of any element in $A$ is isomorphic to $S_{n-1}$. 

The reason we include this example here is that it illustrates the *orbit-stabilizer theorem* and the idea of a *transitive group action* really well. 

We have already seen $D_8$ acting on the four vertices of a square. In the same scenario, we can also think about $D_8$ as acting on the **two diagonals** of the square, which is a set of two elements. We shall be looking at how this action is different from the action on four vertices: 

>[!example] $D_8$ acting on two diagonals
>Label the four vertices of a square as $1, 2, 3, 4$ and let $A$ be the set of pairs of opposite vertices: $A = \{\{1, 3\}, \{2, 4\}\}$. 
>![[Pasted image 20241103211751.png| center | 300]]
>$D_8$ ([[The Dihedral Group| Dihedral Group]] of order $8$) acts on $A$ because the symmetries of the square **preserves the relative positions** between vertices in the same diagonal. In other words, each symmetry sends one diagonal to another (which could be the same diagonal). For example, rotation clockwise by $90$ degrees interchanges the two diagonals. Let $\textbf{1} = \{1, 3\}$ and $\textbf{2}= \{2, 4\}$, then a rotation by $90$ degrees is the same as the transposition $(\textbf{1}, \textbf{2})$. In this sense, $D_8$ acts on $A$ by permuting the diagonals correspondingly. Notice that this action is **not faithful** as the Kernel of the action is $\{r^2, s\}$. This is different from when $D_8$ acts on the four vertices, in which case the action is faithful. 

>[!warning] Remark
>The above example illustrates how the same group can result in very different action when acting on different sets. Thus, we need to be aware that a group action depends on **both** the group and the set being acted. 

This provides an example of a *non-transitive* group action, as we shall see in the next section. 

### Orbit and the Orbit-Stabilizer Theorem

In this section, we introduce another important property of group actions -- the *orbit* of a group action. By studying the orbits of a group action, we are able to obtain information about the group itself (As we will see in [[Sylow's Theorem]] and the the last section). It can be said that the orbits of a group action assigns value to the study of actions. 

The orbit has many commonalities with [[Lagrange's Theorem and Products of Groups|cosets]], the most important of which is that they both originate from an **equivalence relation**: 

>[!success] Equivalence Relation of a Group Action
>Let $G$ be a group acting on a non-empty set $A$, then the relation defined as: 
>$$
>a \sim b \iff a = g \cdot b \text{ for some } g \in G
>$$
>is an equivalence relation. 

Notice that this relation is saying that two elements in $A$ are "equal" if and only if there is a group element that cann act on $a$ to give $b$ (or vice versa). 

**Proof**: We only need to verify the three conditions for an equivalence relation. Fistly, obviously $a \sim a$ as $a = e \cdot a$ by definition of a group action. If $a \sim b$, then there exists $g \in G$ such that $a = g \cdot b$. We then act on the left by the element $g^{-1}$ to get: 
$$
g^{-1} \cdot a = g^{-1} \cdot (g \cdot b) = (g^{-1} g) \cdot b = e \cdot b = b
$$
Hence, $b \sim a$, and this verifies the symmetry condition. For transitivity, notice that if $a \sim b$ and $b \sim c$, then there exist $g_1, g_2 \in G$ such that $a = g_1 \cdot b$ and $b = g_2 \cdot c$. Combining the two equalities yield:
$$
a = g_1 \cdot (g_2 \cdot c) = (g_1g_2) \cdot c
$$
Hence, $a \cdot c$ and we are done. 

Notice that from this equivalence relation, we naturally get equivalence classes. These equivalence classes are called the *orbits* of the action: 

>[!d] Orbits of a Group Action
The *orbits* of a group action are precisely the equivalence classes of the above equivalence relation. More specifically, the set $C_a$ defined as: 
>$$
>C_a = \{ g \cdot a : g \in G \}
>$$
>is called the *orbit* of the action containing $a$. Sometimes, this orbit is also denoted as $\text{orb}_G(a)$. 

Trivially, we can deduce from the fact that orbits are equivalence classes that the orbits **partition $A$**.

>[!success] Orbits form a Partition
>Let $G$ act on a non-empty set $A$, then the orbits of the action partition $A$. 

In some rare occasion, it might be the case that group elements acting on a single element $a$ yields **every element** in $A$. In this case, there is only one equivalence class and hence only one orbit. If this is the case, we call the group action *transitive*: 

>[!d] Transitive Group Actions
>Let $G$ be a group acting on a non-empty set $A$. Then the action of $G$ on $A$ is called *transitive* if and only if there is only **one orbit**. In other words, for any $a, b \in A$, there exists $g \in G$ such that $a = g \cdot b$. 

Next, we shall prove some combinatorial results regarding the total number of elements in a particular orbit (*Orbit-Stabilizer Theorem*) and the total number of distinct orbits (*Burnside's Lemma*) for a group action:

>[!success] Orbit-Stabilizer Theorem
>Let $G$ be a group acting on the non-empty set $A$. Then the number of elements in the orbit containing $a \in A$, i.e. $|\text{orb}_G(a)|$ is: 
>$$
>|\text{orb}_G(a)| = [G:\text{Stab}_G(a)]
>$$

>[!warning] Note
>Notice that this thoerem holds even for **infinite groups**, as the index is defined without specifying that the group is finite. In the special case where the group is indeed finite, this formula can be rewritten as:
>$$
>|\text{orb}_G(a)| = \frac{|G|}{|\text{Stab}_G(a)|}
>$$
>using Lagrange's Theorem

**Proof**: We shall denote the stabilizer of $a$ using the notation $G_a$. We proceed with the proof by constructing a direct bijection between the set of left cosets of $G_a$ and the orbit containing $a$. For any $b \in \text{orb}_G(a)$, $b$ can be expressed as $g \cdot a$ for some $g \in G$. We define the map $f : \text{orb}_G(a)\to G/G_a$ by: $f(g \cdot a) = gG_a$. We can now verify that this is indeed a bijection. The map is clearly surjective as every coset of $G_a$ can be expressed as $gG_a$ for some $g \in G$. $f$ is also injective as $gG_a = g'G_a$ if and only if $g^{-1}g' \in G_a$ and resultingly: 
$$
(g^{-1}g') \cdot a = e \implies g\cdot a = g^{-1} \cdot a
$$
Hence, $f$ is the desired bijection and the desired result follows naturally. 

As an easy corollary, we can see that a group action is transitive if and only if $|\text{orb}_G(a)| = |A|$ if and only if $|G : \text{Stab}_G(a)| = |A|$. As an example, using this result, we can prove that the action of $S_n$ on $\{1, 2, ..., n\}$ is transitive: 

>[!example] An action of $S_n$ is transitive
>As mentioned previously, the stabilizer of any element $i$ is isomorphic to $s_{n-1}$, which has an order of $(n-1)!$. Hence, by the Orbit-Stabilizer Theorem, we have:
>$$
>|\text{orb}_{S_n} (i)| = \frac{n!}{(n-1)!} = n = |A|
>$$
>which implies that the action is transitive. 

### Burnside's Lemma

We have another very useful combinatorial result about orbits that gives a formula for the total number of distinct orbit for a given group action. 

>[!success] Burnside's Lemma
>Let $G$ be a group acting on the non-empty set $X$ and let $|G/X|$ denote the number of distinct orbits of the group action. Then, the following formula holds: 
>$$
>|G/X| = \frac{1}{|G|} \sum_{g \in G} X^g
>$$ 
>where $X^g$ denotes the total number of elements in $X$ that are **fixed** by the element $g$. 

**Proof**: The proof of this result is very elegant. We can first rewrite the expression on the RHS as: 
$$
\frac{1}{|G|} \sum_{g \in G} |\text{Stab}_G(a)|
$$
because from the example table below: 

![[b4806912991c5204455de2d2c9b301b.jpg| center | 350]]

We are simply shifting our perpsective from summation by rows to summation by column to get the above expression. Applying the Orbit-Stabilizer Theorem, we may further deduce that the expression is: 
$$
\sum_{x \in X} \frac{1}{|\text{orb}_G(x)|}
$$
From this point on, we can simply make the easy observation that if $x$ and $y$ belong to the same orbit, then they $|\text{orb}_G(x)| = |\text{orb}_G(y)|$, and consequently, we can group the above summation by the orbits and notice that the terms in the same orbit sums to $1$. Hence, this counts exactly the disitinct orbits of the action and proves the desired formula: 
$$
|G/X| = \frac{1}{|G|} \sum_{g \in G} X^g
$$

We shall consider a simple combinatorics question that can be solved using Burnside's Lemma: 

>[!example] Coloring of a Square
>Suppose we are given $n$ distinct colors to color the four vertices of a square. How many distinct colorings are there? (Note: two colorings are considered the **same** if and only if there exists a rotation about the center of the square that transforms one coloring to another). 

**Solution**: Consider the group $G = \{e, r, r^2, r^3\} \leq D_8$ acting on the four vertices of a square, where $r$ denotes the rotation clockwise by $90$ degrees. Notice that the number of distinct colorings is the same as the number of distinct orbits of this group action, so we can apply Burnside's Lemma. First, consider the number of colorings that are fixed by the identity rotation. Clearly, all colorings are fixed by the identity, so consequently, $X^e = n^4$. How many colorings are fixed by a rotation by $90$ degrees? Notice that the diagonals of the square are exchanged after the rotation, so the only case where a coloring is fixed by this rotation is when **all four vertices** have the same color. Hence, in this case $X^r = n$. For a rotation clockwise by $180$ degrees, notice that the top edge and the bottom edge exchange positions, so a coloring is fixed if and only if the vertices in the top edge have the same color, and the vertices in the bottom edge have the same color. This gives a total of $X^{r^2} = n^2$ colorings that are fixed. Lastly, a rotation by $270$ degrees clockwise is equivalent to a rotation by $90$ degrees clockwise, so $X^{r^3} = X^r = n$. Hence, in total, Burnside's Lemma gives us: 
$$
\frac{1}{|G|} \sum_{g \in G} X^g = \frac{1}{4}(n^4 + n^2 + 2n)
$$
different colorings of the square with $n$ colors. 

### Application: Unique Cycle Decomposition

As an important application of orbits, we shall be proving a theorem which we omitted in the note [[The Symmetric Group]]: that the decomposition of any permutation in $S_n$ into cycles is **unique**: 

>[!success] Unique Cycle Decomposition
>The cycle decomposition of any permutation in $S_n$ is unique. 

**Proof**: We shall prove that the elements involved one cycle in the cycle decomposition forms an orbit under the group action of $S_n$ on $A = \{1, 2, ..., n\}$. In other words, if a permutation can be decomposed into $(12)(34)$, then the orbits of this permutation are precisely $\{1, 2\}$ and $\{3, 4\}$. The way we approach this is by using the group structure of $S_n$. For any $\sigma \in S_n$, we can consider the subgroup generated by $\sigma$, i.e. $G = \langle \sigma \rangle$. When this subgroup acts on $A$, it produces distinct orbits $\mathcal{O}_i$. Let $\mathcal{O}$ be one of these orbits and let $x \in \mathcal{O}$. From the proof of the Orbit-Stabilizer Theorem, we know that the function $f$ that maps $\sigma(x) \to \sigma G_x$ is a bjection from $\mathcal{O}$ to $G / G_x$.  As $G$ is cyclic and hence abelian, $G_x \unlhd G$, so $G / G_x$ is the also a cyclic group. Hence, the elements of $G/ G_x$ are precisely: 
$$
G/G_x = \{ \sigma^i{G_x} : 0 \leq i < d\}
$$
where $d$ is the index $[G : G_x] = |\mathcal{O}|$. With the bijection $f$, we can deduce that the distinct elements of $\mathcal{O}$ are: 
$$
\mathcal{O} = \{\sigma^i(x) : 0 \leq i < d\}
$$
This shows that whenever a permutation $\sigma$ acts on an element $x$, it acts as a cycle and produces a corresponding orbit that is also cyclic. As a result, the disjoint orbits of the action corresponds to the cycles, which proves the existence of a cycle decomposition. To prove the uniqueness, we may simply notice that no matter which **representative** we choose for each orbit, the above argument would yield the same cyclic permutation of the elements in the orbit, and, as the orbits of $\langle \sigma \rangle$ are unique determined by $\sigma$, the uniqueness of cycle decomposition can be deduced easily. 

>[!warning] Remark
>This proof shocases the important idea that by studying the **action of a group on a set**, we are actually able to obtain information about the **group structure** itself. This highlights the importance of group actions in all of group theory. 