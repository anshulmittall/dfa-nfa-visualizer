# DFA / NFA String Processing Visualizer

Interactive simulator for CSET302 Automata Theory and Computability (Simulator Design, Topic 7).

**Live demo:** https://anshulmittall.github.io/dfa-nfa-visualizer/

## Features

- Define your own DFA, NFA or ε-NFA: states, alphabet, start state, accepting states and transition table
- State diagram with active states and traversed transitions highlighted at every step
- Step-by-step playback (play, pause, step forward and back) with an input tape
- Trace table showing δ applied at each step, including ε-closures
- Computation tree of every path an NFA can take, with accepting, rejecting and dead branches
- Test suite that compares expected and actual results for a list of strings
- Input validation with clear messages (unknown symbols, missing DFA transitions, unreachable states)

## Run locally

Open `index.html` in any modern browser. No install or build step is needed.

## Algorithm

```
S ← ε-closure({ q0 })
for each symbol a in w:
    S ← ε-closure( ⋃ δ(q, a) for q in S )
accept if S ∩ F ≠ ∅
```

A DFA is the special case where S always holds exactly one state.
