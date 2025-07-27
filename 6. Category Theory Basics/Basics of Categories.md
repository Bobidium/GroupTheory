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

>[!example] Category on a Single Group (?)
>Let $G$ be a group. We attempt to construct a category on $G$ by taking: 
>1. The objects to be all elements of $G$
>2. The morphisms to be also the **elements** of $G$. In particular, $\text{Hom}(a, b) = \{ab\}$, the product of $a$ and $b$ in $G$ if. 
>
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

>[!example] $\mathcal{C}_{A, B}$
>Let $\mathcal{C}$ be a category and $A, B$ be fixed objects of $C$. We now construct a category $\mathcal{C}_{A, B}$ by taking the objects to be commutative diagrams of the form: 
>   
>![[Pasted image 20250717140404.png| center | 200]]
>where $Z$ is an object of $\mathcal{C}$ and $f, g$ are morphisms in $\mathcal{C}$ and the morphisms between diagrams: 
>
>![[Pasted image 20250717140643.png| center | 400]]
>to be all commutative diagrams: 
>
>![[Pasted image 20250717140758.png| center | 300 ]]
>
>The Composition will be defined as:
>
>![[db9be4909d794858a63faddaf7452b5.jpg| center | 400]] 
>
>The identity and the verification of associativity will be left to the reader as an exercise...

This category will play an important role later when we consider the [[Universal Properties, Products, Coproducts, and Free Objects|universal property of products]]
and coproducts. 

### Identity and Inverses

In this section, we first show that the identity on any object $A$ of a category $\mathcal{C}$ must be unique. 

>[!success] Uniqueness of Identity
>Let $\mathcal{C}$ be a category and for any object $A$ of $\mathcal{C}$, the identity morphism $I_A$ is unique. 

**Proof**: The proof will be very similar to the [[Definition and Elementary Properties of Groups#Elementary Properties|proof for the uniqueness of the identity in a group]]. Suppose that $I_A'$ is another identity morphism on $A$, then for any morphism $f: A \to B$ and $g: C \to A$, we have $f \circ I_A' = f. I_A' \circ g = g$. By taking $f = I_A$ we have: 
$$
I_A = I_AI_A' = I_A'
$$
which completes the proof of uniqueness. 

In the category $\text{Set}$, some morphisms, i.e. functions, are bijective and thus have inverses. In the categories $\text{Grp}$ and $\text{Ab}$, the isomorphisms are the morphisms with an inverse. We can thus extend this notion of "invertible morphisms" onto an arbitrary category: 

>[!d] Equivalence
>In a category $\mathcal{C}$, a morphism $f: A \to B$ is called an *equivalence* if there exists a morphism $g : B \to A$ such that:
>$$
>g \circ f = I_A, \; \; \; \; \; f \circ g = I_B
>$$
>In this case, $g$ is called the *inverse* of $f$. If there exists an equivalence between $A$ and $B$, then $A$ and $B$ are said to be *equivalent*. 

As we migh expect, given any equivalence in a category, the inverse is unique: 

>[!success] Uniqueness of Inverse
>Let $f: A \to B$ be an equivalence in a category $\mathcal{C}$. If $g, g'$ are both inverses of $f$, then $g = g'. 

**Proof**: Again, notice the great similarity between this proof and the  [[Definition and Elementary Properties of Groups#Elementary Properties|proof for the uniqueness of the inverse in a group]]. Notice that: 
$$
g = g \circ I_B = g \circ (f \circ g') = (g \circ f) \circ g' = I_A \circ g' = g'
$$
which proves the uniqueness of the identity. 

--------------------------------------------------------------------------

**Answer**: Why isn't the attempted definition of a category on a single group fail? As we have verified, the construction does satisfy most of the defining properties of a category, except one. Recall that when $a \neq c, b \neq d$, we need $\text{Hom}(a,b)$ and $\text{Hom}(c, d)$ to be disjoint. This is not the case in our construction since the morphism $e$ is in $\text{Hom}(a, a^{-1})$ for all $a \in G$. 

Following up from our failed attempt, we may ask whether there IS a way to realize a single group $G$ as a category. The answer is yes by considering the category whose object(s) is the single element $G$, the morphisms in $\text{Hom}(G, G)$ are precisely all elements of $G$, and the composition of morphisms $a$ and $b$ is given by the product $ab$. Consequently, $e$ is the identity morphism and associativity follows directly from associativity in $G$. In this sense, we may say that a group can be considered as a **category with one object**.  