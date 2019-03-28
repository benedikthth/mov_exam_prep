# Bisimulation:

## Motivation
Allows for us to describe the behaviour of processes
and compare them. Given 2 processes are their
behaviors equivalent?
>todo more

## Definition
We define a relation $\mathcal{R}$ between 2 processes to be a **Strong bisimilation**,
if 

$(S, T)\in \mathcal{R}$
then for all $\alpha \in Act$
if $\exists~S'$ st. $S\xrightarrow{\alpha}S'$
then $\exists~T'$ st. $T\xrightarrow{\alpha}T'$
and that $(S', T') \in \mathcal{R}$
<!-- $$(S, T) \in \mathcal{R}\\
\text{Then}~~~\forall \alpha \in {Act}\\
if S\xrightarrow{\alpha}S' \\
\text{then}~~~T\xrightarrow{\alpha}T'~~~\\
\text{st.} (S', T') \in \mathcal{R}$$
and vice-versa.  -->

---

This relation ~ is an equivalence relation, 
meaning that 
- ~ is symmetric, $(x,x) \in$ ~
- ~ is Reflexive, $(x,y) \in$ ~ $\implies (y, x) \in $ ~
- ~ is Transitive, ${(x, y), (y,z)} \subset ~ \implies (x, z) \in$ ~

**Weak Bisimiliarity** 
Strong bisimilarity does not abstract away $\tau$ actions,
this is why we need weak bisimilarity. 

Weak bisimilarity works the exact same way, but instead of the strictly $\xrightarrow{a}$ relation, 
we allow the $$
\newcommand{\taustar}{(\xrightarrow{\tau})^{*}}
\xRightarrow{a} = \left\{
\begin{array}{l r}
\taustar\xrightarrow{\alpha}\taustar& if~\alpha \neq \tau \\
\taustar & if~\alpha = \tau \\
\end{array}
\right.$$

**it is worth noting that all strong bisimulations are also weak.**

## Example

> Here You can prove that 2 systems are, *or are not*, bisimilar.
>You should also talk about why traceEq != bisimulation
--- 
We want to prove that 

$\text{if}~S\thicksim T \rightarrow a.S \thicksim a.T$

we define a relation $\mathcal{R}=\{(a.S, a.T)|S\thicksim  T\}$
> We want to show that $\mathcal{R}$ is a strong bisimulation. 

Assume that $S \xrightarrow{a} S'$

`then by the definition of bisim.`

$\exists~T'$ st. $T \xrightarrow{a} T'$ 

`We can say that ` $S = a.S'$ and $T = a.T'$

Then by our definition of $\mathcal{R}$,
$(S, T)\in \mathcal{R}$


> `I still feel that there's something missing`

--- 

We also want to prove that 
## ???