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

haha