# Bisimulation:

## Motivation
Allows for us to describe the behaviour of processes
and compare them. Given 2 processes are their
behaviors equivalent?
>todo more

## Definition
We define a relation R between 2 processes to be a 
**Strong bisimilation**,
if $$(S, T) \in R\\
\text{Then}~~~\forall \alpha \in {Act}\\
if S\xrightarrow{\alpha}S' \\
\text{then}~~~T\xrightarrow{\alpha}T'~~~\\
\text{st.} (S', T') \in R$$
and vice-versa. 

---

This relation ~ is an equivalence relation, 
meaning that 
- ~ is symmetric, $(x,x) \in$ ~
- ~ is Reflexive, $(x,y) \in$ ~ $\implies (y, x) \in $ ~
- ~ is Transitive, ${(x, y), (y,z)} \subset ~ \implies (x, z) \in$ ~

** Weak Bisim ** 
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
> Todo: