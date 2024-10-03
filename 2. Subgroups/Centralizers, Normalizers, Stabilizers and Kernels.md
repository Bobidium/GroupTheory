---
aliases:
  - "[[Subgroups]]"
  - "[[Homomorphisms and Isomorphisms]]"
---
### Centralizers and Normalizers

The basic idea behind the introduction of "centralizers" and "normalizers" is to construct a subgroup from a **subset** of a group that is not necessarily itself a subgroup. 

>[!definition] Centralizers
>Let $G$ be a group and $A$ be a non-empty subset of $G$. The *Centralizer* of $A$, denoted as $C_G(A)$, consists of all elements in $G$ that commutes every element in $A$. In other words: 
>$$
>C_G(A) = \{ g \in G: gag^{-1} = a \text{ for all }a \in A \}
>$$

>[!warning] Note
>Notice that it is equivalent to define the centralizer as:
>$$
>C_G(A) = \{ g \in G : ga = ag \text{ for all }a \in A \}
>$$
>which explicitly presents its relationship with commutativity. 

We can verify that the centralizer is indeed a [[Subgroups|subgroup]] of $G$: 

>[!success] Centralizer as a Subgroup
>For any non-empty subset $A$ of a group $G$, $C_G(A) \leq G$. 

**Proof**: As for all $a \in A$, $ege^{-1} = a$, $a \in C_G(A)$, so the centralizer must contain the identity. Now, suppose $g \in C_G(A)$, then $gag^{=1} = a$ for all $a \in A$. Multiply by $g^{-1}$ on the left abd $g$ on the right to both sides of the equation shows that:
$$
g^{-1} (gag^{-1}) g = g^{-1} ag \implies a = g^{-1}ag = g^{-1} a (g^{-1})^{-1}
$$
Consequently, $g^{-1} \in C_G(A)$, so the centralizer is closed under taking inverses. Lastly, suppose $g_1, g_2 \in C_G(A)$, then:
$$
\begin{align}
(g_1g_2) a (g_1g_2)^{-1} &= (g_1g_2) a (g_2^{-1}g_1^{-1})\\
&= g_1(g_2 a g_2^{-1})g_1^{-1} \\
&= g_1ag_1^{-1} \\
&= a
\end{align}
$$
which shows that $g_1g_2 \in C_G(A)$. Thus, the centralizer is closed under the group operation and resultingly, $C_G(A) \leq G$. 

Normalizers can be trreated as a weker version of centralizers, in the sense that it captures the elements in a group that "fixes" the subset $A$ as a whole via conjugation, instead of fixing each element of $A$ individually: 

>[!definition] Normalizers
>Let $G$ be a group and $A$ be a non-empty subset of $G$. The *Normalizer* of $A$, denoted as $N_G(A)$ is defined as:
>$$
>N_G(A) = \{ g \in G : gAg^{-1}  = A \}
>$$
>where $gAg^{-1} = \{ gag^{-1} : a \in A \}$. 

In the same way we proved that the centralizer is a subgroup, we can prove that the normalizer is a subgroup: 

>[!success] Normalizer as a Subgroup
>For any non-empty subset $A$ of a group $G$, $N_G(A) \leq G$. 

There is also an obvious relationship between the centralizer and normalizer of the same subset $A$: 

>[!success] Centralizer as a Subgroup of the Normalizer
>For any nonempty $A \subseteq G$, $C_G(A) \leq N_G(A)$. 

**Proof**: If suffices to prove that $C_G(A) \subseteq N_G(A)$ as $C_G(A)$ is already proven to be a group and the two subgroups inherit the same group operation from $G$. This is trivial since for any $g \in C_G(A)$ and every $a \in A$, $gag^{-1} = a$, so naturally $gAg^{-1} = A$, which shows that $g \in N_G(A)$. 

To illustrate these two concepts, we shall be finding the centralizers and normalizers of the following subset in the [[The Dihedral Group]] $D_{2n}$:
$$
A = \{ e, r, r^2, ..., r^{n-1} \}
$$
 
>[!example] Centralizer of $A$ in $D_{2n}$
>We claim that $C_{D_{2n}}(A) = A$. First notice that all rotations commute with each other: $r^i r^{j} = r^{i+j} = r^{j+i} = r^j r^i$, so we have that $A \subset C_{D_{2n}}(A)$. Now, consider the elements $s \in D_{2n}$. $s \not \in C_{D_{2n}}(A)$ because: 
>$$
>sr = r^{-1}s = r^{n-1}s \neq rs
>$$
>As a result of this, none of the elements of the form $sr^{i}$ are in the centralizer: suppose otherwise, then both $sr^{i}$ and $r^{-i}$ are in the centralizer; with the centralizer being a subgroup, we have that $sr^{i}r^{-i} = s \in C_{D_{2n}}(A)$, which is a contradiction. Thus, elements in the centralizer are exactly the elements of $A$. 

>[!example] Normalizer of $A$ in $D_{2n}$
>We claim that $N_{D_{2n}} (A) = D_{2n}$. We shall prove this fact in two different methods. 
>1. As $C_{D_{2n}}(A) \le N_{D_{2n}}(A)$, $A \subset N_{D_{2n}}(A)$, so naturally $r \in N_{D_{2n}}(A)$. Now, consider the element $s \in D_{2n}$, observe that: $$ sAs^{-1} = \{ ses^{-1}, srs^{-1} , ..., sr^{n-1}s^{-1} \} = \{e, r^{n-1}, r^{n-2}, ..., r\} = A$$ so $s \in N_{D_{2n}}(A)$. As $r$ and $s$ are both in $N_{D_{2n}}(A)$ and they generate $D_{2n}$, naturally, $D_{2n} \subset N_{D_{2n}}(A)$, which proves that $N_{D_{2n}}(A) = D_{2n}$. 
>2. The second approach we can take is by using [[Lagrange's Theorem and Products of Groups|Lagrange's Theorem]], which implies that $|N_{D_{2n}}(A)| \mid |D_{2n}| = 2n$. Now, since $A \subset N_{D_{2n}}(A)$, $|N_{D_{2n}}(A)| \geq n$, so the only possibilities for the order of the normalizer are $n$ or $2n$. If the order is $n$, then it only consists of the elements in $A$. However, as we've seen, $s \in N_{D_{2n}}(A)$ but $s \not \in A$, so $|N_{D_{2n}}(A)| = 2n$ and consequently, $N_{D_{2n}}(A) = D_{2n}$. 

### Center of a Group

Intuitively speaking, the *Center* of a group consists of the elements that can commute with every element in the group. Its definition is NOT dependent on a subset of the group like in the definitions of centralizers and normalizers, it is only dependent on the group itself: 

>[!def] Center of a Group
>Let $G$ be a group. The *center* of $G$, denoted by $Z(G)$ is defined as: 
>$$
>Z(G) = \{ g \in G : gx = xg \text{ for all }x \in G \}
>$$

>[!warning] Remark
>It is equivalent to define the center as being equal to $C_G(G)$ as we are simply replacing the subset $A$ by the entire group $G$. Conseuqently, as centralizers are subgroups, the center of a group must also be a subgroup. 

There is a trivial relationship between the center of a group and the Centralizer of any subset of the group: 

>[!success] Center as a Subgroup of the Centralizer
>Let $G$ be a group and $A$ be any non-empty subset of $G$, then $Z(G) \leq C_G(A)$. 

**Proof**: It suffices to prove that $Z(G) \subseteq C_G(A)$. Notice that for all $g \in Z(G)$,  $g$ commutes with every element in $G$. As elements of $A$ are already elements of $G$, $g$ must also commute with every element in $A$, so $g \in C_G(A)$, completing the proof. 

To summarize, the following relation holds between the center, the centralizer and the normalizer of any subset $A$ of a group $G$: 
$$
Z(G) \leq C_G(A) \leq N_G(A)
$$

As an example, we shall characterize fully the center of the dihedral group: 

>[!success] Center of $D_{2n}$
>The Center of $D_{2n}$ is: 
>1. $\{e\}$ if $n$ is odd. 
>2. $\{e, r^{k}\}$ where $2k  = n$ if $n$ is even. 

**Proof**: Let $A = \{e, r, r^2, ..., r^{n-1}\}$, then we have that $Z(D_{2n}) \subseteq C_{D_{2n}}(A) = A$, so the center must consists only of the identity and rotations of the form $r^i (i \neq 0)$. Notice that for $r^i$ to be in the center, it must satisfy:
$$
sr^i = r^{n-i}s =  r^is
$$
which is equivalent to $n-i = i \implies 2i = n$. If $n$ is odd, no such $i$ exists, so the center consists solely of $e$. If $n$ is even, then the only $i$ must be $k$ where $2k = n$. This completes the proof. 

### Stabilizers and Kernels of an Action

Having introduced Centralizers, Normalizers and the Center, we can now look at them with the lens of group actions. The fact that they are all subgroups is inherited from the fact that they are *stabilizers* or *kernels* of a group action. 

>[!d] Stabilizer of a Group Action
>Let $G$ act on a set $A$ by the action $g \cdot a$. For any $a \in A$, the *stabilizer* of $a$ under the action, denoted by $\text{Stab}_G(a)$ is:
>$$
>\text{Stab}_G(a) = \{ g \in G : g \cdot a = a \}
>$$

In simpler words, the stabilizer of $a$ is the set of all element in $G$ such that fixes $a$ under the group action. We can show that stabilizers are always subgroups of $G$: 

>[!success] Stabilizer as a Subgroup
>Let $G$ act on a set $A$, then for any $a \in A$, $\text{Stab}_G(a) \leq G$. 

**Proof**: The proof is trivial by considering the definition of group actions. Firstly, since $e \cdot a = a$ by definition, $e \in \text{Stab}_G(a)$. Next, suppose $g \in \text{Stab}_G(a)$, then:
$$
\begin{align}
g^{-1}\cdot a &= g^{-1}\cdot (g \cdot a) \\
&= (g^{-1}g) \cdot a \\
&= e \cdot a \\
&= a
\end{align}
$$
so $g^{-1} \in \text{Stab}_G(a)$. Finally, suppose $g_1, g_2 \in \text{Stab}_G(a)$, then:
$$
\begin{align}
(g_1g_2)\cdot a &= g_1\cdot (g_2 \cdot a) \\
&= g_1 \cdot a \\
&= a
\end{align}
$$
so $g_1 g_2 \in \text{Stab}_G(a)$ and $\text{Stab}_G(a)$ is closed under the group operation. As a result, $\text{Stab}_G(a) \leq G$. 

We can restirct stabilizers to the *Kernel* of a group action: 

>[!success] Kernel of a Group Action
>Let a group $G$ act on $A$ by $g \cdot a$. The *Kernel* of this group action is defined to be the set of all elements $g$ such that its permutation representation is the identity. In other words: 
>$$
>\text{Ker}(G) = \{ g \in G : g\cdot a = a \text{ for all }a \in A \}
>$$

>[!example] Example of Kernel
>Consider the action of $D_{2n}$ on the set of vertices of an $n$-gon. The Kernel of this group action is only $\{e\}$ since no other element in $D_{2n}$ can fix all vertices of the $n$-gon. 

Using these terminologies, we can now understand centralizers, normalizers and centers using Group Actions: 
1. For a group $G$, let $\mathcal{P}(G)$ denote its power set (i.e. the set of all subsets of $G$) and define a group action $G \times \mathcal{P}(G) \to \mathcal{P}(G)$ by: $g \cdot A = gAg^{-1}$ for all $A \in \mathcal{P}(G)$. Then, naturally **$N_G(A)$ is the stabilizer of $A$ under this conjugation action on the power set.**  
2. Let the group $N_G(A)$ act on the set $A$ via the conjugation action. This is a well-defined action since the result of taking conjugation by $g$ stays within $A$ if $g \in N_G(A)$. Then it is not hard to see that **$C_G(A)$ is the Kernel of this action**.  
3. **Let $G$ act on itself via the conjugation action, then the kernel of this action is $Z(G)$.** 

It can be seen from this example that studying subgroups of a particular group can be done via the study of corresponding group actions. 









 