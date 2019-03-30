# Timed Automata
## Motivation
She sid
- Give an example of a Timed Automaton
- Show the LTS [Action, clock update, ] 
- Assume that when we do the update, we don't change the location
- Talk about why $\wedge$ and not $\vee$
- explain the equivalence classes

Many real-time systems depend on timing. 
InCCS timeouts were modelled using non-determinism
too abstract for certain questions(avg. time to send message)




>> V(x), where V is our clock function. X is a clock

`Region Graphs:`

## Definition


`Timed Automaton` (*TA*)
A tuple, $(\mathcal{L, l_{0}, E, I})$
$\mathcal{L}$: A Set of locations
$\mathcal{l_{0}}$: Initial Location
$\mathcal{E}$:Guards, Actions, Reset functions, ($\mathcal{l}\xrightarrow{G,A,R}\mathcal{l'}$)
$\mathcal{I}$: Invariants, Logical expressions that have to be true, otherwize there's  a deadlock.


`Time (Labeleded) Transition System`
> A single *instance* of a run on a *TA*

TLTS is a triple (Proc, Act, {$\xrightarrow{a}$})
Proc is a set of processes,

Act = the set of actions, or time elapsing steps.

$\xrightarrow{a}$ is a set of relations,
such that $\xrightarrow{a}|a\in Act$
or that $\xrightarrow{d} | d \in \mathbb{R}^{\ge0}$


`Region Graphs`



> Why can't we have ors

`Because then your equivalent class will not be convex.`

>> Meaning that there are no 'holes' in the equivalence class.

>> Given 2 locations on our region graph, all locations between them must exist.

`Why do we need region graphs?`
*To discretize clock space.*
We use **Equivalence classes** to decide 


## Example

> locations, zone graph,