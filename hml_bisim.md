# HML & Bisimilarity
## Motivation
    HML is a way to logically define properties
    that are, or are not satisfied by some processes. 


## Definition
    We define the syntax of HML as:
$$ \varphi= tt~|~
            ff~|~
            \varphi_{1} \vee \varphi_{2} ~|~
            \varphi_{1} \wedge \varphi_{2}~|~
            \langle\alpha\rangle\varphi~|~
            [\alpha]\varphi
$$

So by this definition, 
We can say that this logic can describe the available actions of the process, up to some finite depth, called the modal depth. 


> What about negation? 

$ \mathtt{tt}^{c} = \mathtt{ff} $
$ \mathtt{ff}^{c} = \mathtt{tt} $
$ (F\wedge G)^{c} = F^{c} \vee G^{c}$
$ (F\vee G)^{c} = F^{c}\wedge G^{c} $
$ (\langle\alpha\rangle F)^{c} = [\alpha]F^{c}$
$ ([\alpha]F)^{c} = \langle\alpha\rangle F^{c}$

> We can intuit that if $P\models F$ then $P\not\models F^{c}$



## Example
We can say that $${S}\thicksim {T} \iff Prop(S) = Prop(T)$$
Or, in human language, that humans understand, 
S and T are bisimilar if they satisfy the same HM predicates.

This can be proven in two ways: 

--- 

Assume that $ S \thicksim T $ and $S \models F~\text{for some } F \in \mathbf{M}$

**We shall prove that since $S\thicksim T$, $S$ and $T$ satisfy the same formula**

We only show for $F = [a]G$, some $\text{formula} \in \mathbf{M}$


By using structural induction we prove  that $T \models F$

Our $I$nductive $H$ypothesis( $IH$ ):

$\forall P_{1}~\&~P_{2}, if P_{1} \thicksim P_{2}~\&~P_{1} \models F~\text{then}~P_{2}\models F$

Using this hypothesis, we shall prove that $T \models [a]G$

To this end, assume that $T\xrightarrow{a}T'$ for some $T'$

We wish to show that $T' \models G$

Now since $S \thicksim T$ and $T\xrightarrow{a}T'$ then $S\xrightarrow{a}S'$ and $S' \thicksim T'$ 

Since we assumed that $S \models [a]G$ we have that $S' \models G$ 

By our $IH$, since $S' \thicksim T'$ then $T' \models G$

Therefore, each $T'$ such that $T\xrightarrow{a}T', T' \models G$

--- 

Assume that $Prop(S) = Prop(T)$

**We shall prove that S and T are strongly bisimilar** 

For this one, we need that T is image finite. 

We define a relation $\mathcal{R}:= \{(S, T)\in\mathcal{R}|Prop(S) = Prop(T)\}$ **and S, T are processes**

We assume that $(S, T) \in \mathcal{R}$ and that $S\xrightarrow{a}S'$ 

We shall now argue that there **exists** a process $T'$ such that $T\xrightarrow{a}T'$ and $(S', T')\in \mathcal{R}$


We assume towards contradiction, that there is **no** $T'$ such that 

$T\xrightarrow{a}T'$ and $Prop(S') = Prop(T')$

Since T is *IF* there is a finite set of states $T$ can reach with an $a$ transition. $\{T'_{1}, \ldots, T'_{n}\}$

And by our assumption, there is no $T'_{i}$  such that $Prop(T'_{i}) = Prop(S')$ in the set.

So, for each  $T'_{i}$ there is a formula 
$F_{i}$ *st.*  $T'_{i} \models F_{i}$ and $S' \not\models  F_{i}$

We are now in the position to create a formula that T satisfies, and S does not. 
Specifically, 
$$<a>(F_{0} \wedge F_{1}\wedge\ldots\wedge F_{n})$$ 

--- 
**Note that the prior proof works for non-image-finite processes.**