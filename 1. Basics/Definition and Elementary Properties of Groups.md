---
tags:
  - Theory
---
### Definition of Groups

Groups are abstractions of Symmetries. In fact, Groups **are** symmetries. We shall begin with the definition of groups: 

>[!definition] Groups
>A group is an ordered pair consisting of a set $G$ and a binary operation $\cdot$ defined on $G$ that satisfies:
>1. (*Associativity*) For all $a, b \in G$, $(a \cdot b )\cdot c = a \cdot (b \cdot c)$. 
>2. (*Identity*) There exists $e \in G$ such that for all $a \in G$, $e \cdot a = a \cdot e = a$. 
>3. (*Inverse*) For any $a \in G$, there exists $a^{-1} \in G$ such that $a\cdot a^{-1} = a^{-1} \cdot a = e$. 

>[!warning] Note
>We will be omitting the repeated use of $\cdot$ by writing $a \cdot b$ as $ab$. 

It is important to remember that it is not sufficient to regard a group simply by its set $G$, we also neeed to specify the operation on the set. The following are all examples of groups: 

>[!example] Example of Groups
>* $(\mathbb{Z}, +)$ is a group, but $(\mathbb{Z}, \times)$ is not a group as $2$ doesn't have a multiplicative inverse in $\mathbb{Z}$. 
>* $(\mathbb{Z} / n\mathbb{Z}, +)$ is always a group, but $(\mathbb{Z} / n\mathbb{Z, \cdot})$ is a group if and only if $n$ is a prime. The group $(\mathbb{Z} / n\mathbb{Z}, \cdot)$ is usually denoted as $\mathbb{Z} / n\mathbb{Z}^{\times}$. 
>* The set of all symmetries of a regular $n$-gon equipped with composition operation is a group. (This is called the *[[The Dihedral Group |Dihedral Group]]* of order $2n$)

### Elementary Properties

We can already derive some simple propositions using only the definitions of groups.

>[!success] Uniqueness of the Identity
>For any Group $G$, the identity is unique. 

**Proof**: Suppose there exists two identity elements $e_1$ and $e_2$ in $G$, then by definition:
$$
\begin{align}
	e_1 &= e_1e_2 \\
		&= e_2e_! \\ 
		&= e_2
\end{align}
$$
Hence, the two identity elements must be equal and we are done. 

>[!success] Propositions about the inverse
>For any Group $G$ and any $a, b \in G$: 
>1. The inverse of $a$ is unique and is denoted as $a^{-1}$. 
>2. $(ab)^{-1} = b^{-1}a^{-1}$
>3. $(a^{-1})^{-1} = a$

**Proof**: 
1. For any $a \in G$, suppose $a$ has two inverses $b$ and $b'$, then:
	$$
	\begin{align}
		b &= b(ab') \\
		&- (ba)b' \\
		&= b'
	\end{align}
	$$
	so the two inverses must be equal, completing the proof for uniqueness. 
2. Suppose that $(ab)^{-1} = c$, then we have:
	$$
	c(ab) = (ab)c = e
	$$
	Multiplying $b^{-1}$ on both sides aims:
	$$
		ca = eb^{-1} = b^{-1}
	$$
	Then, we can multiply $a^{-1}$ on both sidse:
	$$
	c = b^{-1}a^{-1}
	$$
	which is the desired result. 
3. Notice that: 
	$$
		(a^{-1})a = a(a^{-1}) = e
	$$
	By definition of the inverse, $(a^{-1})^{-1} = e$. 


Another very useful property of groups is **cancellation**, as illustrated in the following proposition. 

>[!success] Cancellation Laws
>Let $a, b, u, v \in G$, then:
>1. (*Left Cancellation*) If $au = av$, then $u = v$. 
>2. (*Right Cancellation*) If $ub = vb$, then $u = v$. 

**Proof**: The proof is trivial. If $au = av$, multiplying by $a^{-1}$ on both sides gives:
$$
	au = av \implies a^{-1}au = a^{-1}av \implies u = v

$$
The proof for Right Cancellation is analogous. 

>[!warning] Remark
>A corollary to the cancellation law is the follows: If an element $b$ satisfies that for all $a \in G$, $ab = a$ (or $ba = a$), then $b = e$. This shows that $b$ is the identity if and only if it is a **one sided identity**. A similar result holds for inverses. 
>
### Relevent Definitions

Here, we include some other important definitions related to groups. 

>[!definition] Abelian Groups
>A group $G$ is *Abelian* if and only if for all $a, b \in G$, $ab = ba$. In other words, multiplication is **commutative** in an abelian group.  

>[!definition] Powers in a Group
>For any $n \in \mathbb{N}$, and $x \in G$, $x^n = \underbrace{x \cdot x ... \cdot x}_{\text{n terms}}$, and $x^{-n} = \underbrace{x^{-1} \cdot x^{-1} ... \cdot x^{-1}}_{\text{n terms}}$. If $n =0$, then $x^n = e$. 
>

Next, we shall define the order of an **element** in a group, and the order of the group itself separately: 

>[!definition] Order of an Element
>For a group $G$ and an element $x \in G$, the *order* of $x$, denoted as $o(x)$ is defined to the **smallest** positive integer $n$ such that $x^n = e$. If not such $n$ exists, then $o(x) = \infty$. 

>[!definition] Order of a Group
>The *order* of a Group $G$ is defined to be the Cardinality of $G$ and is denoted as $|G|$. We say that $G$ is a finite Group if $|G|$ is finite and infinite if otherwise. 

As an interesting exercise, we have the following proposition:

>[!success] Groups of Order $2$ Elements are Abelian
>Let $G$ be a group and suppose for all $g =\in G$, $o(g) = 2$, then  $G$ is Abelian. 

**Proof**: Let $x, y\in G$, then $x^2 = y^2 = e$, implying that $x^{-1} = x$ and $y^{-1} = y$. Consequently, consider the inverse $(xy)^{-1}$, we have the following:
$$
xy = (xy)^{-1} = y^{-1}x^{-1} = yx
$$
Hence, $G$ is Abelian. 

This method of using the inverse of a product to prove a commutativity property is used gain in [[Lagrange's Theorem and Products of Groups#Products of Subgroups]]. 

### An Interesting Criterion for Groups

The following
