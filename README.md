# Theory-of-Computation-Automata-Theory
![Linear Algebra](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/banner.jpg)

This repository has been made by the help multiple material but specially from this [playlist](https://www.youtube.com/watch?v=58N2N7zJGrQ&list=PLBlnK6fEyqRgp46KUv4ZY69yXmpwKOIev&index=1). Check it when you need clarification. This is one of the best  explanation on the subject.
_______________________
A Finite State Automata is a simple machine with a finite number of state.

![map final state automata](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/FSA_example.PNG)

![vocabulary final state automata](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/FSA.PNG)

**Finite Atomaton** can be divided in two category and then in multiple sub category.

![map final state automata](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/FSA_Map.PNG)

We will see in details each category.
## FA Without output
### DFA Deterministic Finite Automaton
It is a **finite-state machine** that accepts or rejects strings of symbols and only **produces a unique computation** (or run) of the automaton for each input string. Deterministic refers to the uniqueness of the computation.

### NFA Non-deterministic Finite Automaton
Every DFA is also an NFA. It is because NFA are more flexible than DFA. here are the differences:
- given the current state there could be multiple next states.
- The next state may be chosen at random
- All the next states may be chosen in parallel.
[source](https://www.youtube.com/watch?v=ehy0jGIYRtE&list=PLBlnK6fEyqRgp46KUv4ZY69yXmpwKOIev&index=10)
#### Conversion of NFA to DFA
**Every DFA is an NFA, but not vice versa.**
**But there is an equivalent DFA for every NFA.**

Because :
![map final state automata](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/Dell_NFA_andDFA.PNG)

- Example 1.
![map final state automata](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/Convertion_NFA_to_DFA.PNG)
To convert this NFA to a DFA you basically just have to add the dead state. like so.

- Example 2
![map final state automata](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/conv.PNG)![map final state automata](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/conv21.PNG)
To convert this NFA to a DFA you have to "cheat" by adding a state that stand for the equivalent of the multiple state of the NFA.

- Example 3

[Full explanation](https://www.youtube.com/watch?v=--CSVsFIDng&list=PLBlnK6fEyqRgp46KUv4ZY69yXmpwKOIev&index=15)
#### Minimization of DFA
Minimization of DFA is required to obtain the minimal version of any DFA which consists of the minimum number of states possible.

e.g a DFA with 4 states is more optimized that the same one with 5 states.

###### States equivalence
States that are equivalent can be reduced to one state. But what does equivalent means exactly?
In essence :
![equivalent](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/equivalence.PNG)
It is still quit vague, here is a more practical explanation.

First of all there is multiple level/type of equivalence i.e **0 equivalence, 1 equivalence, 2 equivalence ...**
![equivalence](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/equ.PNG)
To find equivalent states we need to compare them for every possible input.

0 equivalence is the base that we use
it is composed of:
- one set with all the non-final-state(s)
- one set that all the final state(s)

1,2,3... equivalence have multiple set as well, The set that have multiples states are considered **x** equivalent where **x** is the level/type of the equivalence:

How to compare exactly ?
- Two states are equivalent if for input X state A and B have the **same output** or **any of the output** that is not part of the set of the previous equivalence.

When are we finished ?
- In the previous picture you can see that 2 and 3 equivalence are the same.
We can then conclude that it is possible to merge A and C in the state AC.

Here is the optimized version of the previous DFA.

![Minimized DFA](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/minimized_DFA.PNG)

What if there is an unreachable state?
- Just delete the given state and do the minimization as usual.

[full explanation and multiple example  here](https://www.youtube.com/watch?v=hOzc4BUIXRk&list=PLBlnK6fEyqRgp46KUv4ZY69yXmpwKOIev&index=20)
### Epsilon NFA
Epsilon NFA can have empty input.
The epsilon is used here to represent empty symbols.

- When a state get an epsilon as input it always goes to itself.

i.g If I define that the stat *A* should go to *B* when he recieve *epsilon* then it will go to *B* an *A* simultaniously.
![Espilon NFA](https://raw.githubusercontent.com/BasileBron/Theory-of-Computation-Automata-Theory/master/img/epsilon_NFA.PNG)
#### Convert E-NFA to NFA

1. Check if there is at least one path from initial state to one of the many possible accepting states which can be traversed only by null transitions. If so, add the initial state to the set of accepting states.

2. Now, choose two states in e-NFA (let's call them p and q) having null transition between them.

2. Remove the null transition.

3. Any incoming transition to p is to added as an incoming transition to q.
Eg. if there was an incoming transition from some other states (let's call them r and s) to p, then add new incoming transitions from r and s to q on those same input symbols, do not care for now if there are null transitions, just add them blindly.

4. Repeat steps 2, 3, 4 for all the null transitions in the e-NFA.  



## FA With output
### Moore machine
With the moore machine it is not a matter of ending in a final state since every state can have an output. You can print something in every state.

the output is dependent on the state and the input.

![Moore machine](/img/moore.PNG)
[]( )
### Mealy Machine
The only difference from the Moore machine is that the output is only dependent on the state.

![Mealy machine](/img/mealy.PNG)

## Acknowledgement
Huge thank to [Neso Academy](https://www.youtube.com/channel/UCQYMhOMi_Cdj1CEAU-fv80A) for this amazing [playlist](https://www.youtube.com/watch?v=58N2N7zJGrQ&list=PLBlnK6fEyqRgp46KUv4ZY69yXmpwKOIev&index=1).
