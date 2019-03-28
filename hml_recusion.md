# Henessy milner logic with recursion
 
## Motivation

Normal Henessy Milner logic cannot express infinite 
LTS. There are temporal properties that we cannot
express, such as `The property F will invariantly be true`
and `The property F will eventually be true.`


## Definition 

We define recursive HML as such.
$$\varphi := X | tt | ff | {\varphi_{1}}^{\wedge}_{\vee}{\varphi_{2}} |~^{\langle a \rangle}_{[a]}\varphi$$
with the recursive variable $X$.

We define a function 
$\mathcal{O}_{F}(I):= O$
Where the input $I$ is the set of states assumed to 
satisfy the property $X$, and the output is the one that satisfies the property $F$


This fuckery is captured formally by 

$\mathcal{O}_{X}(S) = S$

$\mathcal{O}_{tt}(S) = Proc$

$\mathcal{O}_{ff}(S) = \empty$

$\mathcal{O}_{F_{1}\wedge F_{2}} = 
\mathcal{O}_{F_{1}}(S) \cap \mathcal{O}_{F_{2}}(S) $

$\mathcal{O}_{{F_{1}}\vee F_{2}} =
\mathcal{O}_{F_{1}}(S)\cup \mathcal{O}_{F_{2}}(S)$

$\mathcal{O}_{<a>F}(S) = 
\langle\cdot a \cdot\rangle\mathcal{O}_{F}(S)$

$\mathcal{O}_{[a]F}(S) = [\cdot a \cdot]\mathcal{O}_{F}(S)$

> It's a cool thing to mention that all this shit is 
> Monotonic, Meaning that if $X \subseteq Y $ then $F(X)\subseteq F(Y)$
## Example 