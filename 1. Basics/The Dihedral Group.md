---
tags:
  - Example
aliases:
  - "[[Definition and Elementary Properties of Groups]]"
---
### Introduction

The Dihedral is our first example that links the abstract concept of [[Definition and Elementary Properties of Groups |groups]] to symmetries. 

>[!Definition] Symmetry of an $n$-gon
>A *Symmetry* of a regular $n$-gon refers to a rigid transformation such that the copy of the $n$-gon after the transformation covers exactly the original $n$-gon. 

>[!Definition] Dihedral Group $D_{2n}$
>The *Dihedral Group* $D_{2n}$ is the set of all Symmetries of a regular $n$-gon, equipped with compositions of symmetries as its operation. 

Notice that $D_{2n}$ is a group because:
* Composition of symmetries is associative
* The Rotation by $2\pi$ is the identity element
* Every rigid transformation has a unique inverse transformation. 
* And obviously... the composition of any two symmetries is still a symmetry. 

>[!success] Order of the Dihedral Group
>The order of $D_{2n}$ is $2n$. 

**Proof**: We shall label the vertices of the $n$-gon with the $\{1, 2, ..., n\}$ clockwise starting from a chosen vertex. Suppose a symmetry of the $n$-gon sends vertex $1$ to the position of vertex $i$, then consequently, vertex $2$ will be sent to either vertex $i+1$ or $i-1$. We can show that both cases are possible since if vertex $2$ is mapped to one of $i+1$ and $i-1$, we can simply perform a reflection across the line of symmetry passing through vertex $i$ to send it to the other vertex. Hence, there are $n$ choices of positions for vertex $1$, and only $2$ choices for vertex $2$. Once the positions of vertices $1$ and $2$ have been decided, it follows that the positions of the rest of the vertices are determined. Hence, in total, there are $2 \cdot n$ possible symmetries and consequently:
$$
|D_{2n}| = 2n
$$
>[!warning] Note
>The key idea in this proof is that the position of **all the vertices are determined once the positions of vertices $1$ and $2$ are determined**. We will see this idea again in later proofs. 

### Properties of $D_{2n}$

For an $n$-gon, its Dihdral Group consists of all **clockwise rotations** by an angle of $2k\pi/n$ for $k \in \{ 1, 2, ..., n \}$, and all **reflections** across the axes of symmetries. In general, we denote the rotation by an angle of $2\pi/n$ by the letter $r$ and a reflection across the line passing through a fixed vertex (we call it vertex $1$) as $s$. 

>[!success] Elements of $D_{2n}$
>Every element of $D_{2n}$ can be expressed uniquely as $s^k r^i$ for some $k, i \in \mathbb{Z}$. More specifically: 
>$$
>D_{2n} = \{  r, r^2, r^3, ..., r^n , s, sr, sr^2, ..., sr^{n-1}\}
>$$

**Proof**: Notice that $\{r, r^2, ..., r^n\}$ are all distinct and $r^n$ is the identity, we shall denote this symmetry as $e$. Hence, for a rotation by an angle of $2k\pi/n$, which is denoted as $r^k$, we can perform division algorithm of $k$ and $n$ to see that there exists $q, m \in \mathbb{Z}$ such that 
$$
k = qn + m
$$
and $0 \leq m <n$. Consequently: 
$$
r^k = r^{qn+r} = (r^n)^q (r^m) = e(r^m) =r^m \in \{ r, r^2, ..., r^n\} 
$$
so the rotational symmetries are exactly $\{r, r^2, ..., r^n\}$. Furthermore, we can see that all reflectional symmetries are compositions of a rotational symmetry followed by the reflection $s$, so the reflectional symmetries are exactly $\{ s, sr, sr^2, ..., sr^{n-1} \}$. We can easily verify that $sr^i \neq sr^j$ if $i \neq j$ as $s^2 = e$ and consequently if $sr^i = sr^j$:
$$
s(sr^i) = s(sr^j) \implies (s^2)r^i = (s^2)r^j \implies r^i = r^j
$$
which is a contradiction. 

>[!success] Commuting Multiplication
>For any $k \in \mathbb{N}$:
>$$
>\boxed{r^is = sr^{-i}}
>$$

**Proof**: We proceed with proof by Induction. In the base case, we want to show that:
$$
rs = sr^{-1}
$$
We shall consider the position of vertices $1$ and $2$ after these two transformations. The symmetry $rs$ maps vertex $1$ to position 2 and vertex $2$ to position $1$. On the other hand, the symmetry $sr^{-1}$ also maps vertex $1$ to position $2$ and vertex $2$ to position $1$. As the positions of these two vertices uniquely determines the symmetry, we may conclude that $rs = sr^{-1}$. 

For the inductive step, suppose we have $r^ns = sr^{-n}$, then:
$$
\begin{align}
	r^{n+1}s &= r(r^ns)\\
	&= r(sr^{-n}) \\
	&= (rs)r^{-n} \\
	&= sr^{-1}r^{-n} \\
	&= sr^{-(n+1)}
\end{align}
$$
Thus, by the Principle of Mathematical Induction, we have the desired result. 

>[!warning] Remark
>As a result of this, $D_{2n}$ is not [[Definition and Elementary Properties of Groups#Relevent Definitions|abelian]] when $n \geq 3$ (as in this case $r^i \neq r^{-i}$). 
>

### Generator and Presentation of $D_{2n}$

>[!definition] Set of Generators
> A *set of generators* of a group $G$ is a subset $S$ of $G$ with the property that any element in $G$ can be expressed as a finite product of the elements in $S$. We may represent this as:
>$$
> G = \langle S \rangle
>$$

With the above discussions, we can easily see that $\{r, s\}$ is a set of generators for $D_{2n}$, in other words:
$$
D_{2n} = \langle r, s \rangle
$$
However, we need extra information about $r$ and $s$ to be able to recreate $D_{2n}$ completely from the generator set. These extra conditions are called the *relations* in $G$. For $D_{2n}$ the relations are exactly:
* $r^n = e$
* $s^2 = e$
* $r^n s = sr^{-n}$

Using the above observations, we can represent $D_{2n}$ as the following:
$$
D_{2n} = \langle r, s | r^n = s^2 = e, \; r^ns = sr^{-n} \rangle
$$
This is called the *Presentation* of the Dihedral Group. In general, the presentation of a group $G$ consists of its generators along with the relations that define the group. 