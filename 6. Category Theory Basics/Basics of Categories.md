---
aliases:
  - "[[Definition and Elementary Properties of Groups]]"
  - "[[Homomorphisms and Isomorphisms]]"
---
### Definition of Categories

In our study of groups, we find that there is really two things of interest: the groups themselves, and the homomorphisms between groups. One of the main tasks of group theory is to determine the **internal structures** of each group, their subgroups, quotient groups etc. , and to characterize all groups up to [[Homomorphisms and Isomorphisms|isomorphisms]], i.e. we look at which groups are "essentially the same" with each other using homomorphisms. 

These two critical aspects, upon further abstraction, become the two defining aspects of a *category*: the *Objects*, and the *Morphisms* between objects. Studying categories in general gives us a higher perspective on the structure of groups in general, and is of large importance in the study of [[Free Groups and Presentation of Groups|Free Groups]]. 

>[!d] Category
>A *category* $\mathcal{C}$ consists of: 
>1. A class of **objects**, denoted as $\text{Ob}(\mathcal{C})$
>2. For each ordered pair (not necessarily distinct) of objects $A, B$, a set of morphisms, denoted as $\text{Hom}(A, B)$. Each element $f$ is called a **morphism** from $A$ to $B$ and is denoted $f: A \to B$. 
>3. For each triple of objects $(A, B, C)$, a function
>$$
>\text{Hom}(A, B) \times  \text{Hom}(B,C) \to \text{Hom}(A, C)
>$$
>In particular, for morphisms $f : A \to B$ and $g B \to C$, the function maps $(f, g)$ to $g \circ f$. The image $g \circ f$ is called the **composition** of $f$ and $g$. The composition follows the following two rules: 
>a. (Associativity) For morphisms $f : A \to B, g: B \to C, h: C \to D$, we have: 
>$$
>(h \circ g) \circ f = h \circ (g \circ f)
>$$
>b. (Identity) For each object $B$ of $\mathcal{C}$, there exists a morphism $I_B : B \to B$ such that for any morphisms $f: A \to B$, $g: C \to B$: 
>$$
>I_B \circ f = f,\; \; \; \; \;  g \circ I_B = g
>$$

A few remarks are worth mentions

>[!warning] Remark
>1. The objects form a *class*, which is wider than the notion of sets precisely because we need the class of all sets to be a category (see below). There is no "set" of all sets, as this would cause Russel's paradox. The same problem does not occur with the maps between sets: the collection of all possible maps from a set A to $B$ DOES form a set, for reasons beyond the scope of group theory. Thus, we may restrict $\text{Hom}(A, B)$ to a set. 
>2. There is in fact a further requirement for morphisms: If $A \neq C$, $B \neq D$ are objects of the category $\mathcal{C}$. then:
>	$$
>	\text{Hom}(A, B) \cap \text{Hom}(C, D) = \emptyset
>	$$
>	meaning that $\text{Hom}(A, B)$ and $\text{Hom}(C, D)$ are disjoint sets. But since this often true trivially, we don't usually pay much attention to this property lol. 
>3. The identity $I_A$ for some object $A$ is unique, as we shall prove in [[Basics of Categories#Identity and Inverses]]


### Examples of Categories


### Identity and Inverses



