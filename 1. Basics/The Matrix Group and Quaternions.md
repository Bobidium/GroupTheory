---
aliases:
  - "[[Definition and Elementary Properties of Groups]]"
tags:
  - Example
---
###  The Matrix Groups

The study of matrix groups depend largely on the system in which the entries of the matrix lie in. In specific, we need the entries to be in a special algebraic structure called *fields*: 

>[!definition] Fields
>A *field* is a set $F$ equipped with two binary operations $+$ and $\cdot$ (usually called addition and multiplication) such that $(F, +)$ is an [[Definition and Elementary Properties of Groups#Relevent Definitions|abelian group]], $(F- \{0\}, \cdot)$ is an abelian group and the distributive property holds: for all $a, b, c \in F$,
>$$
>(a+b)\cdot c = a\cdot c+b \cdot c
>$$ 

>[!warning] Note
>The field structure is in a sense the **smallest** algebraic structure in which we can perform addition, multiplication, subtraction and division. 

We can now list some simple example and non-examples of fields:

>[!example] Example of Fields
>* $\mathbb{Q}, \mathbb{R}, \mathbb{C}$ are all examples of fields. 
>* $\mathbb{Z}$ is not a field as multiplicative inverses don't exist for all elements, so $\mathbb{Z} - \{0\}$ is not an abelian group under multiplciation. 
>* $\mathbb{Z} / n\mathbb{Z}$ is not generally a field, as any element $[k]$ such that $(k, n) > 1$ does not have a multiplicative inverse (a direct result from *Bezout's Lemma*). In fact, $\mathbb{Z} / n\mathbb{Z}$ is a field if and only if **$n$ is a prime $p$**. In this case, we shall denote $\mathbb{Z} / p\mathbb{Z}$ as $\mathbb{F}_p$ for simplicity. 

We can now introduce the notion of Matrix Groups. These groups are particularly important because they provide yet another way of representing **symmetries** in the form of linear transformations: 

>[!defiinition] Matrix Groups
>Given $n \in \mathbb{Z}^{+}$ and a field $F$, the *matrix group* $GL_n(F)$ (also known as the general linear group of degree $n$) is the set:
>$$
>GL_n(F) = \{ A | A \text{ is an } n \times n \text{ matrix such that } \det(A) \neq 0  \}
>$$
>equipped with matrix multiplication as its binary operation. 

As an $n \times n$ matrix is invertible if and only if its determinant is non-zero, it is also equivalent to define $GL_n(F)$ as the set of all $n \times n$ **invertible matrices** with entries in $F$. It is easy to verify that both definitions satisfy the axioms for a group. 

As some preliminary results, we shall be proving two propositions related to the order of $GL_n(F)$: 

>[!success] Upper bound for $|GL_n(F)|$
>If $|F| = q$ is finite, then:
>$$
>|GL_n(F)| < q^{n^2}
>$$

**Proof**: Denote the set of all $n \times n$ matrices with entries in $F$ as $M_n(F)$. Then as there are in total $n^2$ entries and there are $q$ possibilities for each entry, we naturally have:
$$
|M_n(F)| = q^{n^2}
$$
Consequently, as $GL_n(F) \subset M_n(F)$ by definition, we have:
$$
|GL_n(F)| \leq |M_n(F)| = q^{n^2}
$$
which is the desired result. 

After developing more tools in field theory, we will see that the exact value of $|GL_n(F)|$ when $F$ is a finite field is: 
$$
|GL_n(F)| = \prod_{k = 0}^{n-1} (q^n - q^k)
$$
Though we cannot derive this general result yet, we can deduce the exact order of $GL_2(\mathbb{F}_p)$: 

>[!success] Order of $GL_n(\mathbb{F}_p)$
>Let $p$ be a prime, then:
>$$
>|GL_2(\mathbb{F}_p)| = p^4 - p^3 - p^2 + p
>$$

**Proof**: This is simply a counting problem. We shall proceed by counting all matrices in $M_2(\mathbb{F}_p)$, then subtract the number of all singular matrices. Note that a mtrix is singular if and only if one row is a multiple of the other. We can use this fact to produce all singular matrices. The main idea is that we can choose first the two entries in the first row, then choose a scale factor of the first row to be the second row in order to produce a singular matrix. However, care must be taken when zeroes occur in rows. We split the counting into stages. Firstly, if neither entries in the first row are zero, there are $(p-1)^2$ possibilities for the first row, and for each possibility, there are $(p-1)$ non-zero multiples it. Hence, there are in total:
$$
(p-1)^3
$$
singular matrices with no zero entries. Now, suppose there is exactly $1$ zero entry in the first row, then there are $p-1$ possibilities for the other entry in the same row, and $p-1$ non-zero multiples of the row. Hence, there are exactly:
$$
2(p-1)^2
$$
singular matrices with exactly one zero in the first row. In the final case, suppose that one of the two rows have two zero entries, then consequently for the other row, any choice of entries would result in a singular matrix. Thus, there are in total:
$$
2p^2 - 1
$$
matrices with at least one all-zero row. (We subtract $1$ to include overcounting of the zero matrix). Therefore, there are in total:
$$
(p-1)^3 + 2(p-1)^2+2p^2-1 = p^3 + p^2 - p
$$
singular matrices in $M_2(\mathbb{F}_p)$. As there are in total $p^{2^2} = p^4$ matrices in $M_2(\mathbb{F}_p)$, we can conclude that:
$$
|GL_n(\mathbb{F}_p)| = p^4 - p^3 - p^2 + p
$$
which is the desired result. 

The notation of matrices actually allows us to represent many other groups more conveniently, for example the [[The Symmetric Group|Symmetric Group]] $S_n$: 

>[!example] Matric representation of $S_n$
>Consider the set of all permutation $n \times n$ matrices, they correspond exactly to the permutations of the elements in the set $\{ 1, 2, ..., n \}$. Thus, we can say that the set of all such permutations are simply a **relabelling** of the permutations in $S_n$ and the two systems are essentially the same. (They are [[Homomorphisms and Isomorphisms|Isomorphic]]) From this example, we can also see that the set of all permutation matrices form a [[Subgroups|subgroup]] of $GL_n(\mathbb{R})$. 

### The Quaternions

The *Quaternion Group* is another important example of groups that we shall frequently reference to: 

>[!definition] The Quaternion Group
>The *Quaternion Group* $Q_8$ is the set:
>$$
>\{ 1, -1, i, -i, j, -j, k, -k \}
>$$
>with the operation $\cdot$ defined by the following rules:
>$$
>\begin{gather}
>	&1 \cdot a = a \cdot 1 = a\;  (\forall\;  a \in Q_8) \\
>	&(-1) \cdot (-1) = 1, \; (-1) \cdot a = -a \;  (\forall\;  a \in Q_8)  \\
>	&i^2 = j^2 = k^2 = -1 \\
>	&i\cdot j = k, \; j \cdot i = -k \\
>	&j\cdot k = i, \; k \cdot j = -i \\
>	&k\cdot i = j, \; i \cdot k = -j \\
>\end{gather}
>$$

It is perhaps easier to write the Quaternion Group as its presentation. There are two ways of wrting this: 
1. Using three elements to generate: 
	$$
	Q_8 = \langle i, j, k: i^2 = j^2 = k^2 = ijk \rangle
	$$
	Then, consequently: 
	$$
	1 := i^4, \; -1 := i^2
	$$
2. Using two elements to generate: 
	$$
	Q_8 = \langle i, j: i^4 = 1, i^2 = j^2, j = iji \rangle
	$$

We can also use complex matrices to represent $Q_8$, more specifically (the $i$ in the matrix is the imaginary number): 
$$
i = \begin{pmatrix}
	i & 0 \\
	0 & -i
\end{pmatrix}, \; j = \begin{pmatrix}
	1 & 0 \\
	0 & -1
\end{pmatrix}, \; k = \begin{pmatrix}
	i & 0 \\
	0 & i
\end{pmatrix}
$$
It is easy to verify that the group generated by these three matrices is a subgroup of the [[The Matrix Group and Quaternions#The Matrix Groups|matrix group]] $GL_2(\mathbb{C})$ and it is "isomorphic" to the Quaternion Group $Q_8$. 