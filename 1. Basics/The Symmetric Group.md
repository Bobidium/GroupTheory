---
tags:
  - Example
aliases:
  - "[[Definition and Elementary Properties of Groups]]"
---
### Definitions

The Symmetric Group can be seen as a generalization of the [[The Dihedral Group|Dihedral Group]]. It is defined as follows: 

>[!definition] Symmetric Group
>For a non-empty set $\Omega$, let $S_{\Omega}$ be the set of all bijections $\sigma: \Omega \to \Omega$. The *Symmetric Group on $\Omega$* is the set $S_{\Omega}$ under the operation of **function composition**. 

>[!warning] Remark
>When $\Omega = \{ 1, 2, ..., n \}$, $S_{\Omega}$ is simply denoted as $S_n$. This Group is called the *Symmetric Group on $n$ letters* or *Symmetric Group of order $n$*. 

$S_n$ is of great interest to us because it is a direct example linking the concept of groups and "symmetries" (permutations of a finite set). 

We shall introduce a new notation to represent the elements in $S_n$: 

>[!definition] Cycle Notation
>We use the notation $(a_1, a_2, ..., a_k)$ to denote the permutation $\sigma \in S_n$ such that $\sigma(a_i) = a_{i+1}$ if $i < k$ and $\sigma(a_k) = a_1$. 

Permutations that can be represented as $(a_1, ... a_k)$ are called *cycles*. A cycle that involves $k$ elements (with length $k$) is called a *$k$-cycle*. 

>[!warning] Note
>All cycles of length $1$ are ommitted in the decomposition. 

### Properties of $S_n$

We shall first look at the order of $S_n$: 

>[!success] Order of $S_n$
>The order of $S_n$ is $n!$. 

**Proof**: 
The elements of $S_n$ are simply all the bijections from $\{1, 2, ... n\}$ to itself. Consider the possibilities that $1$ can be mapped to: there are $n$ possibilities as $1$ can be mapped to any element in the set. Now suppose we have determined where $1$ is mapped to, $2$ can only be mapped to $n-1$ possible elements to ensure injectivity. Likewise, there are $n-2$ possibilities for $3$, $n-3$ possibilities for $4$... 
Applying the Muliplication law would give us the result that there are in total $n!$ permutaitons of the $n$ elements, which shows that:
$$
|S_n| = n!
$$

Another crucial result about the elements of $S_n$ is that each can be written as a combination of **disjoint cycles** of the following form:
$$
(a_1, a_2, ... a_{m_1})(a_{m_1 + 1}, ... a_{m_2}) ... (a_{m_{k-1}+1}, ..., a_{m_k})
$$
where $a_i \neq a_j$ whenever $i \neq j$. The benefit of doing so is that
* We can freely **commute** the cycles themselves as each cycle only permutes elements in disjoint sets. 
* We can easily find out the **inverse** of a particular permutation -- this is done simply by **reversing the order** of the elements in each cycle. For instance, the inverse of the permutation shown above is: 
	$$
	(a_{m_1}, ... a_2, a_1)(a_{m_2}, ... a_{m_1+2}, a_{m_1+1}) ... (a_{m_k}, ..., a_{m_{k-1}+2}, a_{m_{k-1}+1})
	$$

Notice that when written in cycle notation, the permutation:
$$
(a_1, a_2, ..., a_n)
$$
is not only an element of $S_n$. It is also an element of $S_k$ for all $k \geq n$ as it represents the permutation that only permutes the element $\{a_1, ..,, a_n\}$ while **fixing** all of $\{ a_{n+1}, ..., a_k \}$. Using this idea, we can prove that: 

>[!success] $S_n$ as non-abelian groups
>$S_n$ is **not [[Definition and Elementary Properties of Groups#Relevent Definitions|abelian]]** for all $n \geq 3$. 

**Proof**: Notice that: 
$$
(12)(13) = (132) \neq (123) = (13)(12)
$$
As $(12),(13)$ are both elements in $S_n$ for all $n \geq 3$, $S_n$ cannot be abelian whenever $n \geq 3$. 

### Order of Elements in $S_n$

The main aim of this section is to prove that the [[Definition and Elementary Properties of Groups#Relevent Definitions|order]] of any element in $S_n$ is the **Least Common Multiple** of the lengths of its cycles when written in disjoint cycle decomposition. We first have the following lemma: 

>[!success] Order of an $m$-cycle
>Suppose $\sigma = (a_1, a_2, ..., a_m)$, then $o(\sigma) = m$. 

**Proof**: Consider the permutation $\sigma^i$. For any $a_k$, it is easy to see that $\sigma^i(a_k) = a_n$ where $n \equiv k+i \; (\text{mod }m)$ and $1 \leq n \leq m$ from the definition of function composition. Hence, we can see that $\sigma^m$ maps any element $a_k$ to $a_{k}$ as $k$ is the only positive integer between $1$ and $m$ such that $k \equiv k+m \; (\text{mod }m)$. Thus:
$$
\sigma^{m} = e
$$
Now, suppose $i <m$, then $\sigma^i(a_k) = a_n$ where $n \equiv k+i \; (\text{mod })m$. Assume FTSOC that $n = k$, then:
$$
k \equiv k+i \; (\text{mod }m) \implies m \mid i
$$
However, as $i < m$, this is a contradiction. Therefore, $\sigma^i(a_k) \neq a_k$, implying that $m$ is the smallest power of $\sigma$ that is equal to the identity permutation. As a result, $o(\sigma) = m$. 

>[!success] Criteria for $m$-Cycle
>If $\sigma = (1,2,.. ,m)$, then $\sigma^i$ is an $m$-cycle if and only if $(i, m)=1$. 

**Proof**: We can write $\sigma^i$ in disjoint cycle decomposition and consider the cycle that contains $1$. Suppose this cycle is of the form: $(1, 1+i, 1+2i, ... 1+(k-1)i)$, then it suffices to show that $k = m$ if and only if $(i, m) = 1$. From the previous proposition, we can deduce that
$$
ki \equiv 0 \; (\text{mod m}) \iff m \mid ki
$$
Suppose $(i, m) = 1$, then from Number Theory, we know that $m \mid k$, so $k \geq m$. On the other hand, $k \leq m$ as there are only $m$ elements that are being permuted. Thus, $k = m$, completing the proof in the backwards direction. If $(i, m) =d > 1$, then $k = m/d$ < m , which shows that the cycle containing $1$ is a cycle with length $m/d$. Thus, $\sigma^i$ is not an $m$-cycle. In fact, in this case, $\sigma^i$ can be  written as $d$ disjoint cycles of length $m/d$. 

>[!success] Order of elements in $S_n$
>The order of any element in $S_n$ equals the least common multiple of the orders of the cycles in its disjoint cycle decomposition. 

**Proof**: Take any permutation $\sigma \in S_n$. Then $\sigma$ can be written as:
$$
\sigma = (a_1, a_2, ... a_{m_1})(a_{m_1 + 1}, ... a_{m_2}) ... (a_{m_{k-1}+1}, ..., a_{m_k})
$$
Since these disjoint cycles permute, we further have that:
$$
\sigma^i = (a_1, a_2, ... a_{m_1})^i(a_{m_1 + 1}, ... a_{m_2})^i ... (a_{m_{k-1}+1}, ..., a_{m_k})^i
$$
Suppose $o(\sigma) = n$, then as the cycles shown above are all disjoint, we must have that each cycle to the power of $n$ is the identity permutation: 
$$
(a_1, a_2, ... , a_{m_1})^n = e,\; (a_{m_1 + 1}, ... a_{m_2})^n = e\; ...\;  (a_{m_{k-1}+1}, ..., a_{m_k})^n = e
$$
As the order of an $m$ cycle is simply $m$, we may further deduce that:
$$
m_1 \mid n, \; m_2 \mid n, \; ..., \; m_k \mid n
$$
By the minimality of the order, we can conclude that:
$$
n = \text{lcm}(m_1, m_2, ..., m_k)
$$
which is the desired result. 

As an interesting Corollary, we have the following result: 

>[!important] Corollary
>Let $p$ be a prime. Then an element in $S_n$ has order $p$ if and only its disjoint cycle decomposition consists of commuting cycles of length $p$. 

**Proof**: Suppose the cycles in the decomposition have lengths $m_1, m_2, ... m_k$, then:
$$
p = \text{lcm}(m_1, m_2, ..., m_k) \implies m_1 \mid p,\;  m_2 \mid p, ..., \; m_k \mid p
$$
As all cycles of length $1$ are omitted in the cycle decomposition, we must have:
$$
m_1 = m_2 = ... = m_k = p
$$
which completes the proof. 