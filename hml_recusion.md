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



`Why do we care that some function has a fixed point?`
A function $F_{\varphi}(S)$ must have a fixed point, for a process to satisfy the $\varphi$


`To find the minimum fix point`, we use the fact that 
 $\empty \subseteq f(\empty)$
then $f(\empty) \subseteq f(f(\empty))$
then we apply $f~\text{to}~\empty$ until $f^{n}(\empty) = f^{n+1}(\empty)$ 
then $f^{n}(\empty)$
is your minimal fixed point.

`To find the Maximum fixed point`, we use the fact that
$f(Proc) \subseteq Proc$ And because f is monotonic, 
$f(f(Proc)) \subseteq f(Proc)$

Similarly, we can apply it until $f^{n}(Proc) = f^{n+1}(Proc)$.
then $f^{n}(Proc)$ is your max fixed point.

 ## Example 

By Tarsky, all functions defined in Recursive HML have a unique minimum and maximum fix point,
> this is because the function is monotonic!

To find the minimum fix point, 
the function $\mathcal{F}$ is applied repeatedly on $\empty$

Because $\mathcal{F}$ is monotonic, $\empty \subseteq \mathcal{F}(\empty) $

This means that because proc is finite, $\mathcal{F}^{n}(\empty) = \mathcal{F}^{n+1}(\empty)$

--- 

This is also applicable in reverse.

> I spoke with anna, and suddenly 
Because $F(Proc) \subseteq Proc$ not $Proc \subseteq F(Proc)$

We can say that 
$Proc \supe F(Proc)$ and $F(Proc) \supe F(F(Proc))$
Then at some point, $F^{n}(Proc) = F^{n+1}(Proc)$

---

`This is great, The former method works by building up from the empty set... The latter works by intersecting from the Proc set`