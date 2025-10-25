# Clean Architecture: A craftsman's guide to software structure and design

## What is design and architecture?

- Architecture is often used in the context of high level that is divorced from
  the low-level details. Design focuses on structures and decisions at a lower level.

## Paradigms

- Structured programming - Discovered by Dijkstra in 1968.
  Structured programming imposes discipline on direct transfer of control.
- Object-Oriented programming - Discovered in 1966 by Dahl and Nygaard.
  Object-oriented programming imposes the discipline on indirect transfer of control.
- Functional programming - Alonzo Church.
  Functional programming imposes discipline upon assignment.

## Structural programming

- Dijkstra recognized a problem early on that programming is hard
  and that programmers don't do it very well.
  Programs are complex and has too many details for
  the human brain to manage without help.
- The discipline of proof was what Dijkstra used
  to use proven structures to tie them together with code.
- Dijkstra realized that he would have to demonstrate the
  technique for writing basic proofs of simple algorithms.
  He found it challenging.
- Dijkstra wanted formal proofs for high-quality software.
  Thank GOD he didn't get his wish.
- "Testing shows the presence, not the absence, of bugs." - Dijkstra
- Structured programming recursively decomposes a program
  into a set of small provable functions.
- This is why functional decomposition is still a great practice.
