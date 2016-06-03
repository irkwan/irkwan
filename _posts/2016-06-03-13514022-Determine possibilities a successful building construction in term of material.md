---
layout:     post
title:      Determine possibilities a successful building construction in term of material
date:       2016-06-03
summary:    Silakan klik pada judul untuk penjelasan tugas
categories: tugas
---

# Determine possibilities a successful building construction in term of material
When you read the topic, I guess you will not understand what the writer talks about. Hopefully, when you read this article, you can understand what it means. Before we go further about the main topic, the writer wants to give the reason why he took this topic. The writer just heard about one of the most visited place in his hometown, Medan, _Sun Plaza_, its roof collapsed and a year ago one of its escalator collapsed too. He was curious how is that even possible, who should be blamed on, the constructor or the architect.

![SunPlazaRoof Collapsed](http://wp.medansatu.com/wp-content/uploads/2016/05/sun-plaza-runtuh-medansatu.jpg)

Instead of blaming who do the mistake, the writer suggest to minimize any casualties. One of the method is like the article's title _Determine Possibilities a Successful Building Construction in Term of Material_.There are few strategy to determine the possibilities. One of the strategy is using _Language Theory_.

## Language Theory
Language theory or automata theory is a study of how machines and automata work. It's also known as the computational problem solving. It's one of computer science study that deals with design, analysis and the programming language. An automaton with limited state or finite state is called _Finite Automata_. It is a concept of theory language. There are other concepts too, they are _Regular Language_, _Pushdown Automata_, _Context-Free Grammar_, _Turing Machine_ and _Decidability_. Why the writer choose theory language? The reason is quite simple. It's because he read an article that theory language can prevent something before it's getting worse. In this article, the writer want to try using Finite Automata. 

## Finite Automata
There are 2 types of Finite Automata.
- Deterministic Finite Automata (DFA)
- Non-Deterministic Finite Automata (NFA)

### Deterministic Finite Automata (DFA)
DFA has 5 tuples where :
- Q is a set of states.
- ∑ is a set of symbols
- δ is a transition function
- qo is an initial state
- F is a set of final state

DFA can be represented by graphical diagram called state diagram.
- initial state is a state with an arrow from no where pointed on circle.
- final state is a state with double circle.
- an arrow is labelled with an input.
- the cicrle is represented as the state.

### Non-Deterministic Finite Automata (NFA)
NFA has the same tuple with DFA which is Q, ∑, δ, qo, F and has the same way to draw state diagram. Then what the different between NFA and DFA. NFA can have 2 or more arrows pointing different states with the same input but DFA cannot. 

### Pushdown Automata (PDA)
PDA has the same way of designing context-free grammar. PDA has the same function with memory stack that can remember infinite amount of number. A PDA has three components:
- an input tape
- a control unit
- a stack with infinite size.

PDA has two operations. they are push and pop. Push is adding new information on the top of other information. Pop is removing information from the top.
PDA has 7 tuples
- Q is a set of states
- ∑ is a set of symbols
- S is a set of stack symbols
- δ is the transition function
- q0 is the initial state
- F is the final state
- I is the initial stack

## Determine the possibilities a successful contruction using Finite Automata
Material is one of the important thing when to construct a buidling. Wrongly mixing material amount can cause collapse of a buidling. In this article, we are going to use how much material so the building can stay good. This is some kind of simulator machine. For example we are making a column for supporting structural, let say it needs 1 : 2 of cements, water. let's short cements, water into c, w and as a ∑. Each of them amount to 50 kg. if the user input cww ,the column has 50 kg of cements and 100 L of water. The initial state is input from any of the material. The final state is when the material meets the same ratio mentioned above. The following is design of the PDA.

P = {Q = {q0,q1}, ∑ = {c,w}, S = {c,w}, δ, q0, q1, Zo}
The transition:
- δ(q, c, Zo) = δ(q, cc)
- δ(q, c, c) = δ(q, cc)
- δ(q, w, c) = δ(q, e)
- δ(q, e, Zo) = δ(p, e) -> acceptable state.

<img src="https://www.dropbox.com/s/lwtaadhuw2npifo/DFA.jpg?dl=0">


## Conclusion
Material is an important thing. Bad composition will cause disaster. Many life will be wasted and money will be drained too. By using theory language to have good composition hopefully it can prevent any casualties.

## Reference
- http://www.tutorialspoint.com/automata_theory/
- http://medansatu.com/berita/tag/atap-sun-plaza-medan-runtuh/url/bruukkk-atap-sun-plaza-medan-runtuh-lihat-fotonya
