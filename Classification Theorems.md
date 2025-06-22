---
aliases:
  - "[[Definition and Elementary Properties of Groups]]"
  - "[[Subgroups]]"
  - "[[Homomorphisms and Isomorphisms]]"
---
In this note, we summarize some important Classification Theorems of Finite Groups. 

### Classification of Groups of Order 4

Apart from the Cyclic group of order $4$, there exists another group of order $4$, as we shall define below: 

>[!d] Klein $4$-Group
>The *Klein 4- Group*, denoted by $V_4$, consists of $4$ elements $\{e, a, b, c\}$ with multiplication defined as in the following multiplication table: 
>
>![[Pasted image 20241003231409.png | center | 200]]
>i.e. any the square of any element is the identity, and the product of any two distinct non-identity elements gives the third non-identity element. 

>[!warning] Note
>The Klein 4-Group is an Abelian Group of order $4$. 

Are there any other groups of order $4$ that are not isomorphic to either the Klein 4-Group or the cyclic group of order $4$? The following **classification theorem** says no: 

>[!success] Classification of Groups of Order $4$
>For a group $G$, if $|G| = 4$,  then $G \simeq Z_4$ or $G \simeq V_4$. 

**Proof**: Suppose $G$ contains an element $x$ of order $4$, then by the proposition in [[Cyclic Groups]], we have that $\langle x \rangle \leq G$ and that $|\langle x \rangle| = 4$, hence, we can conclude that $G = \langle x \rangle$, which implies that $G \simeq Z_4$. Suppose that $G$ does not contain an element of order $4$, then by [[Lagrange's Theorem and Products of Groups#Lagranges Theorem|Lagrange's Theorem]], every non-identity element must have order $2$. Suppose $a, b, c$ are the non-identity element in $G$, then we have:
$$a^2 = b^2 = c^2 = e$$
Suppose FTSOC that $ab = a$, then by the Cancellation Law we have $b = e$, which is a contradiction. Likewise, if $ab = b$, right cancellation implies that $a = e$, which is also a contradiction. Hence, the only possibility is that $ab = c$. Using the same logic, we can derive that:
$$
ab = ba =  c,\;  ac = ca = b, \; bc = cb = a
$$
which shows that our group has exactly the same multiplication table as $V_4$. As a result, we have that $G \simeq V_4$.

### Classificaiton of Groups of Prime Order

>[!success] Groups of Prime Order
>Let $G$ be a finite group and suppose $|G| = p$, where $p \in \mathbb{Z}$ is a prime. Then, $G \simeq Z_p$, where $Z_p$ is the Cyclic Group of order $p$. 

**Proof**: For any $x \in G$, we must have $o(x) \mid p$ by the "Order of Elements Divide Order of Group" Proposition in [[Lagrange's Theorem and Products of Groups]]. If $x \neq e$, then $o(x) \neq 1$. This forces the order of $x$ to be $p$. Consequently, any non-identity element in $G$ has order $p$, which each of them is a generator for $G$. Resultingly, $G$ must be isomorphic to the cyclic group of order $p$. 

### Classification of Groups of Order 6

>[!success] Groups or Order $6$
>Every group $G$ of order $6$ is isomorphic to $Z_6$ or $S_3$. 

**Proof**: Obviously, if $G$ is cyclic, it is isomorphic to $Z_6$ (refer to [[Cyclic Groups]]). If $G$ is not cyclic, then $G$ does not contain an element of order $6$. By [[Theorem of Cauchy|Cauchy's Theorem]], $G$ has an element $a$ of order $2$ and an element $b$ of order $3$. Using these two elements, we can see that the following $6$ elements:
$$
\{ e, b, b^2, a, ab, ab^2 \}
$$
are all distinct elements in $G$. As $G$ has order $6$, this must be **all** elements in $G$ and $a, b$ are the generators of $G$. Consider the subgroup $H - \langle a \rangle$ of order $2$. Notice that $a^{-1}aa = a \in H$ but $b^{-1}ab = ab^2 \not \in H$. Hence, $H$ is a non-normal subgroup of $G$. Let $\bar{H}$ be the set of cosets of $H$ and let $G$ act on $\bar{H}$ by [[Action by Left Multiplication -- Cayley's Theorem|Left Multiplication]], then the permutation representation $\pi_H$ of this action is an injective homomorphism from $G$ to $S_3$ (by Lagrange, $|\bar{H}| = 3$). Furthermore, as $|G| = |S_3| = 6$, $\pi_H$ must be an isomorphism. We can hence conclude that if $G$ is not cyclic, then $G \simeq S_3$, completing the classification.  

### Clasification of Groups of Order $2p$

ss

