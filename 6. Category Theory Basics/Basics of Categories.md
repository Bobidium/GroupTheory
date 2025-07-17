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
>In particular, for morphisms $f : A \to B$ and $g: B \to C$, the function maps $(f, g)$ to $g \circ f$. The image $g \circ f$ is called the **composition** of $f$ and $g$. The composition follows the following two rules: 
>a. (Associativity) For morphisms $f : A \to B, g: B \to C, h: C \to D$, we have: 
>$$
>(h \circ g) \circ f = h \circ (g \circ f)
>$$
>b. (Identity) For each object $B$ of $\mathcal{C}$, there exists a morphism $I_B : B \to B$ such that for any morphisms $f: A \to B$, $g: C \to B$: 
>$$
>I_B \circ f = f,\; \; \; \; \;  g \circ I_B = g
>$$

A few remarks are worth mentioning:

>[!warning] Remark
>1. The objects form a *class*, which is wider than the notion of sets precisely because we need the class of all sets to be a category (see below). There is no "set" of all sets, as this would cause Russel's paradox. The same problem does not occur with the maps between sets: the collection of all possible maps from a set A to $B$ DOES form a set, for reasons beyond the scope of group theory. Thus, we may restrict $\text{Hom}(A, B)$ to a set. 
>2. There is in fact a further requirement for morphisms: If $A \neq C$, $B \neq D$ are objects of the category $\mathcal{C}$. then:
>	$$
>	\text{Hom}(A, B) \cap \text{Hom}(C, D) = \emptyset
>	$$
>	meaning that $\text{Hom}(A, B)$ and $\text{Hom}(C, D)$ are disjoint sets. But since this often true trivially, we don't usually pay much attention to this property lol. 
>3. The identity $I_A$ for some object $A$ is unique, as we shall prove in [[Basics of Categories#Identity and Inverses]]


### Examples of Categories

We shall include below multiple examples of categories, from concrete, to more abstract ones. 

>[!example] Category of Sets
>In the category $\text{Set}$, the objects are sets, the morphisms are functions between sets, and the composition is the usual composition between functions. Clearly, the composition is associative, and the identity $I_A$ is the identity map on set $A$. 

>[!example] Category of Groups
>In the category $\text{Grp}$, the objects are groups, the morphisms are group homomorphisms, and the composition is the usual function compositions. This composition is well-defined as one can verify that the composition of two homomorphisms is still a homomorphism. Clearly, as homomorphisms are function, the composition is associative, and the identity morpphism is simply the identity homomorphism. 

>[!example] Category of Abelian Groups
>Notice that if we restrict to the class of abelian groups only in the example above, the definition morphisms and compositions produces another category, denoted as $\text{Ab}$. This is a category contained within the category $\text{Grp}$, and so it is a *subcategory* of $\text{Grp}$. 

The following two interesting examples are from *Algebra: Chapter 0* by Aluffi, and they illustrate categories whoses objects are not necessarily sets, and whose morphisms are not necessarily maps. 

>[!example] Order Relation without Symmetry
>Let $\sim$ be a relation on a set $S$ that is reflexive ($a \sim a$) and transitive ($a \sim b, b \sim c \implies a \sim c$). Then we can construct a category on $S$ by taking:
>1. The objects to be the **elements** of $S$
>2. The morphism to be as follows: For any $a, b \in S$, $\text{Hom}(a, b)$ is defined as
>$$
>\text{Hom}(a, b) = \begin{cases}
>\{(a, b)\} & \text{if } a \sim b \\
>\emptyset & \text{otherwise}
>\end{cases}
>$$
>
>We have to be more careful when we are trying to define composition. Let $f \in \text{Hom}(a, b), g \in \text{Hom}(b, c)$. Notice that this implies that $\text{Hom}(a, b)\neq \emptyset$ and $\text{Hom}(b, c) \neq \emptyset$, so by the definition above, $a \sim b, b \sim c$. Using transitivity of $\sim$, we have that $a \sim c$, so $\text{Hom}(a, c) = \{(a, c)\}$. Thus, we define the composition $g \circ f := (a, c)$. 
>
>We then need to verify that this composition is associative. This is relatively straight forward as: 
>$$
>[(c, d) \circ (b, c)] \circ (a, b) = (b, d) \circ (a, b) = (a, d)
>$$
>and
>$$
>(c, d) \circ [(b, c) \circ (a, b)] = (c, d) \circ (a, c) = (a, d)
>$$
>As $\sim$ is reflexive, $a \sim a$ for all $a \in S$, so $\text{Hom}(a, a) = \{(a, a)\}$, and it is easy to verify that $I_A := (a, a)$ satisfies the definition of identity since: 
>$$
>(a, b) \circ (a, a) = (a, b), \; \; \; \; \; (a, a) \circ (c, a) = (c, a)
>$$
>Thus, this does consitute a category, although in a wierd fashion. 

Notice that in this category, the objects are no longer sets, but the elements of a particular set. We might attempt to define in a similar fashion a category on each group: 

>[!example] Category on a single group (?)
>Let $G$ be a group. We attempt to construct a category on $G$ by taking: 
>1. The objects to be all elements of $G$
>2. The morphisms to be also the **elements** of $G$. In particular, $\text{Hom}(a, b) = \{ab\}$, the product of $a$ and $b$ in $G$ if. 
>We can then define the composition as follows: For $f: a \to b$ and $g : b \to c$, define: 
>$$
>g \circ f := ac
>$$
>
>This composition is associative as: for $f : a \to b, g: b \to c, h : c \to d$
>$$
>(h \circ g) \circ f = (bd) \circ (ab) = ad
>$$
>and
>$$
>h \circ (g \circ f) = (cd) \circ (ac) = ad
>$$
>In this fashion, the identity element $I_a$ is simply $a^2$ as for any $f: a \to b, g : c \to a$:
>$$
>f \circ I_a = ab \circ a^2 = ab, \; \; \; \; \; I_a \circ g = a^2 \circ ca = ca
>$$
>Is this a valid category? If not, why? Check out the end of this note for an answer. 

The next example of category from Algebra: Chapter 0 is rather abstract in the sense that its definition is dependent on an "ambient category": 

>[!example] 



### Identity and Inverses



