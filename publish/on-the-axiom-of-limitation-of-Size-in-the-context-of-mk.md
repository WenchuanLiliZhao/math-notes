# Something About the Axiom of Limitation of Size in the Context of MK

> [!summary]
> 
> This article introduces a possible motivation for the proposal of the axiom of the limitation of size, mainly in the context of Morse-Kelley set theory (MK). The article also discusses the corollaries that follow from the axiom and compares their dependencies.

Now, let's pretend we don't know the axiom of limitation of size yet.
## How large is "arbitrarily large"?

There is an intuitive way to distinguish if a class is a proper class or a set: If a class is too large, or "arbitrarily large", in size, then it must be a proper class.

But, how large is "arbitrarily large"? In a sense, a class $A$ is said to be arbitrarily large if its size is unlimited. More precisely, $A$ is arbitrarily large if $|B| \le |A|$ whereas $B$ is a class.

Take the universe, $\mathscr U$, for example. $\mathscr U$ contains all object called sets in MK; i.e.,
$$
\forall x\; (M(x) \iff x \in \mathscr U),
$$
where $M(x)$ means "$x$ is a set" or, equivalently, "$x$ is an element"; i.e.,
$$
\forall x\; (M(x) \iff \exists C\; (x \in C)).
$$
So, every class $A$ is a subclass of $\mathscr U$, and, thereby, $|A| \le |\mathscr U|$. Thus, $\mathscr U$ is unlimited in MK. In other words, the **limitation of size**, in the context of MK, is the size of $\mathscr U$. So, $\mathscr U$ must be arbitrarily large, as no class can be larger than it. So, $\mathscr U$ is a proper class in this sense.

How about a seemingly smaller class, say,
$$
X = \{ x \in \mathscr U : |x| = 1 \},
$$
namely, the class of all singletons in the universe?

> [!note]
> 
> Note that, if $X$ is a set, then, by the axiom of union, $\mathscr U = \bigcup X$ must be a set. But, $\mathscr U$ must be a proper class, otherwise, $\mathscr U \in \mathscr U$ contradicts the axiom of foundation.

Let $f: \mathscr U \to X$ be defined as $f(x):= \{x\}$, then $f$ is an bijection. Eventually, we have $|\mathscr U| = |X|$.

On the other hand, sometimes, sets are also called **small classes**, because their sizes are *believed to be* limited; namely, we can hardly find a set, $S$, satisfying $|S| = |\mathcal P(S)|$. For example, $|\mathbb N| < |\mathcal P(\mathbb N)|$. But, this is unprovable in the absence of some necessary axioms,

> [!note]
> 
> By Hartogs's Lemma, for any $S$, there is an ordinal $\alpha$ satisfying $|S| < |\alpha|$. But, this has to be proved by invoking the schema of specification, which is a corollary of the axiom of limitation of size.
> 
> So, since we are talking about the motivation of the axiom of limitation of size, we can only believe (but not prove) it is true the sizes of sets are limited.

So, there is a big "gap" between "small" and "arbitrarily large". However, John von Neumann believed there is a clear boundary in this gap, and proposed the axiom of limitation of size in 1925 as an NBG-axiom, and was subsequently included in MK. This axiom states that a class $A$ is a proper class if and only if there is a function $f: \mathscr U \to A$ being injective. In formal language, that is,

$$
\forall A \left(
\neg M(A) \iff \exists f \forall x
\left(
\begin{aligned}
& (M(x) \implies \exists y(y \in A \land (x,y) \in f)) \land \\
&\forall s \forall z (((x,z) \in f \land (s,z) \in f) \implies x = s)
\end{aligned}
\right)
\right).
$$

The function, $f$, is unnecessary to be a bijective. As $A \subseteq \mathscr U$, certainly we have $|A| \le |\mathscr U|$; so, as $|\mathscr U| \le |A|$ is stated in the axiom, we have $|A| = |\mathscr U|$, by Schröder-Bernstein theorem (no matter if this theorem is guaranteed by the axiom of limitation of size or not).

## Corollaries of the axiom of limitation of size.

### The schema of specification

The schema of specification, which is accepted as an axiom in ZFC, can be a straight corollary following the axiom of limitation of size. 

In the language of MK, the schema of specification can be re-expressed as: each subclass of a set is a set. As the axiom of limitation of size derives the definition of proper classes in terms of cardinality, then sets can be defined as the classes which are not proper classes, as the axiom of infinite guaranteed the existence of sets.

### The axiom of (global) choice and the (global) well-ordering theorem

Another two important propositions in ZFC can also be proved by the axiom of limitation of size: the axiom of choice and the axiom of the well-ordering theorem. But, more than that, the axiom of limitation of size implies the axiom of global choice and the global well-ordering theorem, from which the two ZFC-propositions can be derived respectively.

#### The axiom of (global) choice

First, let's see how the axiom of limitation of size derives the axiom of global choice, which states that there is a function $f: \mathscr U \setminus \{\emptyset\} \to \bigcup (\mathscr U \setminus \{\emptyset\})$ satisfying
$$
\forall x\; (x \in \mathscr U \setminus \{\emptyset\} \implies f(x) \in x).
$$
By Hartogs's Lemma, for every non-empty set $x$, there is an ordinal number $\alpha$ such that $|x| < |\alpha|$, and thereby $x$ can be well-ordered. Thus, for any $x \in \mathscr U$, $\max(x) \in x$. Now, let $f:\mathscr U \setminus \{\emptyset\} \to \bigcup (\mathscr U \setminus \{\emptyset\})$ be defined as
$$
f(x) = \max(x),
$$
then, we have $f(x) \in x$ where as $x$ is non-empty set. Thus, proof of the axiom of global choice is done.

As to the usual axiom of choice, note that, in the proof above, if $S$ is a set with $\emptyset \notin S$, then the restriction $f \restriction_{S}$ is the choice function of $S$.

#### The (global) well-ordering theorem

The global well-ordering theorem states that $\mathscr U$ can be well-ordered.

As the class of all ordinal numbers, $\mathscr O$, is a proper class, then, by the axiom of limitation of size and Schröder-Bernstein theorem, there is an $f: \mathscr U \to \mathscr O$ being bijective. As $\mathscr O$ is strictly well-ordered by $\in_=$, we define $\preceq$ as, for any sets $x$ and $y$,
$$
x \preceq y \iff f^{-1}(x) \in_= f^{-1}(y),
$$
then $\mathscr U$ is thereby well-ordered by $\preceq$. Thus, the global well-ordering theorem is proved.

Since each subclass of a well-ordered class and every set is a subclass of $\mathscr U$, every set can be well-ordered.

#### The axiom of global choice is equivalent to the global well-ordering theorem



#### The axiom of choice is equivalent to the well-ordering theorem





(proved by the axiom) For example, $\mathscr U^\mathscr U$ is seemingly a larger class than $\mathscr U$, but, as each $f \in \mathscr U^\mathscr U$ is a function $\mathscr U \to \mathscr U$, 


## Dependencies of the corollaries of the axiom of limitation of size

$$
\text{LOS} \left\{
\begin{matrix}
\implies &\text{AGC} &\implies &\text{AC} \\
&\Updownarrow & &\Updownarrow \\
\implies &\text{GWO} &\implies &\text{WO} \\
\\
\implies &\text{SS}
\end{matrix}
\right.
$$
In this diagram:
1. LOC is the axiom of limitation of size;
2. AGC is the axiom of global choice;
3. AC is the axiom of choice;
4. GWO is the global well-ordering theorem;
5. WO is the well-ordering theorem;
6. SS is the schema of pacification.

In this diagram, we can see that the truth value of the schema of specification is irrelevant to the truth values of the axiom of choice and the axiom of global choice. So, even if the axiom of choice is false, which implies the axiom of the limitation of size is false, the schema of specification can still be true, as it cannot drives any other proposition in the diagram.


## The axiom of union and the axiom of limitation of size

